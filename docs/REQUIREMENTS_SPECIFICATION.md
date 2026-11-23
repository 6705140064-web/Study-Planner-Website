# Requirements Specification – Study Planner Website

## 1. Introduction
The Study Planner Website is a web application that helps students manage assignments, deadlines, and study schedules. This document describes the main functional and non-functional requirements for the MVP.

## 2. Users
- **Student:** The main user who creates and manages personal study tasks.

## 3. Functional Requirements
| ID | Requirement | Description | Priority |
|---|---|---|---|
| FR-01 | Add task | The student can create a task with a title and details. | Must have |
| FR-02 | Set deadline | The student can assign a due date to a task. | Must have |
| FR-03 | View tasks | The student can see a list of saved tasks and their deadlines. | Must have |
| FR-04 | Edit task | The student can update a task's title, details, or deadline. | Should have |
| FR-05 | Delete task | The student can remove a task. | Should have |
| FR-06 | Study schedule | The student can view tasks arranged by their due dates. | Must have |
| FR-07 | Update status | The student can mark a task as pending or completed. | Must have |

## 4. Non-Functional Requirements
- **Usability:** Pages and controls should be clear and easy for students to understand.
- **Performance:** Common actions such as viewing and saving tasks should complete within a reasonable time under normal use.
- **Reliability:** Saved tasks should remain available after the page is refreshed.
- **Compatibility:** The website should work on current desktop and mobile web browsers.
- **Security:** The application should not expose one user's private tasks to another user. If accounts are implemented, passwords must be stored securely using an appropriate password-hashing method.

## 5. MVP Limitations
The first version focuses on task creation, deadlines, schedule viewing, and completion status. Automatic reminders, calendar synchronization, and collaboration are future enhancements.

## 6. Constraints and Assumptions
- The application is developed as a website.
- The project is built within the time and resources available to the student team.
- The database technology may be selected by the development team.
