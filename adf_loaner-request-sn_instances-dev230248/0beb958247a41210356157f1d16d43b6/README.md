# Loaner Request Application

A **ServiceNow-based application** designed to automate the process of requesting, approving, and tracking loaner items such as laptops, projectors, or other assets. The application offers a seamless self-service experience, complete with approval workflows, inventory management, and real-time tracking.

## Table of Contents
- [Advantages](#advantages)
- [Technologies Used](#technologies-used)
- [ServiceNow Studio and Tools](#servicenow-studio-and-tools)
- [Publishing to GitLab](#publishing-to-gitlab)
- [Features and Concepts](#features-and-concepts)
  - [Form Designing](#form-designing)
  - [Client Scripts](#1-client-scripts)
  - [UI Actions](#2-ui-actions)
  - [UI Policies](#3-ui-policies)
  - [Business Rules](#4-business-rules)
  - [Flow Designer](#5-flow-designer)
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
- **Flow Designer**: Handles the complete approval and order processing workflow. It visualizes the different stages a loan request goes through, from submission to approval, and finally to completion. Each stage is managed through automated actions to ensure the loaner request is processed efficiently.

---

## Technologies Used

- **ServiceNow**: Core platform to develop the application.
- **JavaScript**: For both client-side and server-side scripting.
- **Flow Designer**: For creating custom approval workflows.
- **UI Policies, Client Scripts**: To manage dynamic form behaviors.
- **Business Rules**: Essential for executing server-side logic and ensuring automated processing of loaner requests.
- **GitLab**: Source control for tracking code changes and collaborative development.
- **Glide API**: For querying and manipulating records.

---

## ServiceNow Studio and Tools

- **ServiceNow Studio**: This is where the application was built, managed, and extended. The platform’s core features, like **Client Scripts**, **Business Rules**, and **UI Actions**, were leveraged to ensure smooth functionality.
  
  - **Client Scripts**: JavaScript that runs in the browser, used to control field validation and behavior.
  - **UI Actions**: Custom buttons for form actions (e.g., submit, approve).
  - **UI Policies**: Manage field behavior, such as making fields required or visible under certain conditions.
  - **Business Rules**: Automates back-end processes, ensuring that data is processed correctly.
  - **Flow Designer**: A visual tool to create workflows, handling the routing and approval processes for requests.
  
  -![studio overview](adf_loaner-request-sn_instances-dev230248\0beb958247a41210356157f1d16d43b6\screenshots\studio1.png)
  -![studio overview](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/studio1.png)
---

## Publishing to GitLab

1. **Linking Source Control**:
   - Navigate to **Studio** > **Source Control** > **Link to Source Control**.
   - ![credentials](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/credentials.png)
   - Link GitLab to ServiceNow Studio.
   - ![linking](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/linking%20to%20source.png)
   - Enter your GitLab repository URL and credentials.
   - Select the branch (e.g., main) and commit the changes.
   - ![commits](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/commiting%20files%20to%20gitlab.png)
   - After successful commit.
   - ![succesfull commit](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/comitt%20success.png)

2. **Commit and Push**:
   - Once linked, any changes made in the ServiceNow Studio, such as updates to Client Scripts, UI Actions, or Business Rules, can be committed to GitLab.
   - Collaborators can merge code from different branches and continue developing on separate features.
   - The overview of the source after some files are pushed to a specific branch is like:
   - ![look](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/look.png)

---

## Features and Concepts

### Form Designing

The loan request application features distinct forms for users and admins to streamline the request process.

#### Loan Request Form
- **User Info**: Auto-filled details like name and department.
- **Loaner Item**: Dropdown to select the requested item.
- **Duration**: Start and end dates for the request.
- **Purpose**: Text field for additional information.
- **Submit**: Button to send the request for approval.

#### Admin/Approver View
- **Request Details**: User-submitted information.
- **Approval Status**: Approve, reject, or hold options.
- **Assigned Location**: Auto-filled based on business rules.
- **Inventory Check**: Verify item availability.
- **Fulfillment**: Mark request as completed or in progress.

#### Self-Service View
- **Request Status**: Track approval progress.
- **Loaner Details**: View assigned items and location.
- **Notifications**: Get updates on request status.

### Form Visuals:
- ![Loan Request Form](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/request%20form.png)
- ![Self-Service View](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/self%20view.png)

### 1. Client Scripts
- **Purpose**: To control the form behavior and validate user input.
- **Example**: If the user selects the configuration item **Lenovo**, the "item type" field becomes **LAPTOP**. Conversely, for other items, the type field changes accordingly.
- ![client code](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/client%20code.png)
- ![client script](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/client%20script(phones).png)

### 2. UI Actions
- **Purpose**: Adds buttons or other actions on forms for user interaction.
- **Example**: A **Submit Request** button that triggers the workflow.

### 3. UI Policies
- **Purpose**: Enforces rules on forms, such as making fields visible or read-only based on conditions.
- **Example**: For the **depot** field, if "other" is selected, the "other" field becomes mandatory.
- ![ui policy](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/ui%20policy.png)

### 4. Business Rules
- **Purpose**: Server-side automation for data processing.
- **Example**: Automatically update the city and country of the requested user when the data is submitted.
- ![Business rule](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/br.png)

### 5. Flow Designer
- **Purpose**: Automates workflows for processes like approval, creating tasks, waiting for location, before deployment, post-deployment, and closure.
- **Example**: A flow that routes loan requests through multiple approval stages based on the value of the item.
- ![flow](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/flow1.png)
- ![flow view](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/flow%20view.png)
- Before the trigger starts:
  - Trigger for a flow looks like:
  - In this app, I have used the trigger condition as the **laptop state is reserved**.
  - ![trigger](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/flow%20trigger.png)

---

## Project Sketch

Here’s a visual representation of the application’s workflow:

![Project Sketch](adf_loaner-request-sn_instances-dev230248/0beb958247a41210356157f1d16d43b6/screenshots/sketch.png)

---

## Contributing

If you would like to contribute to this project, please fork the repository and submit a pull request with your proposed changes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For any questions or feedback, please contact [your.email@example.com](mailto:your.email@example.com).
