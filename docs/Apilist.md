## API's

## AuthRoute

#### 1. Create new user

```
POST  /v1/auth/register
```

Registers a new user in the system.

#### 2. Login

```
POST /v1/auth/login
```

Authenticates a user and generates an access token.

#### 3. Logout

```
POST /v1/auth/logout
```

Logs out the user and invalidates their current session.

#### 4. Refresh Token

```
POST /v1/auth/refresh-tokens
```

Generates a new access token using a valid refresh token.

#### 5. Forgot Password

```
POST /v1/auth/forgot-password
```

Sends a password reset link to the user's registered email address.

#### 6. Reset Password

```
POST /v1/auth/reset-password
```

Resets the user's password using the provided token.

#### 7. Reset Password Request

```
POST /v1/auth/reset-password-request
```

Requests a password reset for the user's account.

#### 8. Request Password

```
POST /v1/auth/request-password
```

Initiates a process to retrieve or reset the user's password.

#### 9. Send verification email

```
POST /v1/auth/send-verification-email
```

Sends an email to verify the user's email address.

#### 10. Verify email

```
POST /v1/auth/verify-email
```

Verifies the user's email address using the provided token.

---

## AccessRoute

#### 1. Get side menu

```
GET /v1/access/sideMenu
```

Fetches the side menu structure based on the user's role

#### 2. Change Account

```
POST /v1/access/change-account
```

Changes the user's role or account and regenerates the JWT token.

---

## Agents

#### 1. Create Agent

```
POST /v1/agents/
```

Creates a new agent in the database.

#### 2. Get Agents

```
GET /v1/agents/
```

Fetches a list of all agents.

#### 3. Get All Agents

```
GET /v1/agents/all
```

Fetches all agents, including their detailed information.

#### 4. Agent Heartbeat

```
GET /v1/agents/heartBeat/:agentId
```

Checks the heartbeat status of a specific agent.

#### 5. Get Agents by Site

```
GET /v1/agents/site/:siteRef
```

Fetches agents associated with a specific site.

#### 6. Get Agent

```
GET /v1/agents/:agentId
```

Retrieves detailed information about a specific agent.

#### 7. Update Agent

```
PATCH /v1/agents/:agentId
```

Updates information about a specific agent.

#### 8. Delete Agent

```
DELETE /v1/agents/:agentId
```

Deletes a specific agent.

#### 9. Agent Onboarding

```
GET /v1/agents/borg/:obKey
```

Fetches onboarding details for an agent using an onboarding key.

#### 10. Agent Info

```
GET /v1/agents/getInfo/:agentId
```

Retrieves information about a specific agent.

#### 11. Agent Poll

```
GET /v1/agents/agentPoll/:agentId
```

Initiates a poll request for a specific agent.

#### 12. Start Agent Poll

```
GET /v1/agents/agentPollStart/:agentId
```

Starts the polling process for a specific agent.

#### 13. Stop Agent Poll

```
GET /v1/agents/agentPollStop/:agentId
```

Stops the polling process for a specific agent.

#### 14. Start ML Engine

```
GET /v1/agents/agentStartMLEngine/:agentId
```

Starts the machine learning engine for a specific agent.

#### 15. Stop ML Engine

```
GET /v1/agents/agentStopMLEngine/:agentId
```

Stops the machine learning engine for a specific agent.

#### 16. Agent Stats

```
GET /v1/agents/agentStats/:agentId
```

Fetches statistics for a specific agent.

#### 17. Agent Info

```
GET /v1/agents/agentInfo/:agentId
```

Retrieves information about a specific agent.

#### 18. Get Agent Networks

```
GET /v1/agents/getAgentNetworks/:agentId
```

Fetches the network configuration of a specific agent.

#### 19. Discover Cameras (Username and Password)

```
GET /v1/agents/discover/:agentId/:username/:password
```

Discovers cameras using a username and password.

#### 20. Discover Cameras (Network Interface)

```
GET /v1/agents/discover/:agentId/:networkInterface
```

Discovers cameras using a network interface.

---

## AgentsHistory

#### 1. Get Agents History

```
GET /v1/agentHistory/
```

Fetches the history of all agents.

#### 2. Get Agent History

```
GET /v1/agentHistory/:agentHistoryId
```

Retrieves the history of a specific agent.

#### 3. Delete Agent History

```
DELETE /v1/agentHistory/:agentHistoryId
```

Deletes the history of a specific agent.

---

## Cameras

#### 1.Create Camera

```
POST /v1/cameras/
```

Creates a new camera.

#### 2.Get Cameras

```
GET /v1/cameras/
```

Fetches a list of all cameras.

#### 3. Capture Camera

```
GET /v1/cameras/capture/:cameraId
```

Captures an image from a specific camera.

#### 4.Create Camera by Site

```
POST /v1/cameras/site
```

Creates a camera associated with a specific site.

#### 5. Create Camera by Site URL

```
POST /v1/cameras/site/url
```

Creates a camera using a site URL.

#### 6.Get Camera

```
GET /v1/cameras/:cameraId
```

Fetches details of a specific camera.

#### 7.Update Camera

```
PUT /v1/cameras/:cameraId
```

Updates the information of a specific camera.

#### 8.Delete Camera

```
DELETE /v1/cameras/:cameraId
```

Deletes a specific camera.

#### 9.Update Camera with URL

```
PUT /v1/cameras/url/:cameraId
```

Updates camera details using a URL.

---

## EventRoute

#### 1.Create Event

```
POST /v1/events/
```

Creates a new event in the system.

#### 2.Get Event by Detector

```
POST /v1/events/:siteRef/:agentRef/:detectorRef
```

Retrieves events associated with a specific site, agent, and detector.

#### 3.Get Event Logs by Time and Group

```
GET /v1/events/aggregate
```

Fetches event logs grouped by time.

#### 4. Get Event

```
GET /v1/events/:eventId
```

Retrieves details of a specific event by its ID.

#### 5.Update Event

```
PATCH /v1/events/:eventId
```

Updates the details of a specific event.

#### 6.Delete Event

```
DELETE /v1/events/:eventId
```

Deletes a specific event by its ID.

#### 7.Get Dashboard Alert

```
POST /v1/events/dashboard/alert
```

Fetches dashboard alerts for events.

#### 8. Acknowledge Event

```
PATCH /v1/events/acknowledge/:eventId
```

Acknowledges a specific event.

---

## ScheduleRoute

#### 1. Create Schedule

```
POST /v1/schedules/
```

Creates a new schedule in the system.

#### 2. Get Schedules

```
GET /v1/schedules/
```

Retrieves all schedules.

#### 3.Get Detector Configuration by Agent

```
GET /v1/schedules/getDetectorConfigByAgent
```

Fetches detector configuration associated with a specific agent.

#### 4.Push Schedule

```
POST /v1/schedules/pushSchedule/:agentId
```

Pushes a schedule to the specified agent.

#### 5.Get Schedule

```
GET /v1/schedules/:scheduleId
```

Retrieves details of a specific schedule by its ID.

#### 6.Update Schedule

```
PATCH /v1/schedules/:scheduleId
```

Updates the details of a specific schedule.

#### 7.Delete Schedule

```
DELETE /v1/schedules/:scheduleId
```

Deletes a specific schedule by its ID.

---

## DataLakeRoute

#### 1.Get Data Lakes

```
GET /v1/dataLakes/
```

Retrieves all available data lakes.

---

## BusinessAccountRoute

#### 1.Create Business Account

```
POST /v1/businessAccounts/
```

Creates a new business account in the system.

#### 2. Get Business Accounts

```
GET /v1/businessAccounts/
```

Retrieves all business accounts.

#### 3.Get All Business Switches

```
GET /v1/businessAccounts/AllBusiness
```

Retrieves all business switches.

#### 4.Get Business Accounts by Type

```
GET /v1/businessAccounts/business-type/:typeNo
```

Fetches business accounts based on a specific type.

#### 5.Get and Assign Business Accounts

```
GET /v1/businessAccounts/assign
PATCH /v1/businessAccounts/assign
```

Retrieves and assigns business accounts.

#### 6.Get New Navbar List

```
GET /v1/businessAccounts/navbar
```

Fetches a new navbar list for business accounts.

#### 7. Get Business Account

```
GET /v1/businessAccounts/:businessAccountId
```

Retrieves details of a specific business account by its ID.

#### 8.Update Business Account

```
PATCH /v1/businessAccounts/:businessAccountId
```

Updates a specific business account by its ID.

#### 9.Delete Business Account

```
DELETE /v1/businessAccounts/:businessAccountId
```

Deletes a specific business account by its ID.

---

## UserRoute

#### 1.Create User

```
POST /v1/users/
```

Creates a new user in the system.

#### 2.Get Users

```
GET /v1/users/
```

Retrieves all users.

#### 3.Create Super Admin

```
POST /v1/users/create-super-admin/
```

Creates a super admin user.

#### 4.Upload User Avatar

```
PUT /v1/users/upload-avatar/:userId
```

Uploads an avatar for a specific user

#### 5.Reset User Password

```
POST /v1/users/reset-password/:userId
```

Resets the password for a specific user.

#### 6. Get User

```
GET /v1/users/:userId
```

Retrieves details of a specific user by their ID.

#### 7.Update User

```
PUT /v1/users/:userId
```

Updates details of a specific user.

#### 8.Delete User

```
DELETE /v1/users/:userId
```

Deletes a specific user by their ID.

---

## RoleRoute

#### 1.Get Roles

```
GET /v1/roles/
```

Retrieves all roles.

#### 2.Get Business Roles

```
GET /v1/roles/business
```

Fetches roles associated with businesses.

#### 3.Get All Roles with Users

```
GET /v1/roles/role-user
```

Retrieves all roles with their associated users.

#### 4.Get All Users Grouped by Roles

```
GET /v1/roles/user-groupby-roles
```

Fetches all users grouped by their roles.

#### 5.Get Current Role

```
GET /v1/roles/current-role
```

Retrieves the current role of the authenticated user.

#### 6.Assign Super Admin Role

```
PUT /v1/roles/assign-super-admin/:userId
```

Assigns the Super Admin role to a specific user by their ID.

#### 7. Get Role by ID

```
GET /v1/roles/:roleId
```

Retrieves details of a specific role using its unique ID.

#### 8.Update Role

```
PATCH /v1/roles/:roleId
```

Updates the details of an existing role using its ID.

#### 9.Delete Role

```
DELETE /v1/roles/:roleId
```

Deletes a role from the system using its unique ID.

---

## RoiRoute

#### 1.Create ROI

```
POST /v1/rois/
```

Creates a new Region of Interest (ROI) in the system.

#### 2.Get ROIs

```
GET /v1/rois/
```

Retrieves all ROIs available in the system.

#### 3.Create ROI with Detector Reference

```
POST /v1/rois/detectorRef/:detectorRef/:agentRef
```

Creates a new ROI and links it to a specific detector and agent.

#### 4.Update ROI

```
PATCH /v1/rois/:roiId/:agentRef
```

Updates a specific ROI linked to an agent by its ID.

#### 5.Delete ROI

```
DELETE /v1/rois/:roiId/:detectorRef/:agentRef
```

Deletes a specific ROI using its ID, detector reference, and agent reference.

#### 6.Get ROI by ID

```
GET /v1/rois/:roiId
```

Retrieves details of a specific ROI by its unique ID.

#### 7.Update ROI by ID

```
PATCH /v1/rois/:roiId
```

Updates the details of a specific ROI by its ID.

---

## DetectorDefRoute

#### 1.Get Detector Definitions

```
GET /v1/detectorDefs/
```

Retrieves a list of all available detector definitions.

#### 2.Get Specific Detector Definition

```
GET /v1/detectorDefs/:detectorDefId
```

Retrieves details of a specific detector definition by its ID.

---

## DetectorConfigRoute

#### 1. Create Detector Config

```
POST /v1/detectorConfigs/
```

Creates a new detector configuration in the system.

#### 2. Get Detector Configurations

```
GET /v1/detectorConfigs/
```

Retrieves a list of all detector configurations.

#### 3. Get Detectors by ROI References

```
GET /v1/detectorConfigs/byRois
```

Fetches detectors associated with specific ROI references.

#### 4.Push Detector Config

```
POST /v1/detectorConfigs/pushConf/:agentId
```

Pushes the detector configuration to a specified agent.

#### 5.Get Detectors Without Schedule

```
GET /v1/detectorConfigs/listDectector/:agentId
```

Lists detectors associated with a specific agent that do not have schedules.

#### 6. Get Detector Config by ID

```
GET /v1/detectorConfigs/:detectorConfigId
```

Retrieves details of a specific detector configuration by its ID.

#### 7.Update Detector Config

```
PATCH /v1/detectorConfigs/:detectorConfigId
```

Updates the details of a specific detector configuration by its ID.

#### 8. Delete Detector Config

```
DELETE /v1/detectorConfigs/:detectorConfigId
```

Deletes a specific detector configuration by its ID.

#### 9.Get Detector Config by Camera Reference

```
GET /v1/detectorConfigs/cameraRef/:cameraRef
```

Retrieves detector configurations linked to a specific camera reference.

---

## SiteRoute

#### 1. Create a Site and Agent

```
POST /v1/sites
```

Creates a new site and agent in the database.

Additional operations:

- Creates Pub/Sub topic and subscription using agent ID.

- Creates GCP Cloud Storage folders (`images`, `videos`, `discover`, `logs`).

- Saves GCP service key and unique UUID (agent access key) to the agent model.

#### 2. Fetch All Sites for a Business

```
GET /v1/sites
```

Retrieves all sites for a business.

#### 3. Create Multiple Sites

```
POST /v1/sites/siteByBusiness
```

Creates multiple sites, each with a corresponding agent in the database.

#### 4. Fetch Site Details by ID

```
GET /v1/sites/{siteId}
```

Retrieves details for a specific site by its ID.

#### 5. Update Site Details

```
PATCH /v1/sites/{siteId}
```

Updates site details.

#### 6. Delete a Site

```
DELETE /v1/sites/{siteId}
```

Deletes a site and associated components from the database.

Additional operations:

- Deletes Pub/Sub subscription and topic of the agent.

- Deletes associated folders and files from GCP storage.

---

## AgentOpRoute

#### 1.Create Operation Request

```
POST /v1/agentOps/:agentId/:opId
```

---

## DashboardRoute

#### 1. Create a Business Account

```
POST /v1/businessAccounts
```

Creates a new business, user, and optionally a site in the database.

#### 2. Fetch All Businesses or Specific Business Details

```
GET /v1/businessAccounts
```

Retrieves all businesses or details for a specific business by business name.

#### 3. Fetch All Businesses for Admin Dropdown

```
GET /v1/businessAccounts/AllBusiness
```

Retrieves a list of all businesses for admin sidebar's "Switch Business" dropdown.

#### 4. Fetch Businesses by Type

```
GET /v1/businessAccounts/business-type/{type}
```

Retrieves a list of businesses filtered by type (e.g., `partner` or `customer`).

#### 5. Fetch Assignable Customers

```
GET /v1/businessAccounts/assign
```

Fetches a list of customers that can be assigned by an admin to a partner.

#### 6. Assign Business to Partner

```
PATCH /v1/businessAccounts/assign
```

Assigns a business to a partner.

#### 7. Fetch All Businesses Except Current

```
GET /v1/businessAccounts/navbar
```

Retrieves a list of all businesses except the current one.

**Note**: This API is currently not in use.

#### 8. Fetch Business Details by ID

```
GET /v1/businessAccounts/{businessAccountId}
```

Retrieves details for a specific business account by its ID.

#### 9. Update Business Account

```
PATCH /v1/businessAccounts/{businessAccountId}
```

Updates business account details, such as business name, email, etc.

#### 10. Delete Business Account

```
DELETE /v1/businessAccounts/{businessAccountId}
```

Deletes a business account from the database.

---

## PusherRoute

#### 1.Authenticate User

```
GET /v1/user-auth
```

Authenticates a user via a GET request.

#### 2.Authenticate User (POST)

```
POST /v1/user-auth
```

Authenticates a user via a POST request.

#### 3.Authorize User

```
POST /v1/auth
```

Authorizes a user for access to specific resources or actions.

---

## NotificationRoute

#### 1.Get Notification List

```
GET /v1/notifications/
```

Retrieves a list of all notifications for the user.

#### 2.Create Notification (Development/Testing Only)

```
POST /v1/notifications/
```

Creates a new notification for development or testing purposes.

#### 3. Acknowledge Notification

```
PUT /v1/notifications/
```

Marks a notification as acknowledged.

#### 4.Get Notification by ID

```
GET /v1/notifications/:notifId
```

Fetches details of a specific notification by its ID.

---

## LookupRoute

#### 1.. Get All Constants

```
GET /v1/constants/all
```

Retrieves all constant values defined in the system.

---

## DiscoverCameraRoute

#### 1.Start Camera Discovery

```
POST /v1/cameraDiscover/:agentRef
```

Initiates the discovery of cameras for the specified agent.

#### 2.Get Camera Discovery List

```
GET /v1/cameraDiscover/:siteRef/:agentRef
```

Retrieves a list of discovered cameras for the specified site and agent.

---

## PlanRoute

#### 1.Get Plan Details

```
GET /v1/plan/
```

Fetches details of the current plan or subscription.

---

## CollaborationRoute

#### 1.Get Collaboration Details

```
GET /v1/collaboration/
```

Retrieves details related to collaboration activities or settings.

---
