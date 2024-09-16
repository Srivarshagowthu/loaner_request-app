# Loaner Request Application

A **ServiceNow-based application** designed to automate the process of requesting, approving, and tracking loaner items such as laptops, projectors, or other assets. The application offers a seamless self-service experience, complete with approval workflows, inventory management, and real-time tracking.

## Table of Contents
- [Advantages](#advantages)
- [Technologies Used](#technologies-used)
- [ServiceNow Studio and Tools](#servicenow-studio-and-tools)
- [Publishing to GitLab](#publishing-to-gitlab)
- [Features and Concepts](#features-and-concepts)
  - [Client Scripts](#1-client-scripts)
  - [UI Actions](#2-ui-actions)
  - [UI Policies](#3-ui-policies)
  - [Business Rules](#4-business-rules)
  - [Flow Designer](#5-flow-designer)
- [Screenshots and Walkthrough](#screenshots-and-walkthrough)
- [Project Sketch](#project-sketch)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Advantages

- **Automation**: Streamlines the loan request process, reducing the need for manual intervention.
- **Approval Workflow**: Automatically routes requests to managers for approval or rejection.
- **Self-Service**: Allows users to submit and track their requests independently.
- **Real-Time Inventory Management**: Tracks available items and prevents over-allocation.
- **Notifications**: Sends automatic email or in-app alerts for approvals, rejections, or other updates.
- **Customizable Workflow**: Can be tailored to fit specific organizational needs, making it highly adaptable.

---

## Technologies Used

- **ServiceNow**: Core platform to develop the application.
- **JavaScript**: For both client-side and server-side scripting.
- **Flow Designer**: For creating custom approval workflows.
- **UI Policies, Client Scripts**: To manage dynamic form behaviors.
- **GitLab**: Source control for tracking code changes and collaborative development.
- **Glide API**: For querying and manipulating records.
- **HTML/CSS**: For customized user interfaces and styling.

---

## ServiceNow Studio and Tools

- **ServiceNow Studio**: This is where the application was built, managed, and extended. The platform’s core features, like **Client Scripts**, **Business Rules**, and **UI Actions**, were leveraged to ensure smooth functionality.
  
  - **Client Scripts**: JavaScript that runs in the browser, used to control field validation and behavior.
  - **UI Actions**: Custom buttons for form actions (e.g., submit, approve).
  - **UI Policies**: Manage field behavior, such as making fields required or visible under certain conditions.
  - **Business Rules**: Automates back-end processes, ensuring that data is processed correctly.
  - **Flow Designer**: A visual tool to create workflows, handling the routing and approval processes for requests.

---

## Publishing to GitLab

1. **Linking Source Control**: 
   - Navigate to **Studio** > **Source Control** > **Link to Source Control**.
   - Enter your GitLab repository URL and credentials.
   - Select the branch (e.g., main) and commit the changes.
  
2. **Commit and Push**:
   - Once linked, any changes made in the ServiceNow Studio, such as updates to Client Scripts, UI Actions, or Business Rules, can be committed to GitLab.
   - Collaborators can merge code from different branches and continue developing on separate features.

---

## Features and Concepts

### 1. Client Scripts
- **Purpose**: To control the form behavior and validate user input.
- **Example**: If the user selects a "Laptop" item, the "Serial Number" field becomes mandatory.

### 2. UI Actions
- **Purpose**: Adds buttons or other actions on forms for user interaction.
- **Example**: A "Submit Request" button that triggers the workflow.

### 3. UI Policies
- **Purpose**: Enforces rules on forms, such as making fields visible or read-only based on conditions.
- **Example**: For high-value items, additional approval fields are required.

### 4. Business Rules
- **Purpose**: Server-side automation for data processing.
- **Example**: Automatically update the status of a request to "Pending Approval" when it's submitted.

### 5. Flow Designer
- **Purpose**: Automates workflows for processes like approval, assignment, and notifications.
- **Example**: A flow that routes loan requests through multiple approval stages based on the value of the item.

---

## Screenshots and Walkthrough

### 1. Loan Request Form (Self-Service View)
- **Description**: Users can fill in this form to request loaner items. Fields such as item type, loan period, and reason are required.
- ![Loan Request Form](./screenshots/loan-request-form.png)

### 2. Admin View
- **Description**: Administrators can approve or reject requests, view the history of requests, and manage inventory.
- ![Admin Dashboard](./screenshots/admin-dashboard.png)

### 3. Flow Designer Overview
- **Description**: This visual shows how requests are processed from submission to approval.
- ![Flow Designer Overview](./screenshots/flow-designer-overview.png)

### 4. Request Status Tracking
- **Description**: Users can view the current status of their request in real-time.
- ![Request Status Tracking](./screenshots/request-status.png)

---

## Project Sketch

Here's a high-level overview of how the Loaner Request Application is structured:

