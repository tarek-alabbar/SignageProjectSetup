# 📋 PROJECT MANAGER - Setup Tasks

## Week 1, Day 1 Tasks

### ✅ Task 1: Create Project Email Account

**Create a dedicated Gmail account for this project**

**Steps:**

1. Go to https://accounts.google.com/signup
2. Create account with details:
   - **Email format**: `yourprojectname.team@gmail.com` or `yourcompanyname.dev@gmail.com`
   - **Password**: Use strong password, store in secure location
   - **Recovery email**: Your personal email
   - **Phone**: Add recovery phone number

3. **Enable 2FA** (Two-Factor Authentication):
   - Go to Google Account Settings > Security
   - Enable 2-Step Verification

4. **Document credentials securely**:
   - Store in password manager (LastPass, 1Password, Bitwarden free)
   - Share credentials securely with team (use password manager sharing feature)

5. **Use this email for all project signups**:
   - GitHub organization
   - Azure account
   - Discord
   - Any future services

**📝 Note**: Keep this email credentials accessible to all core team members in case someone is unavailable.

---

### ✅ Task 2: Create GitHub Organization

**Create the GitHub organization that will house all project repositories**

**Steps:**

1. Go to https://github.com/organizations/new
2. Click "Create a free organization"
3. Fill in details:
   - **Organization name**: `yourproject` or `yourcompany` (lowercase, no spaces)
   - **Contact email**: Use the project email you just created
   - **This organization belongs to**: My personal account
4. Choose **"Free"** plan
5. Click "Next"
6. Skip the team member invitation for now (you'll do this in Task 4)
7. Click "Complete setup"

**Verification:**

- You should now have an organization at `https://github.com/yourorg`

---

### ✅ Task 3: Add Team Members to GitHub Organization

**Invite your team members to the GitHub organization**

**Prerequisites:**

- Team members need GitHub accounts (they can create at github.com/signup)

**Steps:**

1. Go to `https://github.com/orgs/yourorg/people`
2. Click "Invite member"
3. Invite Backend Engineer:
   - Enter their GitHub username or email
   - Role: **Owner** (they need full access to set things up)
   - Click "Send invitation"
4. Invite Frontend Engineer:
   - Enter their GitHub username or email
   - Role: **Member**
   - Click "Send invitation"

**Ask team members to:**

- Check their email for GitHub invitation
- Accept invitation
- Confirm they can see the organization

---

### ✅ Task 4: Create Discord Server

**Set up Discord server for team communication**

**Steps:**

1. **Create Discord account** (if you don't have one):
   - Go to https://discord.com
   - Click "Open Discord in your browser" or download app
   - Sign up with project email

2. **Create Server**:
   - Click the "+" button on left sidebar
   - Select "Create My Own"
   - Select "For me and my friends"
   - **Server name**: "YourProject Team" or "YourCompany Dev Team"
   - Upload server icon (optional - use your project logo or skip)
   - Click "Create"

3. **Create Text Channels** (Delete default #general and create these):

   Right-click on "TEXT CHANNELS" header > Create Channel:

   **Channel 1:**
   - Name: `announcements`
   - Description: Important team announcements and updates
   - Make it: Right-click channel > Edit Channel > Permissions > @everyone > Disable "Send Messages"
   - (Only admins can post, everyone can read)

   **Channel 2:**
   - Name: `general`
   - Description: General team chat and casual conversation

   **Channel 3:**
   - Name: `daily-standups`
   - Description: Daily progress updates - what you did, what you're doing, any blockers

   **Channel 4:**
   - Name: `bugs-and-issues`
   - Description: Report bugs and technical issues here before creating GitHub issues

   **Channel 5:**
   - Name: `ideas-and-features`
   - Description: Brainstorm new features and improvements

   **Channel 6:**
   - Name: `links-and-resources`
   - Description: Useful links, documentation, and resources

   **Channel 7:**
   - Name: `meeting-notes`
   - Description: Notes and action items from team meetings

4. **Create Voice Channels**:

   Right-click on "VOICE CHANNELS" header > Create Channel:

   **Voice Channel 1:**
   - Name: `🎙️ Weekly Sync`
   - Description: For weekly team meetings

   **Voice Channel 2:**
   - Name: `🎙️ Pair Programming`
   - Description: For collaborative coding sessions

   **Voice Channel 3:**
   - Name: `🎙️ AFK`
   - Description: Join when you're away from keyboard but still online

5. **Server Settings**:
   - Click server name (top left) > Server Settings
   - Under "Overview": Add server description
   - Under "Moderation": Set verification level to "Low"
   - Save changes

---

### ✅ Task 5: Invite Team to Discord

**Add team members to Discord server**

**Steps:**

1. Click server name (top left) > Invite People
2. Click "Edit invite link"
3. Settings:
   - **Expire after**: Never
   - **Max number of uses**: No limit
4. Click "Generate a New Link"
5. Copy the invite link
6. Send invite link to:
   - Backend Engineer
   - Frontend Engineer
   - (Via email, text, or any other communication method)

**Ask team members to:**

- Click the invite link
- Create Discord account if they don't have one
- Download Discord desktop app (recommended) from https://discord.com/download
- Download Discord mobile app for notifications
- Set notification preferences (Settings > Notifications)

---

### ✅ Task 6: Create GitHub Project Board

**Set up project management board for tracking work**

**Steps:**

1. Go to `https://github.com/orgs/yourorg/projects`
2. Click "New project"
3. Select "Team backlog" template
4. **Project name**: "Digital Signage Platform - Development"
5. Click "Create project"

6. **Customize the Board View**:
   - You'll see columns: Backlog, Ready, In Progress, In Review, Done
   - Keep these columns (they're perfect for your workflow)

7. **Add Custom Fields**:

   Click "+ Add field" at the top:

   **Field 1 - Sprint:**
   - Type: Single select
   - Options: Sprint 1, Sprint 2, Sprint 3, Sprint 4, Backlog

   **Field 2 - Priority:**
   - Type: Single select
   - Options: 🔴 High, 🟡 Medium, 🟢 Low

   **Field 3 - Component:**
   - Type: Single select
   - Options: Backend, Frontend, Player, DevOps, Documentation

   **Field 4 - Estimate:**
   - Type: Number
   - Unit: hours

8. **Create Additional Views**:

   Click "New view" next to "Board":

   **View 2 - Table:**
   - Select "Table" layout
   - Show columns: Title, Status, Assignees, Priority, Sprint, Component, Estimate

   **View 3 - Roadmap:**
   - Select "Roadmap" layout
   - Group by: Sprint
   - This will show timeline view

9. **Project Settings**:
   - Click "..." (three dots) > Settings
   - Enable "Automatically add items" if you want issues to appear automatically
   - Save

---

### ✅ Task 7: Set Up Project Labels

**Create standardized labels for issues across all repositories**

**Note**: Do this after Backend engineer creates repositories

**Steps:**

1. Go to `https://github.com/orgs/yourorg/settings/repository-defaults`
2. Scroll to "Labels"
3. Click "New label" for each of these:

**Label 1:**

- Name: `type: feature`
- Description: New feature or enhancement
- Color: `#1d76db` (blue)

**Label 2:**

- Name: `type: bug`
- Description: Something isn't working
- Color: `#d73a4a` (red)

**Label 3:**

- Name: `type: documentation`
- Description: Documentation improvements
- Color: `#0075ca` (blue)

**Label 4:**

- Name: `type: task`
- Description: General task or chore
- Color: `#bfdadc` (light blue)

**Label 5:**

- Name: `priority: high`
- Description: High priority
- Color: `#d93f0b` (orange)

**Label 6:**

- Name: `priority: medium`
- Description: Medium priority
- Color: `#fbca04` (yellow)

**Label 7:**

- Name: `priority: low`
- Description: Low priority
- Color: `#0e8a16` (green)

**Label 8:**

- Name: `component: backend`
- Description: Backend related
- Color: `#5319e7` (purple)

**Label 9:**

- Name: `component: frontend`
- Description: Frontend related
- Color: `#1d76db` (blue)

**Label 10:**

- Name: `component: player`
- Description: Player related
- Color: `#c5def5` (light blue)

**Label 11:**

- Name: `status: blocked`
- Description: Blocked by another issue
- Color: `#000000` (black)

**Label 12:**

- Name: `good first issue`
- Description: Good for newcomers
- Color: `#7057ff` (purple)

---

### ✅ Task 8: Create Initial Sprint 1 Issues

**Create the first set of issues for Sprint 1 (POC)**

**Note**: Do this after Backend engineer creates repositories and issue templates

**Steps:**

1. Go to the **backend repository**: `https://github.com/yourorg/yourproject-backend`
2. Click "Issues" tab
3. Click "New issue"
4. Create each issue below:

---

**Issue 1:**

```
Title: Set up ASP.NET Core project structure

Type: Feature template

Description:
Create the initial ASP.NET Core 8 Web API project with Clean Architecture structure.

Acceptance Criteria:
- [ ] Project created with .NET 8
- [ ] Folder structure following Clean Architecture (Api, Core, Infrastructure)
- [ ] Basic controllers setup (HealthCheck endpoint)
- [ ] appsettings.json configured with connection strings placeholders
- [ ] Project runs locally
- [ ] README.md with setup instructions

Technical Notes:
- Use Clean Architecture pattern
- Separate concerns: API, Core/Domain, Infrastructure
- Set up dependency injection properly

Labels: type: feature, priority: high, component: backend
Assignee: Backend Engineer
Project: Add to "Digital Signage Platform - Development"
Sprint: Sprint 1
```

---

**Issue 2:**

```
Title: Set up Azure resources (App Service, SQL Database, Blob Storage)

Type: Task template

Description:
Create and configure all necessary Azure resources for the POC.

Acceptance Criteria:
- [ ] Azure App Service created (Free/Basic tier)
- [ ] Azure SQL Database created (Basic tier)
- [ ] Azure Blob Storage account created
- [ ] Blob container 'media' created
- [ ] Connection strings documented in secure location
- [ ] Resources tested and accessible

Technical Notes:
- Keep costs minimal (use free/basic tiers)
- Document all resource names and connection strings
- Set up proper access policies

Labels: type: task, priority: high, component: backend
Assignee: Backend Engineer
Sprint: Sprint 1
```

---

**Issue 3:**

```
Title: Implement Entity Framework Core models and migrations

Type: Feature template

Description:
Create database models for User, Device, Media, Schedule, and ScheduleItem entities.

Acceptance Criteria:
- [ ] All entities created with proper relationships
- [ ] DbContext configured
- [ ] Initial migration created
- [ ] Migration applied to Azure SQL Database
- [ ] Database schema documented

Technical Notes:
Entities needed: User, Device, Media, Schedule, ScheduleItem, DeviceHeartbeat

Labels: type: feature, priority: high, component: backend
Assignee: Backend Engineer
Sprint: Sprint 1
```

---

**Issue 4:**

```
Title: Implement JWT authentication (register/login endpoints)

Type: Feature template

Description:
Create user authentication system with JWT tokens.

User Story:
As a user, I want to register and login so that I can access my account.

Acceptance Criteria:
- [ ] POST /api/auth/register endpoint (email, password)
- [ ] POST /api/auth/login endpoint (returns JWT token)
- [ ] Password hashing implemented (BCrypt or Identity)
- [ ] JWT token generation with proper claims
- [ ] Token validation middleware configured
- [ ] Endpoints tested with Postman/Swagger

Labels: type: feature, priority: high, component: backend
Assignee: Backend Engineer
Sprint: Sprint 1
```

---

**Issue 5:**

```
Title: Implement media upload to Azure Blob Storage

Type: Feature template

Description:
Create endpoint for uploading images and videos to Azure Blob Storage.

User Story:
As a user, I want to upload media files so that I can use them in schedules.

Acceptance Criteria:
- [ ] POST /api/media/upload endpoint (multipart/form-data)
- [ ] File validation (type, size max 100MB)
- [ ] Upload to Azure Blob Storage
- [ ] Create Media record in database
- [ ] Return media URL and metadata
- [ ] GET /api/media endpoint (list user's media)
- [ ] DELETE /api/media/{id} endpoint

Labels: type: feature, priority: high, component: backend
Assignee: Backend Engineer
Sprint: Sprint 1
```

---

**Issue 6:**

```
Title: Implement device pairing system (generate code, activate device)

Type: Feature template

Description:
Create the device pairing flow with pairing codes.

User Story:
As a user, I want to pair my display device so that I can send content to it.

Acceptance Criteria:
- [ ] POST /api/devices/pair endpoint (generates 6-digit code)
- [ ] Code expires after 15 minutes
- [ ] POST /api/player/activate endpoint (player uses code to register)
- [ ] Device UUID stored
- [ ] GET /api/devices endpoint (list user's devices with status)
- [ ] Device pairing tested end-to-end

Labels: type: feature, priority: high, component: backend
Assignee: Backend Engineer
Sprint: Sprint 1
```

---

5. Go to the **frontend repository**: `https://github.com/yourorg/yourproject-frontend`
6. Create frontend issues:

---

**Issue 7:**

```
Title: Set up React + TypeScript + Vite project

Type: Feature template

Description:
Create the initial frontend project with all necessary dependencies.

Acceptance Criteria:
- [ ] Project created with Vite + React 18 + TypeScript
- [ ] TailwindCSS configured
- [ ] React Router set up
- [ ] Axios configured for API calls
- [ ] Environment variables set up (.env.example)
- [ ] Project runs locally
- [ ] README.md with setup instructions

Technical Notes:
Dependencies: @tanstack/react-query, zustand, react-hook-form, zod, tailwindcss

Labels: type: feature, priority: high, component: frontend
Assignee: Frontend Engineer
Sprint: Sprint 1
```

---

**Issue 8:**

```
Title: Create authentication pages (Login/Register)

Type: Feature template

Description:
Build login and registration pages with form validation.

User Story:
As a user, I want to login and register so that I can access the platform.

Acceptance Criteria:
- [ ] Login page with email and password fields
- [ ] Register page with email, password, confirm password
- [ ] Form validation using react-hook-form + zod
- [ ] Connect to backend auth API
- [ ] Store JWT token in localStorage/cookie
- [ ] Redirect to dashboard on successful login
- [ ] Show error messages for failed login
- [ ] Protected routes implementation

Labels: type: feature, priority: high, component: frontend
Assignee: Frontend Engineer
Sprint: Sprint 1
```

---

**Issue 9:**

```
Title: Create dashboard layout (header, sidebar, main content area)

Type: Feature template

Description:
Build the main application layout structure.

Acceptance Criteria:
- [ ] Header component with logo and user menu
- [ ] Sidebar with navigation links
- [ ] Main content area
- [ ] Responsive design (mobile-friendly)
- [ ] Logout functionality
- [ ] Active route highlighting in sidebar

Labels: type: feature, priority: medium, component: frontend
Assignee: Frontend Engineer
Sprint: Sprint 1
```

---

**Issue 10:**

```
Title: Create Devices page (list, add device with pairing code)

Type: Feature template

Description:
Build the devices management page.

User Story:
As a user, I want to see my devices and add new ones so that I can manage my displays.

Acceptance Criteria:
- [ ] Devices list page showing all devices
- [ ] Device card showing name, status (online/offline), last heartbeat
- [ ] "Add Device" button opens modal
- [ ] Modal shows generated pairing code
- [ ] Poll backend for device activation
- [ ] Show success message when device is paired
- [ ] Update device list when new device added

Labels: type: feature, priority: high, component: frontend
Assignee: Frontend Engineer
Sprint: Sprint 1
```

---

**Issue 11:**

```
Title: Create Media Library page (upload, list, delete)

Type: Feature template

Description:
Build media management page for uploading and managing media files.

User Story:
As a user, I want to upload and manage my media files so that I can use them in schedules.

Acceptance Criteria:
- [ ] Media grid view showing thumbnails
- [ ] Upload button with file picker
- [ ] Support image (jpg, png) and video (mp4) upload
- [ ] Show upload progress bar
- [ ] Display file name, type, size, upload date
- [ ] Delete media functionality with confirmation
- [ ] Responsive grid layout

Labels: type: feature, priority: high, component: frontend
Assignee: Frontend Engineer
Sprint: Sprint 1
```

---

7. Go to the **player repository**: `https://github.com/yourorg/yourproject-player`
8. Create player issues:

---

**Issue 12:**

```
Title: Set up PWA player project (React + TypeScript + Vite)

Type: Feature template

Description:
Create the PWA player project with offline capabilities.

Acceptance Criteria:
- [ ] Vite + React + TypeScript project created
- [ ] Service Worker configured with Workbox
- [ ] PWA manifest file created
- [ ] Fullscreen API integration
- [ ] Project runs locally
- [ ] Can be "installed" as PWA
- [ ] README.md with setup instructions

Technical Notes:
- Use Workbox for service worker
- Configure offline caching strategy
- Set up IndexedDB for local storage

Labels: type: feature, priority: high, component: player
Assignee: Frontend Engineer
Sprint: Sprint 1
```

---

**Issue 13:**

```
Title: Create device pairing screen for player

Type: Feature template

Description:
Build the initial pairing screen where player shows code input.

User Story:
As a display device, I want to show a pairing screen so that the user can register me.

Acceptance Criteria:
- [ ] Generate and store device UUID on first launch
- [ ] Show code input screen
- [ ] Call backend /api/player/activate with code
- [ ] Handle invalid/expired codes
- [ ] Store device credentials locally
- [ ] Redirect to display screen on successful pairing

Labels: type: feature, priority: high, component: player
Assignee: Frontend Engineer
Sprint: Sprint 1
```

---

**Issue 14:**

```
Title: Implement schedule fetching and caching

Type: Feature template

Description:
Build the logic to fetch schedule from backend and cache it locally.

Acceptance Criteria:
- [ ] Fetch schedule from /api/player/schedule/{deviceUuid}
- [ ] Cache schedule in IndexedDB
- [ ] Download and cache media files referenced in schedule
- [ ] Handle offline mode (use cached schedule)
- [ ] Periodic check for schedule updates (every 5 minutes)
- [ ] Handle errors gracefully

Labels: type: feature, priority: high, component: player
Assignee: Frontend Engineer
Sprint: Sprint 1
```

---

**Issue 15:**

```
Title: Implement schedule execution engine (display content)

Type: Feature template

Description:
Build the core logic that displays content according to schedule.

Acceptance Criteria:
- [ ] Parse schedule and determine what to show now
- [ ] Display images fullscreen
- [ ] Display videos fullscreen with autoplay
- [ ] Rotate through active schedule items
- [ ] Handle time ranges correctly (start/end time)
- [ ] Display duration respected for each item
- [ ] Fallback to logo/black screen when no content scheduled

Labels: type: feature, priority: high, component: player
Assignee: Frontend Engineer
Sprint: Sprint 1
```

---

9. **Add all issues to Project Board**:
   - Go to each issue
   - Click "Projects" in right sidebar
   - Select "Digital Signage Platform - Development"
   - Set Status to "Backlog"
   - Set appropriate Sprint, Priority, Component fields

---

### ✅ Task 9: Create Weekly Sync Meeting Template

**Set up a recurring template for weekly meetings**

**Steps:**

1. In Discord, go to `#meeting-notes` channel
2. Pin this message (right-click > Pin Message):

```markdown
# 📅 Weekly Sync Meeting Template

**Copy this template for each meeting:**

---

# Weekly Sync - [Date: YYYY-MM-DD]

**Attendees:** @Backend @Frontend @PM

## ✅ Last Week Accomplishments

**Backend:**

- [Accomplishment 1]
- [Accomplishment 2]

**Frontend:**

- [Accomplishment 1]
- [Accomplishment 2]

**Blockers Resolved:**

- [Blocker 1 and how it was resolved]

## 📊 Sprint Progress

- **Completed:** X/Y issues
- **In Progress:** Z issues
- **Blocked:** N issues

**GitHub Project Board:** [Link to board]

## 🎯 This Week Goals

**Backend:**

- [ ] Goal 1
- [ ] Goal 2

**Frontend:**

- [ ] Goal 1
- [ ] Goal 2

**Player:**

- [ ] Goal 1

## 🚧 Blockers / Help Needed

- [Blocker 1 - who needs help with what]
- [Blocker 2]

## 💬 Discussion Items

1. [Topic 1 to discuss]
2. [Topic 2 to discuss]

## 📝 Action Items

- [ ] [Action item 1] - @Person - Due date
- [ ] [Action item 2] - @Person - Due date

## 📅 Next Meeting

**Date:** [Next week same day/time]
**Time:** [Time]

---
```

---

### ✅ Task 10: Schedule First Team Meeting

**Set up the first weekly sync meeting**

**Steps:**

1. **Choose a meeting time:**
   - Find a time that works for all 3 team members
   - Recommend: Same day/time each week (e.g., Every Monday 10:00 AM)
   - Duration: 1 hour

2. **Create a recurring calendar event** (use Google Calendar with project email):
   - Go to https://calendar.google.com
   - Login with project email
   - Click "Create" > "Event"
   - **Title:** "Weekly Sync - Digital Signage Platform"
   - **Date/Time:** [Your chosen time]
   - **Repeat:** Weekly
   - **Guests:** Add team members' emails
   - **Add video conferencing:** Google Meet (or use Discord voice channel)
   - **Description:**

     ```
     Weekly team sync for Digital Signage Platform project

     Discord Voice Channel: [Link to Discord server]

     Agenda template: [Link to #meeting-notes pinned message]
     ```

   - Click "Save"

3. **Announce in Discord `#announcements`:**

   ```
   📅 **First Team Meeting Scheduled!**

   **When:** [Day, Date, Time]
   **Where:** Discord > 🎙️ Weekly Sync voice channel
   **Duration:** 1 hour

   **Agenda:**
   - Introductions
   - Review project setup progress
   - Discuss tech stack and architecture
   - Sprint 1 planning
   - Q&A

   See you there! 🚀
   ```

---

### ✅ Task 11: Document All Credentials and Access

**Create a secure document with all project credentials**

**Steps:**

1. **Set up a password manager** (Choose one):
   - **Bitwarden** (free tire allows 2 users, PM and Backend to have access): https://bitwarden.com

2. **Create a shared vault/folder** for the project:
   - Name: "ProjectName"

3. **Add all credentials**:

   **Entry 1: Project Email**
   - Title: Project Email Account
   - Username: yourproject.team@gmail.com
   - Password: [password]
   - Notes: Recovery email, phone number

   **Entry 2: GitHub Organization**
   - Title: GitHub Organization
   - URL: https://github.com/yourorg
   - Owner: [GitHub username]
   - Notes: Organization name

   **Entry 3: Azure Subscription**
   - Title: Azure Subscription
   - URL: https://portal.azure.com
   - Email: [Project email]
   - Notes: Subscription ID (Backend will add this)

   **Entry 4: Discord Server**
   - Title: Discord Server
   - URL: [Discord server invite link]
   - Admin: [Your Discord username]
   - Notes: Server ID

4. **Share vault with team**:
   - Invite Backend Engineer (read/write access)
   - Invite Frontend Engineer (read access)
   - Each team member should have their own password manager account

5. **Create a backup** (in case password manager is inaccessible):
   - Create a Google Doc with project email
   - Title: "Project Credentials - CONFIDENTIAL"
   - List all credentials
   - Share only with core team members
   - Set to "Restricted" access

---

### ✅ Task 12: Create Project Documentation Home Page

**Set up the initial Wiki home page**

**Note**: Do this after Backend engineer creates the main backend repository

**Steps:**

1. Go to your main repository (backend): `https://github.com/yourorg/yourproject-backend`
2. Click "Wiki" tab
3. Click "Create the first page"
4. **Title:** Home
5. **Content:**

```markdown
# Digital Signage Platform - Project Documentation

Welcome to the Digital Signage Platform project documentation!

## 🎯 Project Overview

A digital signage solution that allows businesses (restaurants, shops, etc.) to manage and display content on their screens remotely.

**Target Users:** Restaurant owners, retail shops, any business with display screens

**Core Features (POC):**

- User authentication and account management
- Upload images and videos
- Pair display devices remotely
- Schedule content with time ranges
- Display content on any screen (PWA-based player)

## 🏗️ Architecture

**3-Tier System:**

1. **Website** (React + TypeScript) - User management interface
2. **Backend** (.NET 8 API) - Business logic and data management
3. **Player** (PWA) - Content display on devices

**Technology Stack:**

- **Backend:** ASP.NET Core 8, Entity Framework Core, Azure SQL Database
- **Frontend:** React 18, TypeScript, Vite, TailwindCSS
- **Player:** React PWA with Service Workers
- **Cloud:** Azure (App Service, SQL Database, Blob Storage)
- **Storage:** Azure Blob Storage for media files

## 📚 Documentation Structure

- [Getting Started](Getting-Started) - Setup instructions for new developers
- [Architecture](Architecture) - System architecture and design
- [Database Schema](Database-Schema) - Database structure
- [API Documentation](API-Documentation) - Backend API endpoints
- [Deployment Guide](Deployment-Guide) - How to deploy to Azure
- [Meeting Notes](Meeting-Notes) - Team meeting notes and decisions

## 🔗 Quick Links

- **GitHub Organization:** https://github.com/yourorg
- **Project Board:** [Link to GitHub Projects]
- **Discord Server:** [Invite link]
- **Azure Portal:** https://portal.azure.com

## 👥 Team

- **Project Manager:** [Name] - Project coordination and planning
- **Backend Engineer:** [Name] - .NET backend development
- **Frontend Engineer:** [Name] - React frontend and PWA player

## 📅 Project Timeline

**Sprint 1 (Week 1-2):** Foundation - Auth, media upload, device pairing
**Sprint 2 (Week 3-4):** Core features - Scheduling, content display
**Sprint 3 (Week 5-6):** Polish and testing

**Target POC Completion:** 6 weeks

## 🚀 Getting Started

New to the project? Start here:

1. [Set up your development environment](Getting-Started)
2. Check out the [Architecture](Architecture) to understand the system
3. Join our Discord server for communication
4. Look at the [Project Board](link) for current work items

## 📝 Contributing

1. Create a branch from `main`
2. Make your changes
3. Create a Pull Request
4. Request review from team
5. Merge after approval

## 📞 Contact

For questions or issues, reach out in Discord #general channel.

---

**Last Updated:** [Today's date]
```

6. Click "Save Page"

---

### ✅ Task 13: Create Communication Guidelines Document

**Document how the team should communicate**

**Steps:**

1. In Discord, go to `#links-and-resources` channel
2. Post this message and pin it:

```markdown
# 📱 Team Communication Guidelines

## Response Time Expectations

⚡ **Urgent** (someone is blocked): < 2 hours

- Use @mentions in Discord
- Can call if no response

📬 **Normal**: Within same workday

- Regular questions and updates

📅 **Non-urgent**: Next day is fine

- Ideas, suggestions, non-blocking items

## Channel Usage

**#announcements**

- Important updates only
- Everyone should read these
- Notifications turned on

**#general**

- Casual chat and quick questions
- Celebrating wins 🎉
- Memes and fun (keep it professional)

**#daily-standups**

- Post your daily update using the template
- Post by end of day or start of next day
- Keep it brief (3-5 bullets)

**#bugs-and-issues**

- Report bugs here first
- Discuss before creating GitHub issue
- Tag relevant person (@Backend or @Frontend)

**#ideas-and-features**

- Brainstorm new features
- Discuss improvements
- No bad ideas!

**#links-and-resources**

- Useful links, articles, tools
- Documentation links
- Reference materials

**#meeting-notes**

- Meeting notes only
- Use the template
- Post after each meeting

## Voice Channels

**🎙️ Weekly Sync**

- Weekly team meeting (1 hour)
- [Day/Time]

**🎙️ Pair Programming**

- Jump in when you need to collaborate
- Screen sharing for debugging

**🎙️ AFK**

- Join when you're away but still online
- Or just for hanging out while working

## Best Practices

✅ **Do:**

- Use threads for detailed discussions
- @mention people when you need their attention
- Use emojis for reactions (👍 ✅ 👀)
- Share your screen when explaining complex issues
- Post daily standups consistently
- Ask questions! No such thing as a dumb question

❌ **Don't:**

- @everyone unless truly urgent
- Discuss in DMs (keep it in channels for transparency)
- Leave people hanging on blockers
- Feel bad about pinging people when you're stuck

## Work Schedule

We all have day jobs, so we're flexible with timing:

- **No expectation of immediate responses**
- **Core overlap hours (if any):** [Define if needed]
- **Weekly sync is mandatory** (unless you notify in advance)
- **Daily standups are async** (post when you can)

## GitHub Communication

- **Pull Requests:** Request review from relevant person
- **Issues:** Use @mentions in comments
- **Code Reviews:** Provide constructive feedback
- **Commits:** Write clear commit messages

## When You're Blocked

1. Post in #bugs-and-issues or #general
2. @mention the person who can help
3. Explain what you're stuck on and what you've tried
4. If urgent, follow up after 2 hours

## When You'll Be Unavailable

Post in #general:
```

🏖️ **Away:** [Dates]
**Reason:** [Brief reason, optional]
**Availability:** [None / Limited / Emergency only]

```

---

**Questions about these guidelines?** Ask in #general!
```

---

## 📊 PM Weekly Responsibilities

Once initial setup is complete, here are your ongoing weekly tasks:

### **Every Monday (Before weekly sync):**

- [ ] Review GitHub Project Board
- [ ] Check sprint progress (issues completed vs remaining)
- [ ] Identify any blockers or issues
- [ ] Prepare meeting agenda
- [ ] Update project metrics

### **Weekly Sync Meeting (Every Monday):**

- [ ] Facilitate the meeting
- [ ] Take notes in #meeting-notes
- [ ] Ensure action items are clear and assigned
- [ ] Update Project Board during or after meeting

### **Every Friday:**

- [ ] Review week's progress
- [ ] Celebrate completed work in #general
- [ ] Preview next week's priorities
- [ ] Update any documentation that's changed

### **As Needed:**

- [ ] Create new issues based on team discussions
- [ ] Respond to questions in Discord
- [ ] Update project documentation
- [ ] Coordinate between team members if conflicts arise
- [ ] Track time spent (for future estimates)

---

## ✅ PM Setup Completion Checklist

Before considering your setup complete, verify:

- [ ] Project email created and 2FA enabled
- [ ] GitHub organization created
- [ ] All team members invited and accepted GitHub invites
- [ ] Discord server created with all channels
- [ ] Team members joined Discord
- [ ] GitHub Project Board created with custom fields
- [ ] All Sprint 1 issues created and added to Project Board
- [ ] Meeting templates created and pinned
- [ ] First weekly sync scheduled
- [ ] Password manager set up with credentials shared
- [ ] Wiki home page created
- [ ] Communication guidelines posted and pinned
- [ ] All team members have access to everything they need

**Estimated Time:** 4-6 hours total

---
