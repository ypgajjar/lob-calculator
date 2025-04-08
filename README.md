Line of Balance (LOB) Tool
	It is a web‑based Line of Balance (LOB) and Gantt chart application designed for project management. The tool features an intuitive, modern user interface built with Tailwind CSS and Chart.js that supports PMBOK/AACE-based dependency scheduling, hierarchical activity views (WBS), and robust charts for visualizing project timelines and productivity.

Features
	Modern, Elegant UI:
		Floating labels for all form inputs for a clean, modern look.
		Card‑style activity views with a hierarchical (tree) structure based on WBS codes.
		Refined Gantt and LOB charts with rounded bars and grid‑aligned data points.
	Project Scheduling:
		Implements PMBOK/AACE‑compliant dependency scheduling logic (FS, SS, SF, FF) to calculate start/end dates for activities.
		Supports manual adjustments for start dates when necessary.
		Enforces unique WBS codes.
	Charts & Visualization:
		Line of Balance (LOB) Chart:
		Displays each activity as a diagonal line from its start unit to its units + start unit. The Y‑axis increments by 1 unit and the X‑axis is a time‑scale aligned to daily grid lines.
	Gantt Chart:
		Presents a stacked bar chart without showing the offset values. The tooltip shows the activity’s details (WBS, Name, and Duration).
	Edit & Delete:
		Users can easily edit or delete existing activities directly from the WBS view.

Getting Started
	Prerequisites
		To run the tool locally, you'll need a modern web browser (Chrome, Firefox, Edge, etc.). No backend is required as the application is entirely client‑side.
	Installation
		Clone the repository:
			git clone https://github.com/yourusername/elegant-lob-tool.git
			cd elegant-lob-tool
		Open the HTML file:
			Open index.html in your favorite browser (e.g., by double‑clicking the file or using your development server).
	Usage
		Enter the Project Start Date:
			Use the date picker at the top of the page.
		Add Activity:
			Fill in the form on the left with your activity details.
			Use floating label fields for a clean input experience.
			Add dependency links (choose the predecessor, dependency type, and lag in days) as needed.
			Click "Add Activity" to include the activity in the project plan.
		View Activities (WBS View):
			The activities are displayed in a hierarchical tree based on WBS codes.
			Each activity card shows duration and productivity (units/day).
			Use the Edit or Del buttons on each card to modify or remove an activity.
		Visualize with Charts:
			The Line of Balance Chart displays each activity as a diagonal line aligned with daily grid lines.
			The Gantt Chart shows the timeline of activities with refined rounded bars.

Technologies Used
	HTML5, CSS3, and JavaScript
	Tailwind CSS for the UI.
	Chart.js for data visualization.
	date-fns for date manipulation.

Acknowledgments
	Inspired by industry standards in project management (PMBOK & AACE).
	Built using open source libraries such as Tailwind CSS and Chart.js.