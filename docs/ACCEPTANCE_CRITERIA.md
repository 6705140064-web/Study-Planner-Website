# Acceptance Criteria – Study Planner Website

The MVP is accepted when the following conditions can be demonstrated.

## AC-01: Create a Task
**Given** the student is on the task page,  
**When** the student enters a task title and saves it,  
**Then** the task is saved and appears in the task list.

## AC-02: Set a Deadline
**Given** the student is creating or editing a task,  
**When** the student selects a valid due date and saves the task,  
**Then** the selected deadline is displayed with that task.

## AC-03: View Tasks
**Given** the student has saved tasks,  
**When** the student opens the task list,  
**Then** the website displays the saved tasks and their deadlines.

## AC-04: View the Study Schedule
**Given** the student has tasks with due dates,  
**When** the student opens the schedule view,  
**Then** the tasks are shown in due-date order.

## AC-05: Mark a Task as Completed
**Given** a task is pending,  
**When** the student selects the completed option,  
**Then** the task status changes to completed and the new status is visible.

## AC-06: Edit a Task
**Given** a saved task exists,  
**When** the student changes its information and saves,  
**Then** the updated information is displayed.

## AC-07: Delete a Task
**Given** a saved task exists,  
**When** the student chooses to delete it and confirms,  
**Then** the task is removed from the task list.

## AC-08: Keep Data After Refresh
**Given** the student has saved a task,  
**When** the page is refreshed,  
**Then** the saved task is still available.

## Basic Validation
- A task title cannot be empty.
- A task must have a valid title before it can be saved.
- Invalid or missing dates should be handled with a clear message.
