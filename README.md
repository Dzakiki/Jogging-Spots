# Jogging Spots

[![Ask DeepWiki](httpshttps://devin.ai/assets/askdeepwiki.png)](https://deepwiki.com/Dzakiki/Jogging-Spots)

This repository contains a JavaFX application for managing a database of jogging spots across Singapore. The application provides a graphical user interface to view, add, edit, and delete various types of jogging locations, including Parks, Park Connectors, and Stadiums. It interacts with a MySQL database to persist data.

## Features

*   **View Jogging Spots**: Display a comprehensive list of all jogging spots from the database.
*   **Dynamic Filtering**: Filter the list of spots by category (Park, Park Connector, Stadium) using interactive checkboxes.
*   **Add New Spots**: A dedicated form to add new jogging spots. The form dynamically adjusts to capture category-specific details:
    *   **Park**: Specify if it has a seaview.
    *   **Park Connector**: Specify its distance in kilometers.
    *   **Stadium**: Specify its closing time.
*   **Find, Edit, and Delete**:
    *   A search/management window to find specific jogging spots.
    *   Select a spot to view its details, edit its attributes, or delete it from the database.
*   **Stadium Event Management**:
    *   View unavailability for any stadium for the next 14 days.
    *   Add new event dates to mark a stadium as unavailable.

## Application Architecture

The application is built using Java and JavaFX, following an object-oriented design.

*   **`JoggingSpot`**: An abstract base class for all jogging locations.
*   **`Park`, `ParkConnector`, `Stadium`**: Concrete subclasses that extend `JoggingSpot` and include specific attributes for each type of location.
*   **`JSApp_JFX`**: The main application class with the primary GUI. It provides the main dashboard for viewing and filtering spots and launching other functions.
*   **`JSApp_Add`**: A JavaFX window for adding new jogging spots to the database.
*   **`JSApp_FindJS`**: A window that lists all spots and allows the user to select one to edit, delete, or (for stadiums) add an event date.
*   **`JSApp_Edit`**: A window for modifying the details of an existing jogging spot.
*   **`JSApp_EventDate`**: A dedicated window for adding unavailability dates for stadiums.
*   **`DBUtil`**: A utility class that handles all JDBC connections and SQL query execution against the MySQL database.

## Technologies Used

*   **Language**: Java 16
*   **GUI**: JavaFX
*   **Database**: MySQL
*   **Connectivity**: JDBC (via mysql-connector-java)

## Setup and Usage

1.  **Database Setup**:
    *   Ensure you have a MySQL server running.
    *   Create a database named `assignment_pr_3`.
    *   The application expects two tables: `jogging_spot` and `unavailability_date`. You will need to create these tables with the appropriate columns based on the application's queries.
    *   The database connection is configured in the code to connect to `jdbc:mysql://localhost:3306/assignment_pr_3` with the username `root` and an empty password.

2.  **Run the Application**:
    *   Compile the Java source files.
    *   Run the `JSApp_JFX.java` file (`project_3` package) as the main entry point to launch the GUI application.