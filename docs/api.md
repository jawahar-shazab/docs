## API's

## AuthRoute

#### 1. Create new user

```
POST  /v1/auth/register
```

This API allows new users to register by providing essential details such as their name, email address, and password. Upon successful registration, a new user account is created.

#### 2. Login

```
POST /v1/auth/login
```

This API authenticates a user by verifying their credentials (email and password). Upon successful login, the system generates and returns an access token, and optionally a refresh token, for ongoing access.

#### 3. Logout

```
POST /v1/auth/logout
```

This API logs out an authenticated user by invalidating their current session and associated tokens. After logging out, the user must log in again to regain access to the system.

#### 4. Refresh Token

```
POST /v1/auth/refresh-tokens
```

This API generates a new access token when the current one expires. A valid refresh token is required to access this API, enabling users to maintain their sessions without the need for repeated logins.

#### 5. Forgot Password

```
POST /v1/auth/forgot-password
```

This API initiates the password recovery process by sending a password reset link to the email address associated with the user account. Users can use this link to securely reset their password.

#### 6. Reset Password

```
POST /v1/auth/reset-password
```

This API allows a user to set a new password for their account by providing a valid reset token (usually received via email) and the new password. This process ensures the account's security during password updates.

#### 7. Reset Password Request

```
POST /v1/auth/reset-password-request
```

This API enables users to request a password reset by submitting their registered email address. The system generates a password reset token and sends it to the provided email for further action.

#### 8. Request Password

```
POST /v1/auth/request-password
```

This API initiates the password retrieval or reset process. Similar to the reset-password-request API, the user provides their registered email address to receive further instructions on resetting or recovering their password.

#### 9. Send verification email

```
POST /v1/auth/send-verification-email
```

This API sends a verification email to the user's registered email address. The email contains a token or link that the user can use to verify their email address, ensuring its authenticity.

#### 10. Verify email

```
POST /v1/auth/verify-email
```

This API verifies the user's email address by validating the token provided in the verification link sent to their email. Successful verification confirms the email's legitimacy and activates the user's account for full access.

---

## AccessRoute

#### 1. Get side menu

```
GET /v1/access/sideMenu
```

This API retrieves the structure and content of the side menu tailored to the user's role and permissions. The side menu dynamically adjusts based on the user's access level, ensuring that only relevant and authorized sections of the application are visible.

#### 2. Change Account

```
POST /v1/access/change-account
```

This API allows a user to switch between accounts or roles (if multiple roles or accounts are associated with their profile). Upon changing the account or role, a new JWT token is generated to reflect the updated permissions and access rights, ensuring secure access to the appropriate resources.

---

## Agents

#### 1. Create Agent

```
POST /v1/agents/
```

This API is used to create a new agent in the system. Users provide necessary details (e.g., name, type, and configuration) to register the agent in the database, enabling it to perform its assigned tasks within the system.

#### 2. Get Agents

```
GET /v1/agents/
```

This API retrieves a list of all agents currently registered in the system. The response includes basic information for each agent, such as their ID and status.

#### 3. Get All Agents

```
GET /v1/agents/all
```

This API returns detailed information about all agents, including their configurations, statuses, and other key details. It provides a comprehensive view of all agents in the system.

#### 4. Agent Heartbeat

```
GET /v1/agents/heartBeat/:agentId
```

This API checks the heartbeat status of a specific agent, indicating whether the agent is online and active. It helps monitor the agent's availability in real time.

#### 5. Get Agents by Site

```
GET /v1/agents/site/:siteRef
```

This API fetches a list of agents associated with a specific site, identified by the `siteRef`. It is useful for site-specific management and monitoring of agents.

#### 6. Get Agent

```
GET /v1/agents/:agentId
```

This API retrieves detailed information about a specific agent, identified by the `agentId`. It provides insights into the agent's configuration, status, and other parameters.

#### 7. Update Agent

```
PATCH /v1/agents/:agentId
```

This API allows you to update the details of a specific agent, identified by the `agentId`. It can be used to modify agent configurations, update status, or change other parameters.

#### 8. Delete Agent

```
DELETE /v1/agents/:agentId
```

This API deletes a specific agent from the system, identified by the `agentId`. Deleting an agent removes it from monitoring and all associated data, so it should be used with caution.

#### 9. Agent Onboarding

```
GET /v1/agents/borg/:obKey
```

This API fetches onboarding details for an agent using the provided onboarding key (`obKey`). It assists in initiating the agent's registration and setup process in the system.

#### 10. Agent Info

```
GET /v1/agents/getInfo/:agentId
```

This API retrieves specific information about an agent, identified by the `agentId`. The data may include various operational and configuration details.

#### 11. Agent Poll

```
GET /v1/agents/agentPoll/:agentId
```

This API initiates a poll request for a specific agent, identified by `agentId`. It allows the system to query or collect data from the agent on demand.

#### 12. Start Agent Poll

```
GET /v1/agents/agentPollStart/:agentId
```

Starts the polling process for a specific agent, enabling the system to regularly fetch updates from the agent.

#### 13. Stop Agent Poll

```
GET /v1/agents/agentPollStop/:agentId
```

Stops the ongoing polling process for a specific agent, halting the regular data retrieval from the agent.

#### 14. Start ML Engine

```
GET /v1/agents/agentStartMLEngine/:agentId
```

Starts the machine learning engine for a specific agent, enabling it to process data and perform machine learning-based tasks.

#### 15. Stop ML Engine

```
GET /v1/agents/agentStopMLEngine/:agentId
```

Stops the machine learning engine for a specific agent, pausing machine learning-based processing tasks.

#### 16. Agent Stats

```
GET /v1/agents/agentStats/:agentId
```

This API fetches statistics related to a specific agent, including performance metrics, operational data, and other relevant information for monitoring purposes.

#### 17. Agent Info

```
GET /v1/agents/agentInfo/:agentId
```

This API retrieves detailed information about a specific agent, identified by the `agentId`. It provides insights into the agent's status, configuration, and other important details.

#### 18. Get Agent Networks

```
GET /v1/agents/getAgentNetworks/:agentId
```

This API fetches the network configuration details of a specific agent, identified by the `agentId`. It includes information such as IP addresses, network interfaces, and other connectivity data.

#### 19. Discover Cameras (Username and Password)

```
GET /v1/agents/discover/:agentId/:username/:password
```

This API discovers cameras accessible to a specific agent using the provided `username` and `password` for authentication. It helps identify and register devices within the agent's scope.

#### 20. Discover Cameras (Network Interface)

```
GET /v1/agents/discover/:agentId/:networkInterface
```

This API discovers cameras connected to a specific network interface of an agent. It uses the network interface as a discovery parameter instead of credentials.

---

## AgentsHistory

#### 1. Get Agents History

```
GET /v1/agentHistory/
```

This API retrieves the historical records of all agents. It provides a comprehensive log of activities, updates, and events associated with each agent in the system, making it useful for monitoring and troubleshooting purposes.

#### 2. Get Agent History

```
GET /v1/agentHistory/:agentHistoryId
```

This API fetches the history of a specific agent, identified by `agentHistoryId`. It details all recorded actions, updates, and events for the particular agent, providing insights into its operational timeline.

#### 3. Delete Agent History

```
DELETE /v1/agentHistory/:agentHistoryId
```

This API deletes the historical records of a specific agent, identified by `agentHistoryId`. Use this with caution, as it permanently removes logs associated with the agent, potentially impacting monitoring and troubleshooting.

---

## Cameras

#### 1.Create Camera

```
POST /v1/cameras/
```

This API creates a new camera in the system. You can specify the necessary details, such as the camera's name, location, and configuration parameters, to register it for monitoring and management.

#### 2.Get Cameras

```
GET /v1/cameras/
```

This API retrieves a list of all cameras registered in the system. It provides an overview of all available cameras, including their basic details, for monitoring and administrative purposes.

#### 3. Capture Camera

```
GET /v1/cameras/capture/:cameraId
```

This API captures an image from a specific camera, identified by `cameraId`. It is used to retrieve a snapshot for live monitoring or analysis purposes.

#### 4.Create Camera by Site

```
POST /v1/cameras/site
```

This API allows you to create a camera and associate it with a specific site. It helps organize cameras based on their physical or logical locations within the system.

#### 5. Create Camera by Site URL

```
POST /v1/cameras/site/url
```

This API creates a camera using a site URL. It is useful for scenarios where cameras need to be added programmatically based on their network or site configuration.

#### 6.Get Camera

```
GET /v1/cameras/:cameraId
```

This API retrieves detailed information about a specific camera, identified by `cameraId`. It includes configuration settings, status, and other relevant details.

#### 7.Update Camera

```
PUT /v1/cameras/:cameraId
```

This API updates the information of a specific camera. You can modify attributes such as the name, location, or configuration parameters for the camera, identified by cameraId.

#### 8.Delete Camera

```
DELETE /v1/cameras/:cameraId
```

This API deletes a specific camera from the system, identified by `cameraId`. Use this to remove cameras that are no longer needed or operational.

#### 9.Update Camera with URL

```
PUT /v1/cameras/url/:cameraId
```

This API updates the details of a specific camera using a URL. It is helpful for scenarios where camera configuration or location changes can be defined through URLs, streamlining the update process.

---

## EventRoute

#### 1.Create Event

```
POST /v1/events/
```

This API creates a new event in the system. Events can represent various occurrences or detections, such as security alerts, operational logs, or system notifications, and are essential for tracking activities and incidents.

#### 2.Get Event by Detector

```
POST /v1/events/:siteRef/:agentRef/:detectorRef
```

This API retrieves events associated with a specific site, agent, and detector, identified by `siteRef`, `agentRef`, and `detectorRef`. It helps filter events based on their source or origin..

#### 3.Get Event Logs by Time and Group

```
GET /v1/events/aggregate
```

This API fetches event logs grouped by time, allowing for analysis and visualization of events over specific periods. It is useful for generating reports, creating dashboards, or identifying trends in event activity.

#### 4. Get Event

```
GET /v1/events/:eventId
```

This API retrieves detailed information about a specific event, identified by `eventId`. It provides insights into the nature, source, and status of the event for further analysis or resolution.

#### 5.Update Event

```
PATCH /v1/events/:eventId
```

This API updates the details of a specific event. Changes may include updating the event status, modifying metadata, or adjusting other event parameters.

#### 6.Delete Event

```
DELETE /v1/events/:eventId
```

This API deletes a specific event, identified by `eventId`. It is typically used to remove obsolete or resolved events from the system.

#### 7.Get Dashboard Alert

```
POST /v1/events/dashboard/alert
```

This API fetches alerts for the dashboard based on events. These alerts highlight critical or actionable events that require immediate attention from users or administrators.

#### 8. Acknowledge Event

```
PATCH /v1/events/acknowledge/:eventId
```

This API acknowledges a specific event, identified by `eventId`. Acknowledging an event indicates that it has been reviewed or addressed, assisting in managing and tracking the event's resolution status.

---

## ScheduleRoute

#### 1. Create Schedule

```
POST /v1/schedules/
```

This API creates a new schedule in the system. Schedules define time-based configurations or tasks, such as camera monitoring schedules or system checks, ensuring that operations are performed at the appropriate times.

#### 2. Get Schedules

```
GET /v1/schedules/
```

This API retrieves all schedules in the system. It provides a list of configured schedules, including their details, to help users manage and review time-based operations.

#### 3.Get Detector Configuration by Agent

```
GET /v1/schedules/getDetectorConfigByAgent
```

This API fetches the detector configurations associated with a specific agent. It allows users to review and manage detector-related settings for efficient scheduling and execution.

#### 4.Push Schedule

```
POST /v1/schedules/pushSchedule/:agentId
```

This API pushes a schedule to a specified agent, identified by `agentId`. It ensures that the agent operates according to the predefined schedule, such as executing specific tasks or processes at designated times.

#### 5.Get Schedule

```
GET /v1/schedules/:scheduleId
```

This API retrieves details of a specific schedule, identified by `scheduleId`. It provides comprehensive information about the schedule, including its purpose, time settings, and associated resources.

#### 6.Update Schedule

```
PATCH /v1/schedules/:scheduleId
```

This API updates the details of a specific schedule. Modifications can include changing the schedule's timing, associated tasks, or configuration parameters.

#### 7.Delete Schedule

```
DELETE /v1/schedules/:scheduleId
```

This API deletes a specific schedule from the system, identified by `scheduleId`. Use this to remove outdated or unnecessary schedules, helping to keep the system clean and organized.

---

## DataLakeRoute

#### 1.Get Data Lakes

```
GET /v1/dataLakes/
```

This API retrieves a list of all available data lakes in the system. Data lakes are centralized repositories used to store, manage, and analyze large volumes of structured and unstructured data. The response includes details such as data lake names, locations, and configurations, helping users monitor and manage their data storage resources.

---

## BusinessAccountRoute

#### 1.Create Business Account

```
POST /v1/businessAccounts/
```

This API creates a new business account in the system. It is used to register a new entity, enabling access to business-related services and resources.

#### 2. Get Business Accounts

```
GET /v1/businessAccounts/
```

This API retrieves a list of all business accounts in the system. It provides an overview of the registered business accounts, including basic details for management and monitoring purposes.

#### 3.Get All Business Switches

```
GET /v1/businessAccounts/AllBusiness
```

This API fetches all business switches, providing details on the status and configuration of business accounts within the system.

#### 4.Get Business Accounts by Type

```
GET /v1/businessAccounts/business-type/:typeNo
```

This API retrieves business accounts based on a specific type, identified by `typeNo`. It allows for filtering accounts by their classification or purpose, such as different business categories or services.

#### 5.Fetch Assignable Customers

```
GET /v1/businessAccounts/assign
```

This API fetches a list of customers that can be assigned by an admin to a partner. It facilitates the management of customer assignments and business relationships.

#### 6.Assign Business to Partner

```
PATCH /v1/businessAccounts/assign
```

This API assigns a business to a partner. It modifies the business's association within the system, establishing a partnership between the two entities.

#### 7.Get New Navbar List

```
GET /v1/businessAccounts/navbar
```

This API fetches a new navbar list for business accounts. It provides an updated navigation structure for managing business account-related settings and resources.

#### 8. Get Business Account

```
GET /v1/businessAccounts/:businessAccountId
```

This API retrieves detailed information about a specific business account, identified by `businessAccountId`. It provides insights into the account's configuration, resources, and status.

#### 9.Update Business Account

```
PATCH /v1/businessAccounts/:businessAccountId
```

This API updates a specific business account, identified by `businessAccountId`. Modifications may include changes to account settings, contact information, or service configurations.

#### 10.Delete Business Account

```
DELETE /v1/businessAccounts/:businessAccountId
```

This API deletes a specific business account from the system, identified by `businessAccountId`. Use this to remove inactive or unnecessary business accounts from the system.

---

## UserRoute

#### 1.Create User

```
POST /v1/users/
```

This API creates a new user in the system. It registers a user with the provided details, enabling access to the platform and associated services.

#### 2.Get Users

```
GET /v1/users/
```

This API retrieves a list of all users in the system. It provides an overview of registered users, including basic details like names, roles, and statuses.

#### 3.Create Super Admin

```
POST /v1/users/create-super-admin/
```

This API creates a super admin user with elevated privileges. Super admins typically have the highest level of access and can manage system-wide settings, including other users.

#### 4.Upload User Avatar

```
PUT /v1/users/upload-avatar/:userId
```

This API uploads an avatar for a specific user, identified by `userId`. The avatar can be used for user profiles or personalized visuals in the system.

#### 5.Reset User Password

```
POST /v1/users/reset-password/:userId
```

This API resets the password for a specific user, identified by `userId`. It allows for restoring access in case of forgotten passwords or security breaches.

#### 6. Get User

```
GET /v1/users/:userId
```

This API retrieves detailed information about a specific user, identified by `userId`. It includes data such as the user's name, email, role, and other profile information.

#### 7.Update User

```
PUT /v1/users/:userId
```

This API updates the details of a specific user, identified by `userId`. Updates may include changes to the user's name, email, role, or other profile information.

#### 8.Delete User

```
DELETE /v1/users/:userId
```

This API deletes a specific user from the system, identified by `userId`. Use this to remove inactive or unnecessary users from the platform.

---

## RoleRoute

#### 1.Get Roles

```
GET /v1/roles/
```

This API retrieves a list of all roles in the system. It provides a comprehensive view of all the different roles available, which may be associated with varying levels of permissions and responsibilities within the platform.

#### 2.Get Business Roles

```
GET /v1/roles/business
```

This API fetches roles specifically associated with business entities. These roles may include permissions and capabilities relevant to business management and operations.

#### 3.Get All Roles with Users

```
GET /v1/roles/role-user
```

This API retrieves all roles along with their associated users. It helps in understanding which users are assigned to which roles, making role management more transparent and organized.

#### 4.Get All Users Grouped by Roles

```
GET /v1/roles/user-groupby-roles
```

This api fetches all users, grouped by their assigned roles. It allows for quick visualization of the user distribution across different roles in the system.

#### 5.Get Current Role

```
GET /v1/roles/current-role
```

This API retrieves the current role of the authenticated user. It provides information about the user's active role and associated permissions in the system.

#### 6.Assign Super Admin Role

```
PUT /v1/roles/assign-super-admin/:userId
```

This API assigns the Super Admin role to a specific user, identified by `userId`. Super Admins typically have the highest level of access and control over the system.

#### 7. Get Role by ID

```
GET /v1/roles/:roleId
```

This API retrieves detailed information about a specific role, identified by `roleId`. It provides insights into the permissions, responsibilities, and scope associated with that role.

#### 8.Update Role

```
PATCH /v1/roles/:roleId
```

**Note**: This API is currently commented.

This API updates the details of an existing role using its unique `roleId`. It allows changes to the role’s name, permissions, or other associated attributes.

#### 9.Delete Role

```
DELETE /v1/roles/:roleId
```

**Note**: This API is currently commented.

This API deletes a specific role from the system using its unique `roleId`.

---

## RoiRoute

#### 1.Create ROI

```
POST /v1/rois/
```

This API creates a new Region of Interest (ROI) in the system. An ROI is a specific area within a camera's field of view or monitoring space, which can be used for focused monitoring, analysis, or detection.

#### 2.Get ROIs

```
GET /v1/rois/
```

This API retrieves a list of all ROIs available in the system. It provides an overview of the different regions marked for monitoring or analysis across various cameras or systems.

#### 3.Create ROI with Detector Reference

```
POST /v1/rois/detectorRef/:detectorRef/:agentRef
```

This API creates a new ROI and links it to a specific detector and agent, identified by their `detectorRef` and `agentRef`. This allows for targeting a particular area of interest tied to specific detection systems and agents.

#### 4.Update ROI

```
PATCH /v1/rois/:roiId/:agentRef
```

This API updates a specific ROI, identified by its `roiId`, and links it to a specific agent, identified by `agentRef`. The update can modify aspects such as the ROI's dimensions, coordinates, or other parameters.

#### 5.Delete ROI

```
DELETE /v1/rois/:roiId/:detectorRef/:agentRef
```

This API deletes a specific ROI by its unique `roiId`, along with the associated `detectorRef` and `agentRef`. This is used to remove unnecessary or outdated regions of interest from the system.

#### 6.Get ROI by ID

```
GET /v1/rois/:roiId
```

This API retrieves detailed information about a specific ROI, identified by its unique `roiId`. It provides insights into the dimensions, coordinates, and other relevant data associated with the Region of Interest.

#### 7.Update ROI by ID

```
PATCH /v1/rois/:roiId
```

This API updates the details of a specific ROI, identified by its `roiId`. It allows for modifications to the ROI's attributes, such as its size, position, or other characteristics.

---

## DetectorDefRoute

#### 1.Get Detector Definitions

```
GET /v1/detectorDefs/
```

This API retrieves a list of all available detector definitions in the system. Detector definitions describe the various types of detectors that can be used in the monitoring system, including their characteristics and capabilities.

#### 2.Get Specific Detector Definition

```
GET /v1/detectorDefs/:detectorDefId
```

This API fetches detailed information about a specific detector definition, identified by its `detectorDefId`. It offers a comprehensive overview of the detector's configuration, functionality, and parameters, enabling users to understand its capabilities and integration options within the monitoring system.

---

## DetectorConfigRoute

#### 1. Create Detector Config

```
POST /v1/detectorConfigs/
```

This API creates a new detector configuration in the system. A detector configuration defines how a detector operates and interacts with other system components, such as cameras and agents.

#### 2. Get Detector Configurations

```
GET /v1/detectorConfigs/
```

This API retrieves a list of all detector configurations in the system, offering an overview of the various detector setups defined for different monitoring and detection requirements.

#### 3. Get Detectors by ROI References

```
GET /v1/detectorConfigs/byRois
```

This API retrieves detectors associated with specific ROI (Region of Interest) references, enabling filtering based on the areas of interest they are linked to within the system.

#### 4.Push Detector Config

```
POST /v1/detectorConfigs/pushConf/:agentId
```

This API deploys a detector configuration to a specified agent, identified by its `agentId`, enabling the application of new or updated detector settings to the agent.

#### 5.Get Detectors Without Schedule

```
GET /v1/detectorConfigs/listDectector/:agentId
```

This API retrieves a list of detectors associated with a specific agent, identified by its `agentId`, that currently lack assigned schedules. This helps identify detectors that are ready to be scheduled or configured for monitoring.

#### 6. Get Detector Config by ID

```
GET /v1/detectorConfigs/:detectorConfigId
```

This API retrieves detailed information about a specific detector configuration, identified by its `detectorConfigId`. It provides comprehensive details about the configuration, including its settings and parameters.

#### 7.Update Detector Config

```
PATCH /v1/detectorConfigs/:detectorConfigId
```

This API updates the details of a specific detector configuration identified by its `detectorConfigId`, allowing modifications to the settings or parameters of the configuration.

#### 8. Delete Detector Config

```
DELETE /v1/detectorConfigs/:detectorConfigId
```

This API deletes a specific detector configuration from the system, identified by its `detectorConfigId`, removing it from the system's monitoring and detection setup.

#### 9.Get Detector Config by Camera Reference

```
GET /v1/detectorConfigs/cameraRef/:cameraRef
```

This API retrieves the detector configurations linked to a specific camera reference, identified by its `cameraRef`, enabling the identification of the detector settings associated with that particular camera in the system.

---

## SiteRoute

#### 1. Create a Site and Agent

```
POST /v1/sites
```

This API creates a new site and an associated agent in the database, registering both a physical site and the necessary agent for monitoring or other system tasks.

Additional operations:

- Creating a Pub/Sub topic and subscription using the agent ID.
- Creating GCP Cloud Storage folders (`images`, `videos`, `discover`, `logs`).
- Saving the GCP service key and a unique UUID (agent access key) to the agent model.

#### 2. Fetch All Sites for a Business

```
GET /v1/sites
```

This API retrieves all sites associated with a specific business, providing a list of all locations or establishments under the same business entity.

#### 3. Create Multiple Sites

```
POST /v1/sites/siteByBusiness
```

This API enables the creation of multiple sites, each with its corresponding agent, for a specific business. It facilitates bulk registration of sites and agents for businesses with numerous locations.

#### 4. Fetch Site Details by ID

```
GET /v1/sites/{siteId}
```

This API retrieves detailed information about a specific site, identified by its `siteId`, providing in-depth data on the site's configuration, setup, or current status.

#### 5. Update Site Details

```
PATCH /v1/sites/{siteId}
```

This API updates the details of an existing site, identified by its `siteId`, allowing modifications to the site's configuration or information.

#### 6. Delete a Site

```
DELETE /v1/sites/{siteId}
```

This API deletes a specific site, identified by its `siteId`, and removes all associated components from the database, including the site and its corresponding agent.

Additional operations:

- Deleting the Pub/Sub subscription and topic related to the agent.
- Deleting the associated folders and files from GCP storage.

---

## AgentOpRoute

#### 1.Create Operation Request

```
POST /v1/agentOps/:agentId/:opId
```

This API creates a new operation request for a specific agent, identified by its `agentId`, and associates it with an operation identified by `opId`. This request triggers an operation on the specified agent, which may involve tasks such as configuration changes, updates, or other actions.

---

## DashboardRoute

#### 1.Fetch All Business Count

```
GET /v1/customer
```

This API retrieves the total number of businesses available in the system. The count is displayed on the user dashboard, offering an overview of the scale of businesses managed by the platform. It provides quick insights into the total business volume.

#### 2.Fetch All Business Alerts

```
POST /v1/alert
```

This API fetches a list of alerts related to businesses. These alerts are displayed on the dashboard to notify businesses of important updates or actions required, such as pending tasks, system warnings, or other relevant business-related information.

#### 3.Set Alert Action

```
POST /v1/alert/action
```

This API allows users to set or update actions associated with specific business alerts. For example, users can acknowledge alerts, mark them as resolved, or trigger follow-up actions. This functionality aids in managing and tracking alert-related activities efficiently.

#### 4.Fetch Alerts by Gender

```
POST /v1/alert/gender
```

This API retrieves business alerts filtered by gender-specific data, allowing users to analyze or act upon alerts based on demographic insights, such as male or female engagement metrics. This feature is useful for targeted business operations and decision-making.

#### 5.Fetch Gender-Based Alert Graph

```
POST /v1/alert/gender/graph
```

This API generates graphical data representing gender-specific business alerts. The output can be used for visual analysis, helping users identify trends or patterns in business alerts based on gender demographics.

#### 6.Fetch Business Dashboard Data

```
GET /v1/business
```

This API retrieves comprehensive data for the business dashboard, including metrics, summaries, and insights that assist users in monitoring and managing business performance directly from the dashboard.

#### 7.Fetch Business Plan Dashboard Data

```
GET /v1/business/plan
```

This API retrieves detailed information about business plans, including active subscriptions, plan usage, and related statistics, for display on the user dashboard. It provides insights into the status and performance of business plans.

#### 8.Fetch Business Collaboration Data

```
GET /v1/business/collaboration
```

This API retrieves detailed information about collaboration between businesses, such as partnerships or shared initiatives. The data displayed on the dashboard includes the scope of collaboration, statuses, and related metrics to help users manage inter-business relationships effectively.

---

## PusherRoute

#### 1.Authenticate User

```
GET /v1/user-auth
```

This API authenticates a user via a GET request, typically used for quick authentication without the need to submit sensitive data in the request body.

#### 2.Authenticate User (POST)

```
POST /v1/user-auth
```

This API authenticates a user via a POST request, typically used when the authentication process requires sending sensitive data, such as a username and password, in the request body.

#### 3.Authorize User

```
POST /v1/auth
```

This API authorizes a user for access to specific resources or actions, ensuring that the user has the necessary permissions to perform a particular operation within the system.

---

## NotificationRoute

#### 1.Get Notification List

```
GET /v1/notifications/
```

This API retrieves a list of all notifications for the authenticated user, typically used to display any new or pending notifications within the system, such as alerts or system messages.

#### 2.Create Notification (Development/Testing Only)

```
POST /v1/notifications/
```

This API allows for the creation of a new notification, primarily for development or testing purposes, where users can simulate notifications for testing scenarios. The request body typically includes notification details such as the message content or type.

#### 3. Acknowledge Notification

```
PUT /v1/notifications/
```

This API is used to mark one or more notifications as "acknowledged." Once a user interacts with or views a notification, this API flags it as acknowledged, ensuring that it no longer appears as an active or unread notification in the system.

#### 4.Get Notification by ID

```
GET /v1/notifications/:notifId
```

This API fetches details of a specific notification by its unique ID, allowing the user to view the full content and details, such as the message, timestamp, and any relevant data associated with the notification.

---

## LookupRoute

#### 1.. Get All Constants

```
GET /v1/constants/all
```

This API retrieves all constant values defined within the system. These constants may include system-wide settings, default configurations, or predefined values used across various operations. They are typically not expected to change during runtime and are consistently applied throughout the application.

---

## DiscoverCameraRoute

#### 1.Start Camera Discovery

```
POST /v1/cameraDiscover/:agentRef
```

This API initiates the process of discovering cameras for a specific agent, identified by its `agentRef`. When called, it triggers the system to search for available cameras that can be associated with the specified agent, enabling automatic detection and configuration of cameras within the agent's environment.

#### 2.Get Camera Discovery List

```
GET /v1/cameraDiscover/:siteRef/:agentRef
```

This API retrieves a list of cameras discovered for a particular site (`siteRef`) and agent (`agentRef`). It returns the cameras available for the specified agent at the given site, typically after the discovery process has been initiated. This helps in managing and reviewing the detected cameras.

---

## PlanRoute

#### 1.Get Plan Details

```
GET /v1/plan/
```

This API retrieves the details of the current plan or subscription associated with the user or business. It provides information about the active plan, including available features, limitations, billing cycle, and other plan-specific data. This is useful for checking the subscription status and understanding the features currently accessible.

---

## CollaborationRoute

#### 1.Get Collaboration Details

```
GET /v1/collaboration/
```

This API retrieves details about collaboration settings between partners and customers, including the status, scope, and specific settings of their partnership. It helps manage interactions and coordinate shared resources or activities effectively.

---
