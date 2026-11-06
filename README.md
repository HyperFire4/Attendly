Build a Modern Student Attendance Tracker Web App
Project Overview

Build a modern, minimal, responsive web application called Attendly (the name can be changed later).

The application is a personal attendance tracker designed for college and university students.

Students should be able to add their subjects, configure their weekly class schedules, mark attendance daily, and monitor their attendance statistics.

The most important feature is an intelligent attendance calculator that tells students exactly how many more classes they can miss while maintaining their required attendance percentage, defaulting to 80%.

This should feel like a polished, modern SaaS product rather than a traditional college management system.

1. Core Requirements
Subject-wise attendance tracking.
Custom subject management.
Custom weekly class schedules.
Daily attendance marking.
Automatic attendance calculations.
Attendance calendar.
Attendance statistics and visualizations.
Persistent data storage.
Responsive design for desktop and mobile.

The application should be fully functional. Do not create buttons that are merely decorative or statistics that use hardcoded sample values.

2. Dashboard

Create a beautiful dashboard as the main landing page.

At the top, display:

A welcoming heading such as "Good morning!"
Current date.
A short attendance summary.

Create summary cards displaying:

Overall Attendance: Current attendance percentage across all subjects.
Classes Attended: Total number of attended classes.
Classes Missed: Total number of absent classes.
Total Classes: Total classes conducted.

Below the summary cards, create a prominent attendance insights section.

Display:

Overall attendance percentage using a circular progress indicator.
Default attendance target of 80%.
Number of additional classes that can be missed without falling below the target.
Number of consecutive classes that must be attended to recover to the target, if currently below it.

Add a subject-wise overview section containing individual subject cards.

Each subject card should display:

Subject name.
Attendance percentage.
Classes attended.
Classes missed.
Total classes.
A colored progress bar.
Remaining safe absences.
An appropriate status indicator.

Use visual status indicators:

Green: Safely above the attendance target.
Yellow: Close to the attendance target.
Red: Below the attendance target.

Include a quick action to mark today's attendance.

3. Subject Management

Create a dedicated Subjects page.

Students must be able to:

Add new subjects.
Edit existing subjects.
Delete subjects.
Assign a custom color to each subject.
Set a custom attendance target for each subject (default 80%).
Configure the weekly class schedule for each subject.

When adding a subject, provide:

Subject name.
Optional subject code.
Subject color.
Attendance target percentage.
Weekly class days.
Optional class time.

Allow multiple classes of the same subject on the same day.

Make subject creation and editing simple and intuitive.

4. Attendance Marking

Create a dedicated Attendance page.

Display classes scheduled for the selected date.

For every scheduled class, allow students to select:

Present
Absent
Not marked

Use clear, easy-to-tap buttons.

Important functionality:

Allow attendance marking for today and previous dates.
Allow editing previously recorded attendance.
Prevent duplicate attendance records for the same class.
Allow multiple classes of the same subject on one day.
Automatically update all statistics when attendance changes.
Show a clear confirmation or visual feedback when attendance is saved.

Include a date selector so students can navigate between days.

Do not automatically mark a class as absent simply because the student has not marked attendance yet.

5. Smart Attendance Calculator

This is a critical feature and must work with mathematically accurate calculations.

For every subject, calculate the following:

Current attendance

Attendance percentage = (Classes Attended / Total Classes Conducted) × 100.

Safe absences

Calculate the maximum number of additional classes the student can miss while maintaining their attendance target.

Use this formula:

Maximum additional absences = floor((Classes Attended / Target Attendance) - Total Classes Conducted)

Do not return a negative number. If the student is already below the target, show zero safe absences.

Classes needed to recover

If the student is below the target, calculate the minimum number of consecutive classes they must attend to reach the target.

Use:

Required consecutive attended classes = ceil((Target × Total Classes - Classes Attended) / (1 - Target))

Use the target as a decimal, such as 0.80 for 80%.

If the student is already meeting or exceeding the target, display that they are currently meeting their attendance requirement.

Future projections

Allow students to simulate future attendance:

What happens if I attend the next 5 classes?
What happens if I miss the next 2 classes?
What will my attendance be after 10 more classes?

Show the projected attendance percentage immediately.

Important edge cases
If no classes have been conducted, display "No attendance data yet" instead of NaN or an incorrect percentage.
Never display negative safe absences.
Round displayed percentages to one decimal place.
Use unrounded values for calculations.
Make sure calculations update immediately after attendance is edited.

The overall attendance should be calculated using total attended classes divided by total conducted classes across all subjects, not by taking a simple average of subject percentages.

6. Attendance Calendar

Create a monthly attendance calendar.

Requirements:

Display all dates in a standard monthly calendar layout.
Highlight dates with attended classes.
Highlight dates with absent classes.
Use different visual indicators for mixed attendance days.
Clearly distinguish days without scheduled classes.
Allow navigating between months.
Clicking a date should display all scheduled classes and their attendance statuses.
Allow editing attendance directly from the selected date.

Use subtle colors that match the overall design.

7. Weekly Timetable

Create a weekly timetable page or section.

Display the student's weekly class schedule.

Features:

Monday through Sunday.
Subject names and class times.
Different colors for different subjects.
Ability to add, edit, or remove scheduled classes.
Ability to view today's classes quickly.

The timetable should be used to populate the daily attendance marking interface.

Changing a schedule should not silently change historical attendance records.

8. Settings

Create a simple settings page.

Include:

Default attendance target (80%).
Light and dark mode toggle.
Semester start and end dates (optional).
Subject management shortcuts.
Export attendance data as CSV.
Reset attendance data with a confirmation dialog.

Use persistent storage so that information remains available after refreshing or reopening the website.

9. Design and User Experience

The design is extremely important.

Create a premium, modern, minimalist SaaS dashboard.

Design inspiration:

Linear
Notion
Modern analytics dashboards
Clean productivity applications

Visual requirements:

Minimal interface with plenty of whitespace.
Clean typography, preferably Inter.
Soft neutral backgrounds.
Indigo or violet as the primary accent color.
Rounded cards and subtle borders.
Elegant progress bars and circular progress indicators.
Consistent spacing and alignment.
Smooth, subtle transitions.
Attractive empty states.
Clear visual hierarchy.
No unnecessary gradients or excessive animations.

Desktop:

Use a left sidebar for navigation.
Main content should use a responsive dashboard grid.

Mobile:

Use a compact layout.
Replace the sidebar with a bottom navigation bar or mobile-friendly menu.
Make attendance marking easy with one hand.
Ensure cards and charts fit smaller screens.

Navigation should include:

Dashboard
Attendance
Subjects
Timetable
Calendar
Settings
10. Technical Requirements

Build a functional frontend and implement the necessary data management.

Use a modern component-based architecture.
Use reusable components.
Use a clean and maintainable project structure.
Ensure all calculations are dynamic.
Use localStorage or IndexedDB for persistent local data.
Avoid requiring a backend or user account for the initial version.
Ensure the app works after refreshing the browser.
Handle empty states and invalid inputs gracefully.
Include confirmation dialogs for destructive actions.
Ensure the interface works on mobile, tablet, and desktop.

Organize attendance records so that each class session has a unique identifier, subject, date, and attendance status.

Keep scheduled classes separate from actual attendance records.

Do not count unmarked classes as attended or absent.

11. Important Implementation Instructions

Prioritize functionality over decorative elements.

All buttons, navigation links, forms, attendance controls, and settings must work.

Do not use hardcoded attendance statistics in the actual application.

Use realistic sample data only if needed for an initial demo, and allow users to remove it.

Ensure that adding, editing, or deleting a subject correctly updates the dashboard and relevant views.

Ensure attendance calculations are consistent across the dashboard, subject cards, calendar, and calculator.

Build the complete application rather than just a static UI mockup.

Final Goal

The finished product should make it possible for a student to:

Add their college subjects.
Configure their weekly timetable.
Mark daily attendance in a few seconds.
See their overall and subject-wise attendance.
Know exactly how many classes they can safely miss.
Know how many classes they need to attend to recover their attendance.
View their attendance history in a calendar.
Track everything without complicated setup.

The experience should be simple, fast, visually beautiful, and reliable.
