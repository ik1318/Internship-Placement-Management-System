# Internship Placement Management System
*Developed as part of a group project for SC2002.*

The Internship Placement Management System is a robust Java-based CLI tool designed to streamline and automate the internship application and placement process. It ensures transparency and efficiency by managing roles for Students, Company Representatives, and Career Center Staff within a unified ecosystem.

## THIS PROJECT PERFORMS THE FOLLOWING JOBS:

- **Data Processing:** Loading and managing student, staff, and company records from CSV files using a custom bootstrap mechanism.
- **Algorithmic Matching:** Enforcing eligibility rules based on student year and major to match students with appropriate internship levels (Basic, Intermediate, Advanced).
- **Application Lifecycle:** Managing the end-to-end journey of an internship from creation and staff approval to student application and final placement acceptance.
- **Result Exporting:** Automatically persisting all runtime changes (new applications, status updates, etc.) back to CSV format for session continuity.

## CORE FEATURES

- **Role-Based Access Control:** Distinct functional menus for Students, Company Representatives, and Career Center Staff.
- **Diversity & Eligibility Logic:**
    - **Year-Based Filtering:** Automatically restricts Year 1-2 students to "Basic" level internships while allowing Year 3-4 students access to all levels.
    - **Major-Specific Matching:** Filters opportunities to match the student's academic major or those open to all majors.
- **Opportunity Management:** Full lifecycle support for Company Representatives to create/edit opportunities and for Staff to review and approve them.
- **Automated Slot Management:** Real-time tracking of available slots, preventing over-subscription and marking opportunities as "FILLED" when capacity is reached.
- **Comprehensive Reporting:** Advanced DTO-based reporting for staff to monitor application trends, placement rates, and system statistics.

## PROJECT STRUCTURE

- `App.java`: Main entry point orchestrating the entire application.
- `src/code/cli/`: Boundary layer handling all user interactions and menu displays.
- `src/code/service/`: Control layer containing core business logic and coordination.
- `src/code/model/`: Entity layer representing domain objects (Student, Internship, Application).
- `src/code/repository/`: Persistence abstraction managing in-memory and file-based data access.
- `src/code/data/`: Data loading, CSV processing, and persistence management utilities.
- `src/code/dto/`: Data Transfer Objects for filtering and reporting.

## HOW IT WORKS

1. **System Bootstrap:** Upon startup, the system initializes repositories by loading data from seed CSV files via `DataBootstrap`.
2. **Authentication:** Users log in using their ID and password (supporting default password detection and security prompts).
3. **Menu Dispatching:** Based on the user's role, the system dispatches to the appropriate role-based menu (e.g., `StudentMenu`).
4. **Action Execution:** Users perform actions (View, Apply, Approve) which are processed by the service layer and updated in the repository.
5. **Persistence:** When the application exits, `DataPersistenceManager` exports the current state to updated CSV files, ensuring all changes are saved.

## TECH STACK

- **Language:** Java (Pure Java SDK)
- **Persistence:** CSV (Text-based storage) using `BufferedReader` and `BufferedWriter`.
- **Architecture:** Entity-Control-Boundary (ECB) pattern adhering to SOLID principles.
- **UI:** Command Line Interface (CLI) with interactive menu-driven navigation.
- **Documentation:** Full Javadoc API documentation and UML diagrams.