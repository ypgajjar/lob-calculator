# Line of Balance (LOB) Scheduler & Analyzer

A web-based tool for creating, visualizing, and analyzing project schedules using the Line of Balance technique. It also includes Gantt chart visualization, activity management with dependencies, and various export options.

This tool is built with HTML, CSS (Tailwind CSS for basic layout, with custom theming), and vanilla JavaScript. It utilizes Chart.js for charting and jsPDF/html2canvas for PDF export.

## Features

*   **Project Setup:**
    *   Define a global project start date.
*   **Activity Management:**
    *   Add, edit, and delete activities with WBS codes.
    *   Define overall duration, number of repetitive units, and start unit for each activity.
    *   Optionally set a manual start date for an activity.
    *   Manage complex dependencies between activities (Finish-to-Start, Start-to-Start, Finish-to-Finish, Start-to-Finish) with configurable lag times.
*   **Scheduling & Calculation:**
    *   Automatic calculation of activity start and end dates based on dependencies, project start date, and activity durations.
    *   Dynamic recalculation of the entire schedule upon changes.
*   **Visualization:**
    *   **Line of Balance (LOB) Chart:** Visualizes the rate of production/completion of units for each activity over time.
    *   **Gantt Chart:** Displays a traditional bar chart view of activity timelines.
    *   **WBS View:** Hierarchical tree view of activities, color-coded to match chart representations.
*   **Project Summary:**
    *   Displays overall project start date, end date, and total duration.
*   **Data Persistence & Management:**
    *   **Local Storage:** Save multiple projects directly in the browser for quick access. Load saved projects from a selectable list.
    *   **JSON Export/Import:** Export the entire project (settings and activities) to a JSON file for backup, sharing, or transfer between browsers/computers. Import projects from these JSON files.
    *   **Reset Project:** Clear the current project and start fresh.
*   **Reporting & Export:**
    *   **CSV Export:** Export activity data (WBS, name, dates, duration, units, dependencies) to a CSV file.
    *   **PDF Export:** Generate a comprehensive PDF report including:
        *   Project summary.
        *   A detailed table of activities with their properties.
        *   Line of Balance chart image.
        *   Gantt chart image.
        *   Page numbers in the footer.
        *   Charts start on new pages for better layout.
*   **User Interface:**
    *   Themed interface with floating labels for input fields.
    *   Tooltips for buttons and input fields to guide the user.
    *   Global message area for user feedback (success, error, info messages).
    *   Responsive layout for dependency rows (items wrap on smaller screens).

## Technologies Used

*   **HTML5**
*   **CSS3:**
    *   Tailwind CSS (via CDN for rapid layout prototyping)
    *   Custom CSS for theming and detailed styling
*   **JavaScript (ES6+):** Vanilla JS for all application logic.
*   **Chart.js:** For rendering LOB and Gantt charts.
    *   `chartjs-adapter-date-fns` and `date-fns`: For date handling in Chart.js.
*   **jsPDF & html2canvas:** For generating PDF reports by capturing chart images and structuring text.
*   **Font Awesome:** For icons.
*   **Google Fonts:** For custom typography (`Aldrich`, `Exo 2`, `Roboto Mono`).

## How to Use

1.  **Open `index.html`:** Simply open the `index.html` file in a modern web browser (Chrome, Firefox, Edge, Safari recommended).
2.  **Set Project Start Date:** Begin by selecting the overall start date for your project.
3.  **Add Activities:**
    *   Use the "Add/Edit Activity" form on the left.
    *   **WBS Code:** Enter a hierarchical code (e.g., `1`, `1.1`, `1.1.2`).
    *   **Activity Name:** A descriptive name.
    *   **Overall Duration:** The total time in days for the activity to complete all its units.
    *   **Manual Start Date (Optional):** If this activity must start on a specific date, irrespective of dependencies (unless dependencies push it later).
    *   **Number of Units:** The total number of repetitive units (e.g., floors, houses, software modules).
    *   **Start Unit (Informational):** Typically `1`. This is the starting unit number on the LOB chart's Y-axis for this activity.
    *   **Dependencies:**
        *   Click "Add Dependency".
        *   Select a "Predecessor" activity from the dropdown.
        *   Choose the "Dependency Type" (FS, SS, FF, SF).
        *   Enter "Lag" in days (can be positive or negative).
    *   Click "Add Activity" or "Update Activity" (if editing).
4.  **View Schedule:**
    *   The **Project Summary** updates with overall dates and duration.
    *   The **Activities (WBS View)** lists all activities hierarchically. Cards have a left border matching their chart color.
    *   The **Line of Balance Chart** and **Gantt Chart** will render based on the calculated schedule.
5.  **Manage Project Data:**
    *   **Save (Local Storage):** Click Save to save the current project state to your browser's local storage. You'll be prompted for a project name.
    *   **Load (Local Storage):** Click Load to open a modal where you can select a previously saved project from local storage.
    *   **Reset:** Click Reset to clear the current project and start a new one.
    *   **Export JSON:** Click Export JSON to download a JSON file of your entire project. This is recommended for backups or transferring to another computer/browser.
    *   **Import JSON:** Click Import JSON to load a project from a previously exported JSON file.
6.  **Export Reports:**
    *   **Export CSV:** Click Export CSV to download a CSV file of the activity list.
    *   **Export PDF:** Click Export PDF to generate and download a PDF report.

## File Structure

*   `index.html`: The single HTML file containing all the structure, CSS, and JavaScript.

## Development Notes & Potential Future Enhancements

*   **Error Handling:** While basic error messages are shown, more comprehensive validation and error handling could be added.
*   **Critical Path:** The current version does not explicitly calculate or highlight the critical path.
*   **Resource Management:** No features for resource allocation or leveling.
*   **Performance:** For extremely large projects (thousands of activities), performance of recalculations and rendering might degrade. Optimizations or a more robust data management approach (like IndexedDB or a virtual rendering list) could be considered.
*   **Advanced PDF Table:** For more complex PDF table layouts, integrating a library like `jspdf-autotable` would be beneficial.
*   **Accessibility (A11y):** While some ARIA attributes are used, a full accessibility audit and improvements could be made.
*   **Backend Integration:** For multi-user collaboration, persistent cloud storage, or more advanced features, integrating a backend service would be necessary.
*   **UI/UX Refinements:** Continuous improvements to the user interface and experience.

## Browser Compatibility

The tool is designed for modern web browsers that support ES6 JavaScript, Chart.js, and the Local Storage API. Tested primarily on Chrome and Firefox. Some visual aspects or advanced API usage (like PDF generation) might have slight variations in older browsers.
