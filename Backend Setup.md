# 💻 BACKEND ENGINEER - Setup Tasks

## Week 1, Day 1-2 Tasks

### ✅ Task 1: Accept GitHub Organization Invite

**Join the GitHub organization**

**Steps:**

1. Check your email for GitHub invitation from PM
2. Click the invitation link
3. Click "Join [organization-name]"
4. Verify you can see the organization at `https://github.com/yourorg`

**If you don't have a GitHub account:**

1. Go to https://github.com/signup
2. Create account
3. Ask PM to resend invitation

---

### ✅ Task 2: Create GitHub Repositories

**Create the three main repositories for the project**

**Steps:**

**Repository 1: Backend**

1. Go to `https://github.com/orgs/yourorg/repositories`
2. Click "New repository"
3. **Repository name:** `yourproject-backend` (replace yourproject with actual name)
4. **Description:** `.NET 8 backend API for Digital Signage Platform`
5. **Visibility:** Private
6. **Initialize repository with:**
   - ✅ Add a README file
   - ✅ Add .gitignore: Choose "VisualStudio" template
   - ✅ Choose a license: MIT License (or your preference)
7. Click "Create repository"

**Repository 2: Frontend**

1. Click "New repository" again
2. **Repository name:** `yourproject-frontend`
3. **Description:** `React frontend web application for Digital Signage Platform`
4. **Visibility:** Private
5. **Initialize repository with:**
   - ✅ Add a README file
   - ✅ Add .gitignore: Choose "Node" template
   - ✅ Choose a license: MIT License
6. Click "Create repository"

**Repository 3: Player**

1. Click "New repository" again
2. **Repository name:** `yourproject-player`
3. **Description:** `PWA player for displaying content on screens`
4. **Visibility:** Private
5. **Initialize repository with:**
   - ✅ Add a README file
   - ✅ Add .gitignore: Choose "Node" template
   - ✅ Choose a license: MIT License
6. Click "Create repository"

**Verification:**

- Go to `https://github.com/yourorg`
- You should see all 3 repositories listed

---

### ✅ Task 3: Set Up GitHub Issue Templates

**Create issue templates for consistent issue reporting**

**Steps:**

**For Backend Repository:**

1. Go to `https://github.com/yourorg/yourproject-backend`
2. Click "Settings" tab
3. Scroll down to "Features" section
4. Check ✅ "Issues"
5. Click on repository name to go back to main page
6. Click "Issues" tab
7. Click "Set up templates" (or if you don't see it, go to Settings > Features > Issues > Set up templates)

**Alternative method (recommended):**

1. Clone the backend repository locally:

```bash
git clone https://github.com/yourorg/yourproject-backend.git
cd yourproject-backend
```

2. Create `.github/ISSUE_TEMPLATE/` directory:

```bash
mkdir -p .github/ISSUE_TEMPLATE
```

3. Create **Feature Template** file:

Create file: `.github/ISSUE_TEMPLATE/feature.md`

```markdown
---
name: Feature
about: New feature or enhancement
title: ""
labels: "type: feature"
assignees: ""
---

## Description

Brief description of the feature

## User Story

As a [user type], I want [goal] so that [benefit]

## Acceptance Criteria

- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

## Technical Notes

Any implementation details, API endpoints, database changes, etc.

## Dependencies

**Blocks:** #issue-number
**Blocked by:** #issue-number

## Definition of Done

- [ ] Code written and tested
- [ ] Unit tests added
- [ ] Code reviewed and approved
- [ ] Merged to main branch
- [ ] Deployed to Azure (if applicable)
```

4. Create **Bug Template** file:

Create file: `.github/ISSUE_TEMPLATE/bug.md`

```markdown
---
name: Bug Report
about: Something isn't working correctly
title: ""
labels: "type: bug"
assignees: ""
---

## Description

Clear description of what the bug is

## Steps to Reproduce

1. Step 1
2. Step 2
3. Step 3

## Expected Behavior

What should happen

## Actual Behavior

What actually happens

## Screenshots / Logs

If applicable, add screenshots or error logs

## Environment

- **Browser/Device:**
- **OS:**
- **Version:**
- **API Environment:** (Development / Staging / Production)

## Additional Context

Any other information about the problem

## Possible Solution

If you have ideas on how to fix this
```

5. Create **Task Template** file:

Create file: `.github/ISSUE_TEMPLATE/task.md`

```markdown
---
name: Task
about: General task or chore
title: ""
labels: "type: task"
assignees: ""
---

## Description

What needs to be done

## Acceptance Criteria

- [ ] Criterion 1
- [ ] Criterion 2

## Additional Notes

Any relevant information

## Definition of Done

- [ ] Task completed
- [ ] Changes documented (if applicable)
- [ ] Team notified
```

6. Commit and push:

```bash
git add .github/ISSUE_TEMPLATE/
git commit -m "Add issue templates"
git push origin main
```

**Repeat for Frontend and Player repositories:**

1. Copy the `.github/ISSUE_TEMPLATE/` folder to the other repositories
2. Push to each repository

---

### ✅ Task 4: Set Up Pull Request Template

**Create a PR template for consistent code reviews**

**Steps:**

1. In your backend repository (locally):

Create file: `.github/PULL_REQUEST_TEMPLATE.md`

```markdown
## Description

Brief description of what this PR does

## Type of Change

- [ ] Bug fix
- [ ] New feature
- [ ] Breaking change
- [ ] Documentation update
- [ ] Refactoring

## Related Issues

Closes #issue-number

## Changes Made

- Change 1
- Change 2
- Change 3

## Testing

- [ ] Unit tests added/updated
- [ ] Manual testing completed
- [ ] Tested on local environment
- [ ] Tested on Azure (if deployed)

## Screenshots (if applicable)

Add screenshots for UI changes

## Checklist

- [ ] Code follows project style guidelines
- [ ] Self-reviewed my own code
- [ ] Commented complex code sections
- [ ] Updated documentation (if needed)
- [ ] No new warnings or errors
- [ ] Added tests that prove the fix/feature works
- [ ] All tests passing locally

## Additional Notes

Any additional context or notes for reviewers
```

2. Commit and push:

```bash
git add .github/PULL_REQUEST_TEMPLATE.md
git commit -m "Add pull request template"
git push origin main
```

3. Copy to frontend and player repositories and push

---

### ✅ Task 5: Connect GitHub to Discord

**Set up webhook so Discord gets notified of GitHub activity**

**Steps:**

1. **Get Discord Webhook URL** from PM:
   - PM should have created this in Task 6
   - It should be posted in #links-and-resources
   - Format: `https://discord.com/api/webhooks/...`

2. **Configure webhook for Backend repository:**
   - Go to `https://github.com/yourorg/yourproject-backend`
   - Click "Settings" tab
   - Click "Webhooks" in left sidebar
   - Click "Add webhook"
   - **Payload URL:** Paste Discord webhook URL + `/github` (important to add /github)
     - Example: `https://discord.com/api/webhooks/123456/abcdef/github`
   - **Content type:** application/json
   - **Which events:** Select "Send me everything" or customize:
     - ✅ Push events
     - ✅ Pull requests
     - ✅ Issues
     - ✅ Issue comments
   - Click "Add webhook"

3. **Test the webhook:**
   - Make a small change to README.md
   - Commit and push
   - Check Discord #general (or wherever webhook is configured)
   - You should see a notification about the commit

4. **Repeat for Frontend and Player repositories**

**Alternative (easier) method:**

1. Go to https://github.com/settings/installations
2. Search for "Discord" in GitHub Marketplace
3. Install "Discord" integration
4. Configure which repositories to connect
5. Follow authentication flow with Discord

---

### ✅ Task 6: Install Development Tools

**Set up your local development environment**

**Required Software:**

1. **.NET 8 SDK:**
   - Download: https://dotnet.microsoft.com/download/dotnet/8.0
   - Choose SDK (not just runtime)
   - Install for your OS
   - Verify: Open terminal and run `dotnet --version` (should show 8.x.x)

2. **Visual Studio 2022** (Windows) OR **Visual Studio Code** (Mac/Linux):

   **Option A: Visual Studio 2022 (Recommended for Windows):**
   - Download: https://visualstudio.microsoft.com/downloads/
   - Choose "Community" edition (free)
   - During installation, select:
     - ✅ ASP.NET and web development
     - ✅ Azure development
     - ✅ .NET desktop development

   **Option B: Visual Studio Code (Mac/Linux/Windows):**
   - Download: https://code.visualstudio.com/
   - Install extensions:
     - C# Dev Kit (Microsoft)
     - Azure Tools (Microsoft)
     - GitLens
     - REST Client (for API testing)

3. **Azure CLI:**
   - Download: https://docs.microsoft.com/cli/azure/install-azure-cli
   - Install for your OS
   - Verify: Run `az --version`

4. **Git:**
   - Download: https://git-scm.com/downloads
   - Install for your OS
   - Configure:
     ```bash
     git config --global user.name "Your Name"
     git config --global user.email "your.email@example.com"
     ```

5. **Postman or Insomnia** (for API testing):
   - Postman: https://www.postman.com/downloads/
   - Or Insomnia: https://insomnia.rest/download

6. **SQL Server Management Studio (SSMS)** (optional, Windows only):
   - Download: https://aka.ms/ssmsfullsetup
   - Or use **Azure Data Studio** (cross-platform): https://aka.ms/azuredatastudio

7. **Node.js** (needed for some .NET tooling):
   - Download: https://nodejs.org/ (LTS version)
   - Verify: `node --version` and `npm --version`

---

### ✅ Task 7: Create Azure Account and Subscription

**Set up Azure cloud resources**

**Steps:**

1. **Create Azure Account:**
   - Go to https://azure.microsoft.com/free/
   - Click "Start free"
   - Sign up using **project email** (created by PM)
   - You get $200 free credit for 30 days
   - Verify email address

2. **Complete Azure Setup:**
   - Add phone number for verification
   - Add credit card (required for verification, won't be charged during free trial)
   - Complete profile information

3. **Access Azure Portal:**
   - Go to https://portal.azure.com
   - Sign in with project email

4. **Note your Subscription ID:**
   - In Azure Portal, search for "Subscriptions"
   - Click on your subscription
   - Copy the "Subscription ID" (you'll need this)
   - Share with PM to add to password manager

---

### ✅ Task 8: Create Azure Resources

**Set up all cloud resources needed for the project**

**Steps:**

**1. Create Resource Group:**

```bash
# Login to Azure
az login

# Create resource group (replace with your chosen location)
az group create \
  --name digitalsignage-rg \
  --location eastus

# Note: Choose a location close to your target users
# Options: eastus, westus, westeurope, etc.
```

**2. Create Azure SQL Database:**

```bash
# Create SQL Server
az sql server create \
  --name digitalsignage-sql-server \
  --resource-group digitalsignage-rg \
  --location eastus \
  --admin-user sqladmin \
  --admin-password "YourSecurePassword123!"

# Note: Replace password with a strong password, save it securely

# Configure firewall to allow Azure services
az sql server firewall-rule create \
  --resource-group digitalsignage-rg \
  --server digitalsignage-sql-server \
  --name AllowAzureServices \
  --start-ip-address 0.0.0.0 \
  --end-ip-address 0.0.0.0

# Add your local IP for development
az sql server firewall-rule create \
  --resource-group digitalsignage-rg \
  --server digitalsignage-sql-server \
  --name AllowLocalDevelopment \
  --start-ip-address YOUR_IP_ADDRESS \
  --end-ip-address YOUR_IP_ADDRESS

# Find your IP: https://www.whatismyip.com/

# Create database (Basic tier for POC)
az sql db create \
  --resource-group digitalsignage-rg \
  --server digitalsignage-sql-server \
  --name digitalsignage-db \
  --service-objective Basic \
  --backup-storage-redundancy Local

# Get connection string
az sql db show-connection-string \
  --client ado.net \
  --server digitalsignage-sql-server \
  --name digitalsignage-db
```

**3. Create Azure Blob Storage:**

```bash
# Create storage account (name must be globally unique, lowercase, no hyphens)
az storage account create \
  --name digitalsignagestorage \
  --resource-group digitalsignage-rg \
  --location eastus \
  --sku Standard_LRS \
  --kind StorageV2

# Create blob container for media
az storage container create \
  --name media \
  --account-name digitalsignagestorage \
  --public-access off

# Get storage connection string
az storage account show-connection-string \
  --name digitalsignagestorage \
  --resource-group digitalsignage-rg
```

**4. Create Azure App Service (for Backend API):**

```bash
# Create App Service Plan (Free tier for POC)
az appservice plan create \
  --name digitalsignage-plan \
  --resource-group digitalsignage-rg \
  --location eastus \
  --sku F1 \
  --is-linux

# Create Web App
az webapp create \
  --name digitalsignage-api \
  --resource-group digitalsignage-rg \
  --plan digitalsignage-plan \
  --runtime "DOTNET|8.0"

# Note: Web app name must be globally unique
# Your API will be at: https://digitalsignage-api.azurewebsites.net
```

**5. Document Connection Strings:**

Create a local file: `azure-credentials.txt` (DO NOT commit to git)

```text
=== AZURE CREDENTIALS ===

Resource Group: digitalsignage-rg
Location: eastus

--- SQL Database ---
Server: digitalsignage-sql-server.database.windows.net
Database: digitalsignage-db
Admin User: sqladmin
Admin Password: [Your password]

Connection String:
Server=tcp:digitalsignage-sql-server.database.windows.net,1433;Database=digitalsignage-db;User ID=sqladmin;Password=[password];Encrypt=true;Connection Timeout=30;

--- Blob Storage ---
Storage Account: digitalsignagestorage
Container: media

Connection String:
DefaultEndpointsProtocol=https;AccountName=digitalsignagestorage;AccountKey=[key];EndpointSuffix=core.windows.net

--- App Service ---
Web App Name: digitalsignage-api
URL: https://digitalsignage-api.azurewebsites.net
```

**6. Share credentials with PM:**

- Send the credentials to PM to add to password manager
- DO NOT post in Discord or commit to git

**Verification:**

- Go to Azure Portal: https://portal.azure.com
- Navigate to Resource Group "digitalsignage-rg"
- You should see:
  - SQL Server
  - SQL Database
  - Storage Account
  - App Service Plan
  - App Service

**Cost Estimate:**

- SQL Database (Basic): ~$5/month
- App Service (Free tier): $0
- Blob Storage: ~$0.02/GB
- **Total: ~$5-10/month**

---

## Week 1, Day 3-5 Tasks

### ✅ Task 9: Create .NET Backend Project

**Set up the ASP.NET Core Web API project with Clean Architecture**

**Steps:**

1. **Clone the backend repository:**

```bash
cd ~/projects  # or wherever you keep projects
git clone https://github.com/yourorg/yourproject-backend.git
cd yourproject-backend
```

2. **Create solution and projects:**

```bash
# Create solution
dotnet new sln -n DigitalSignage

# Create API project (Web API)
dotnet new webapi -n DigitalSignage.Api -o src/DigitalSignage.Api

# Create Core/Domain project (Class Library)
dotnet new classlib -n DigitalSignage.Core -o src/DigitalSignage.Core

# Create Infrastructure project (Class Library)
dotnet new classlib -n DigitalSignage.Infrastructure -o src/DigitalSignage.Infrastructure

# Add projects to solution
dotnet sln add src/DigitalSignage.Api/DigitalSignage.Api.csproj
dotnet sln add src/DigitalSignage.Core/DigitalSignage.Core.csproj
dotnet sln add src/DigitalSignage.Infrastructure/DigitalSignage.Infrastructure.csproj

# Set up project references
cd src/DigitalSignage.Api
dotnet add reference ../DigitalSignage.Core/DigitalSignage.Core.csproj
dotnet add reference ../DigitalSignage.Infrastructure/DigitalSignage.Infrastructure.csproj

cd ../DigitalSignage.Infrastructure
dotnet add reference ../DigitalSignage.Core/DigitalSignage.Core.csproj

cd ../../..
```

3. **Your folder structure should look like:**

```
yourproject-backend/
├── src/
│   ├── DigitalSignage.Api/          # Web API (Controllers, Startup)
│   ├── DigitalSignage.Core/         # Domain models, Interfaces
│   └── DigitalSignage.Infrastructure/ # EF Core, Repositories, Services
├── DigitalSignage.sln
├── .gitignore
├── README.md
└── LICENSE
```

4. **Install NuGet packages:**

**For Api project:**

```bash
cd src/DigitalSignage.Api

dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.AspNetCore.Authentication.JwtBearer
dotnet add package Swashbuckle.AspNetCore
dotnet add package Azure.Storage.Blobs
dotnet add package Serilog.AspNetCore
dotnet add package Serilog.Sinks.Console
```

**For Infrastructure project:**

```bash
cd ../DigitalSignage.Infrastructure

dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Tools
dotnet add package Azure.Storage.Blobs
dotnet add package BCrypt.Net-Next
```

**For Core project:**

```bash
cd ../DigitalSignage.Core

# No external packages needed for now (just domain models)
```

5. **Create folder structure:**

```bash
cd ../DigitalSignage.Core

# Create folders
mkdir Entities
mkdir Interfaces
mkdir Enums

cd ../DigitalSignage.Infrastructure

mkdir Data
mkdir Services
mkdir Repositories

cd ../DigitalSignage.Api

mkdir Controllers
mkdir DTOs
mkdir Middleware
```

6. **Verify everything builds:**

```bash
cd ../../..  # Back to solution root
dotnet build
```

Should see: "Build succeeded"

7. **Update appsettings.json** in Api project:

File: `src/DigitalSignage.Api/appsettings.json`

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=tcp:digitalsignage-sql-server.database.windows.net,1433;Database=digitalsignage-db;User ID=sqladmin;Password=YOUR_PASSWORD;Encrypt=true;Connection Timeout=30;",
    "BlobStorage": "YOUR_BLOB_STORAGE_CONNECTION_STRING"
  },
  "JwtSettings": {
    "SecretKey": "YOUR-SECRET-KEY-AT-LEAST-32-CHARACTERS-LONG-FOR-SECURITY",
    "Issuer": "DigitalSignageApi",
    "Audience": "DigitalSignageClient",
    "ExpirationMinutes": 1440
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*"
}
```

8. **Create appsettings.Development.json:**

File: `src/DigitalSignage.Api/appsettings.Development.json`

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "YOUR_LOCAL_CONNECTION_STRING_IF_DIFFERENT"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Debug",
      "Microsoft.AspNetCore": "Information"
    }
  }
}
```

9. **Add appsettings.json to .gitignore** (to avoid committing secrets):

Edit `.gitignore` and add:

```
# Sensitive config files
**/appsettings.json
**/appsettings.*.json
!**/appsettings.Development.Example.json
```

10. **Create example config file:**

File: `src/DigitalSignage.Api/appsettings.Development.Example.json`

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=YOUR_SQL_SERVER;Database=YOUR_DB;User ID=YOUR_USER;Password=YOUR_PASSWORD;",
    "BlobStorage": "YOUR_BLOB_CONNECTION_STRING"
  },
  "JwtSettings": {
    "SecretKey": "GENERATE-A-LONG-RANDOM-SECRET-KEY-HERE",
    "Issuer": "DigitalSignageApi",
    "Audience": "DigitalSignageClient",
    "ExpirationMinutes": 1440
  }
}
```

11. **Commit initial project structure:**

```bash
git add .
git commit -m "Initial project structure with Clean Architecture"
git push origin main
```

---

### ✅ Task 10: Create Entity Framework Core Models

**Create the database entities**

**Steps:**

1. **Create Enums:**

File: `src/DigitalSignage.Core/Enums/MediaType.cs`

```csharp
namespace DigitalSignage.Core.Enums;

public enum MediaType
{
    Image = 1,
    Video = 2
}
```

2. **Create Entities:**

File: `src/DigitalSignage.Core/Entities/User.cs`

```csharp
namespace DigitalSignage.Core.Entities;

public class User
{
    public Guid Id { get; set; }
    public string Email { get; set; } = string.Empty;
    public string PasswordHash { get; set; } = string.Empty;
    public DateTime CreatedAt { get; set; }

    // Navigation properties
    public ICollection<Device> Devices { get; set; } = new List<Device>();
    public ICollection<Media> MediaFiles { get; set; } = new List<Media>();
    public ICollection<Schedule> Schedules { get; set; } = new List<Schedule>();
}
```

File: `src/DigitalSignage.Core/Entities/Device.cs`

```csharp
namespace DigitalSignage.Core.Entities;

public class Device
{
    public Guid Id { get; set; }
    public Guid UserId { get; set; }
    public string? PairingCode { get; set; }
    public string? DeviceUuid { get; set; }
    public string Name { get; set; } = "Unnamed Device";
    public bool IsPaired { get; set; }
    public DateTime? LastHeartbeat { get; set; }
    public DateTime CreatedAt { get; set; }
    public DateTime? PairingCodeExpiresAt { get; set; }

    // Navigation properties
    public User User { get; set; } = null!;
    public ICollection<Schedule> Schedules { get; set; } = new List<Schedule>();
}
```

File: `src/DigitalSignage.Core/Entities/Media.cs`

```csharp
using DigitalSignage.Core.Enums;

namespace DigitalSignage.Core.Entities;

public class Media
{
    public Guid Id { get; set; }
    public Guid UserId { get; set; }
    public string FileName { get; set; } = string.Empty;
    public MediaType FileType { get; set; }
    public string BlobUrl { get; set; } = string.Empty;
    public string? ThumbnailUrl { get; set; }
    public long SizeInBytes { get; set; }
    public int? DurationSeconds { get; set; }
    public DateTime UploadedAt { get; set; }

    // Navigation properties
    public User User { get; set; } = null!;
    public ICollection<ScheduleItem> ScheduleItems { get; set; } = new List<ScheduleItem>();
}
```

File: `src/DigitalSignage.Core/Entities/Schedule.cs`

```csharp
namespace DigitalSignage.Core.Entities;

public class Schedule
{
    public Guid Id { get; set; }
    public Guid UserId { get; set; }
    public Guid DeviceId { get; set; }
    public string Name { get; set; } = string.Empty;
    public bool IsActive { get; set; }
    public string Timezone { get; set; } = "UTC";
    public DateTime CreatedAt { get; set; }
    public DateTime UpdatedAt { get; set; }

    // Navigation properties
    public User User { get; set; } = null!;
    public Device Device { get; set; } = null!;
    public ICollection<ScheduleItem> Items { get; set; } = new List<ScheduleItem>();
}
```

File: `src/DigitalSignage.Core/Entities/ScheduleItem.cs`

```csharp
namespace DigitalSignage.Core.Entities;

public class ScheduleItem
{
    public Guid Id { get; set; }
    public Guid ScheduleId { get; set; }
    public Guid MediaId { get; set; }
    public int DisplayOrder { get; set; }
    public TimeSpan StartTime { get; set; }  // Time of day (e.g., 09:00)
    public TimeSpan EndTime { get; set; }     // Time of day (e.g., 17:00)
    public int DisplayDuration { get; set; }  // Seconds to display

    // Navigation properties
    public Schedule Schedule { get; set; } = null!;
    public Media Media { get; set; } = null!;
}
```

File: `src/DigitalSignage.Core/Entities/DeviceHeartbeat.cs`

```csharp
namespace DigitalSignage.Core.Entities;

public class DeviceHeartbeat
{
    public Guid Id { get; set; }
    public Guid DeviceId { get; set; }
    public DateTime Timestamp { get; set; }
    public string? PlayerVersion { get; set; }
    public Guid? CurrentMediaId { get; set; }
    public string? IpAddress { get; set; }
    public string? ErrorMessage { get; set; }

    // Navigation property
    public Device Device { get; set; } = null!;
}
```

3. **Create DbContext:**

File: `src/DigitalSignage.Infrastructure/Data/AppDbContext.cs`

```csharp
using Microsoft.EntityFrameworkCore;
using DigitalSignage.Core.Entities;

namespace DigitalSignage.Infrastructure.Data;

public class AppDbContext : DbContext
{
    public AppDbContext(DbContextOptions<AppDbContext> options) : base(options)
    {
    }

    public DbSet<User> Users { get; set; }
    public DbSet<Device> Devices { get; set; }
    public DbSet<Media> MediaFiles { get; set; }
    public DbSet<Schedule> Schedules { get; set; }
    public DbSet<ScheduleItem> ScheduleItems { get; set; }
    public DbSet<DeviceHeartbeat> DeviceHeartbeats { get; set; }

    protected override void OnModelCreating(ModelBuilder modelBuilder)
    {
        base.OnModelCreating(modelBuilder);

        // User configuration
        modelBuilder.Entity<User>(entity =>
        {
            entity.HasKey(e => e.Id);
            entity.HasIndex(e => e.Email).IsUnique();
            entity.Property(e => e.Email).IsRequired().HasMaxLength(255);
            entity.Property(e => e.PasswordHash).IsRequired();
        });

        // Device configuration
        modelBuilder.Entity<Device>(entity =>
        {
            entity.HasKey(e => e.Id);
            entity.HasIndex(e => e.DeviceUuid).IsUnique();
            entity.HasIndex(e => e.PairingCode);
            entity.Property(e => e.Name).HasMaxLength(255);

            entity.HasOne(e => e.User)
                .WithMany(u => u.Devices)
                .HasForeignKey(e => e.UserId)
                .OnDelete(DeleteBehavior.Cascade);
        });

        // Media configuration
        modelBuilder.Entity<Media>(entity =>
        {
            entity.HasKey(e => e.Id);
            entity.Property(e => e.FileName).IsRequired().HasMaxLength(500);
            entity.Property(e => e.BlobUrl).IsRequired();

            entity.HasOne(e => e.User)
                .WithMany(u => u.MediaFiles)
                .HasForeignKey(e => e.UserId)
                .OnDelete(DeleteBehavior.Cascade);
        });

        // Schedule configuration
        modelBuilder.Entity<Schedule>(entity =>
        {
            entity.HasKey(e => e.Id);
            entity.Property(e => e.Name).IsRequired().HasMaxLength(255);

            entity.HasOne(e => e.User)
                .WithMany(u => u.Schedules)
                .HasForeignKey(e => e.UserId)
                .OnDelete(DeleteBehavior.Restrict);

            entity.HasOne(e => e.Device)
                .WithMany(d => d.Schedules)
                .HasForeignKey(e => e.DeviceId)
                .OnDelete(DeleteBehavior.Cascade);
        });

        // ScheduleItem configuration
        modelBuilder.Entity<ScheduleItem>(entity =>
        {
            entity.HasKey(e => e.Id);

            entity.HasOne(e => e.Schedule)
                .WithMany(s => s.Items)
                .HasForeignKey(e => e.ScheduleId)
                .OnDelete(DeleteBehavior.Cascade);

            entity.HasOne(e => e.Media)
                .WithMany(m => m.ScheduleItems)
                .HasForeignKey(e => e.MediaId)
                .OnDelete(DeleteBehavior.Restrict);
        });

        // DeviceHeartbeat configuration
        modelBuilder.Entity<DeviceHeartbeat>(entity =>
        {
            entity.HasKey(e => e.Id);
            entity.HasIndex(e => e.Timestamp);

            entity.HasOne(e => e.Device)
                .WithMany()
                .HasForeignKey(e => e.DeviceId)
                .OnDelete(DeleteBehavior.Cascade);
        });
    }
}
```

4. **Update Program.cs to register DbContext:**

File: `src/DigitalSignage.Api/Program.cs`

```csharp
using Microsoft.EntityFrameworkCore;
using DigitalSignage.Infrastructure.Data;

var builder = WebApplication.CreateBuilder(args);

// Add services to the container
builder.Services.AddControllers();
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();

// Add DbContext
builder.Services.AddDbContext<AppDbContext>(options =>
    options.UseSqlServer(
        builder.Configuration.GetConnectionString("DefaultConnection")));

// Add CORS for frontend
builder.Services.AddCors(options =>
{
    options.AddPolicy("AllowFrontend",
        policy =>
        {
            policy.AllowAnyOrigin()
                  .AllowAnyMethod()
                  .AllowAnyHeader();
        });
});

var app = builder.Build();

// Configure the HTTP request pipeline
if (app.Environment.IsDevelopment())
{
    app.UseSwagger();
    app.UseSwaggerUI();
}

app.UseHttpsRedirection();
app.UseCors("AllowFrontend");
app.UseAuthorization();
app.MapControllers();

app.Run();
```

5. **Create initial migration:**

```bash
cd src/DigitalSignage.Api

dotnet ef migrations add InitialCreate \
  --project ../DigitalSignage.Infrastructure/DigitalSignage.Infrastructure.csproj \
  --startup-project DigitalSignage.Api.csproj \
  --context AppDbContext

# Apply migration to Azure database
dotnet ef database update \
  --project ../DigitalSignage.Infrastructure/DigitalSignage.Infrastructure.csproj \
  --startup-project DigitalSignage.Api.csproj \
  --context AppDbContext
```

**If migration succeeds, you should see:**

- "Done." message
- Database created in Azure

6. **Verify in Azure:**
   - Go to Azure Portal
   - Navigate to your SQL Database
   - Click "Query editor"
   - Login with sqladmin credentials
   - Run: `SELECT * FROM INFORMATION_SCHEMA.TABLES`
   - You should see all your tables

7. **Commit changes:**

```bash
git add .
git commit -m "Add Entity Framework Core models and initial migration"
git push origin main
```

---

### ✅ Task 11: Implement JWT Authentication

**Create authentication endpoints**

**Steps:**

1. **Create DTOs:**

File: `src/DigitalSignage.Api/DTOs/RegisterRequest.cs`

```csharp
using System.ComponentModel.DataAnnotations;

namespace DigitalSignage.Api.DTOs;

public class RegisterRequest
{
    [Required]
    [EmailAddress]
    public string Email { get; set; } = string.Empty;

    [Required]
    [MinLength(8)]
    public string Password { get; set; } = string.Empty;
}
```

File: `src/DigitalSignage.Api/DTOs/LoginRequest.cs`

```csharp
using System.ComponentModel.DataAnnotations;

namespace DigitalSignage.Api.DTOs;

public class LoginRequest
{
    [Required]
    [EmailAddress]
    public string Email { get; set; } = string.Empty;

    [Required]
    public string Password { get; set; } = string.Empty;
}
```

File: `src/DigitalSignage.Api/DTOs/AuthResponse.cs`

```csharp
namespace DigitalSignage.Api.DTOs;

public class AuthResponse
{
    public string Token { get; set; } = string.Empty;
    public string Email { get; set; } = string.Empty;
    public DateTime ExpiresAt { get; set; }
}
```

2. **Create JWT Service Interface:**

File: `src/DigitalSignage.Core/Interfaces/IJwtService.cs`

```csharp
using DigitalSignage.Core.Entities;

namespace DigitalSignage.Core.Interfaces;

public interface IJwtService
{
    string GenerateToken(User user);
    Guid? ValidateToken(string token);
}
```

3. **Implement JWT Service:**

File: `src/DigitalSignage.Infrastructure/Services/JwtService.cs`

```csharp
using System.IdentityModel.Tokens.Jwt;
using System.Security.Claims;
using System.Text;
using Microsoft.Extensions.Configuration;
using Microsoft.IdentityModel.Tokens;
using DigitalSignage.Core.Entities;
using DigitalSignage.Core.Interfaces;

namespace DigitalSignage.Infrastructure.Services;

public class JwtService : IJwtService
{
    private readonly IConfiguration _configuration;

    public JwtService(IConfiguration configuration)
    {
        _configuration = configuration;
    }

    public string GenerateToken(User user)
    {
        var securityKey = new SymmetricSecurityKey(
            Encoding.UTF8.GetBytes(_configuration["JwtSettings:SecretKey"]!));
        var credentials = new SigningCredentials(securityKey, SecurityAlgorithms.HmacSha256);

        var claims = new[]
        {
            new Claim(JwtRegisteredClaimNames.Sub, user.Id.ToString()),
            new Claim(JwtRegisteredClaimNames.Email, user.Email),
            new Claim(JwtRegisteredClaimNames.Jti, Guid.NewGuid().ToString())
        };

        var token = new JwtSecurityToken(
            issuer: _configuration["JwtSettings:Issuer"],
            audience: _configuration["JwtSettings:Audience"],
            claims: claims,
            expires: DateTime.UtcNow.AddMinutes(
                Convert.ToDouble(_configuration["JwtSettings:ExpirationMinutes"])),
            signingCredentials: credentials
        );

        return new JwtSecurityTokenHandler().WriteToken(token);
    }

    public Guid? ValidateToken(string token)
    {
        try
        {
            var tokenHandler = new JwtSecurityTokenHandler();
            var key = Encoding.UTF8.GetBytes(_configuration["JwtSettings:SecretKey"]!);

            tokenHandler.ValidateToken(token, new TokenValidationParameters
            {
                ValidateIssuerSigningKey = true,
                IssuerSigningKey = new SymmetricSecurityKey(key),
                ValidateIssuer = true,
                ValidIssuer = _configuration["JwtSettings:Issuer"],
                ValidateAudience = true,
                ValidAudience = _configuration["JwtSettings:Audience"],
                ValidateLifetime = true,
                ClockSkew = TimeSpan.Zero
            }, out SecurityToken validatedToken);

            var jwtToken = (JwtSecurityToken)validatedToken;
            var userId = Guid.Parse(jwtToken.Claims.First(x => x.Type == JwtRegisteredClaimNames.Sub).Value);

            return userId;
        }
        catch
        {
            return null;
        }
    }
}
```

4. **Create Auth Controller:**

File: `src/DigitalSignage.Api/Controllers/AuthController.cs`

```csharp
using Microsoft.AspNetCore.Mvc;
using Microsoft.EntityFrameworkCore;
using DigitalSignage.Api.DTOs;
using DigitalSignage.Core.Entities;
using DigitalSignage.Core.Interfaces;
using DigitalSignage.Infrastructure.Data;

namespace DigitalSignage.Api.Controllers;

[ApiController]
[Route("api/[controller]")]
public class AuthController : ControllerBase
{
    private readonly AppDbContext _context;
    private readonly IJwtService _jwtService;

    public AuthController(AppDbContext context, IJwtService jwtService)
    {
        _context = context;
        _jwtService = jwtService;
    }

    [HttpPost("register")]
    public async Task<ActionResult<AuthResponse>> Register(RegisterRequest request)
    {
        // Check if user exists
        if (await _context.Users.AnyAsync(u => u.Email == request.Email))
        {
            return BadRequest(new { message = "User already exists" });
        }

        // Hash password
        var passwordHash = BCrypt.Net.BCrypt.HashPassword(request.Password);

        // Create user
        var user = new User
        {
            Id = Guid.NewGuid(),
            Email = request.Email,
            PasswordHash = passwordHash,
            CreatedAt = DateTime.UtcNow
        };

        _context.Users.Add(user);
        await _context.SaveChangesAsync();

        // Generate token
        var token = _jwtService.GenerateToken(user);
        var expiresAt = DateTime.UtcNow.AddMinutes(1440);

        return Ok(new AuthResponse
        {
            Token = token,
            Email = user.Email,
            ExpiresAt = expiresAt
        });
    }

    [HttpPost("login")]
    public async Task<ActionResult<AuthResponse>> Login(LoginRequest request)
    {
        // Find user
        var user = await _context.Users.FirstOrDefaultAsync(u => u.Email == request.Email);

        if (user == null || !BCrypt.Net.BCrypt.Verify(request.Password, user.PasswordHash))
        {
            return Unauthorized(new { message = "Invalid email or password" });
        }

        // Generate token
        var token = _jwtService.GenerateToken(user);
        var expiresAt = DateTime.UtcNow.AddMinutes(1440);

        return Ok(new AuthResponse
        {
            Token = token,
            Email = user.Email,
            ExpiresAt = expiresAt
        });
    }
}
```

5. **Register JWT in Program.cs:**

Update `src/DigitalSignage.Api/Program.cs`:

```csharp
using Microsoft.EntityFrameworkCore;
using Microsoft.AspNetCore.Authentication.JwtBearer;
using Microsoft.IdentityModel.Tokens;
using System.Text;
using DigitalSignage.Infrastructure.Data;
using DigitalSignage.Core.Interfaces;
using DigitalSignage.Infrastructure.Services;

var builder = WebApplication.CreateBuilder(args);

// Add services
builder.Services.AddControllers();
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();

// DbContext
builder.Services.AddDbContext<AppDbContext>(options =>
    options.UseSqlServer(builder.Configuration.GetConnectionString("DefaultConnection")));

// JWT Service
builder.Services.AddScoped<IJwtService, JwtService>();

// JWT Authentication
builder.Services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
    .AddJwtBearer(options =>
    {
        options.TokenValidationParameters = new TokenValidationParameters
        {
            ValidateIssuerSigningKey = true,
            IssuerSigningKey = new SymmetricSecurityKey(
                Encoding.UTF8.GetBytes(builder.Configuration["JwtSettings:SecretKey"]!)),
            ValidateIssuer = true,
            ValidIssuer = builder.Configuration["JwtSettings:Issuer"],
            ValidateAudience = true,
            ValidAudience = builder.Configuration["JwtSettings:Audience"],
            ValidateLifetime = true,
            ClockSkew = TimeSpan.Zero
        };
    });

// CORS
builder.Services.AddCors(options =>
{
    options.AddPolicy("AllowFrontend",
        policy => policy.AllowAnyOrigin().AllowAnyMethod().AllowAnyHeader());
});

var app = builder.Build();

if (app.Environment.IsDevelopment())
{
    app.UseSwagger();
    app.UseSwaggerUI();
}

app.UseHttpsRedirection();
app.UseCors("AllowFrontend");
app.UseAuthentication();
app.UseAuthorization();
app.MapControllers();

app.Run();
```

6. **Test the API:**

Run the API:

```bash
cd src/DigitalSignage.Api
dotnet run
```

Open browser: `https://localhost:7XXX/swagger` (port will be shown in console)

Test register and login endpoints in Swagger UI.

7. **Commit:**

```bash
git add .
git commit -m "Implement JWT authentication (register/login)"
git push origin main
```

### ✅ Task 12: Deploy Frontend to Azure Static Web Apps

**Deploy the frontend to Azure**

**Steps:**

1. **Create Azure Static Web App:**

```bash
# Login to Azure (if not already)
az login

# Create Static Web App
az staticwebapp create \
  --name digitalsignage-frontend \
  --resource-group digitalsignage-rg \
  --source https://github.com/yourorg/yourproject-frontend \
  --location "East US 2" \
  --branch main \
  --app-location "/" \
  --output-location "dist" \
  --login-with-github
```

This will:

- Create Azure Static Web App
- Set up GitHub Actions for automatic deployment
- Ask you to authorize GitHub

2. **Get deployment token:**

```bash
az staticwebapp secrets list \
  --name digitalsignage-frontend \
  --resource-group digitalsignage-rg
```

Copy the `token` value (you'll need this for GitHub Actions)

3. **Verify GitHub Action was created:**

- Go to your GitHub repository
- Click "Actions" tab
- You should see a workflow file created automatically

If not created automatically, create manually:

File: `.github/workflows/azure-static-web-apps.yml`

```yaml
name: Azure Static Web Apps CI/CD

on:
  push:
    branches:
      - main
  pull_request:
    branches:
      - main

jobs:
  build_and_deploy:
    runs-on: ubuntu-latest
    name: Build and Deploy
    steps:
      - uses: actions/checkout@v3

      - name: Build And Deploy
        uses: Azure/static-web-apps-deploy@v1
        with:
          azure_static_web_apps_api_token: ${{ secrets.AZURE_STATIC_WEB_APPS_API_TOKEN }}
          repo_token: ${{ secrets.GITHUB_TOKEN }}
          action: "upload"
          app_location: "/"
          output_location: "dist"
```

4. **Add deployment token to GitHub secrets:**

- Go to GitHub repository
- Settings > Secrets and variables > Actions
- Click "New repository secret"
- Name: `AZURE_STATIC_WEB_APPS_API_TOKEN`
- Value: Paste the token from step 2
- Click "Add secret"

5. **Push to trigger deployment:**

```bash
git add .
git commit -m "Add Azure Static Web Apps deployment"
git push origin main
```

6. **Monitor deployment:**

- Go to GitHub repository > Actions tab
- Watch the workflow run
- Should complete in 2-3 minutes

7. **Get your website URL:**

```bash
az staticwebapp show \
  --name digitalsignage-frontend \
  --resource-group digitalsignage-rg \
  --query "defaultHostname" \
  --output tsv
```

Your frontend will be at: `https://digitalsignage-frontend.azurestaticapps.net`

8. **Update environment variable for production:**

Create: `.env.production`

```bash
VITE_API_URL=https://digitalsignage-api.azurewebsites.net/api
```

## Commit and push again.

## Next Steps Summary

You've completed the foundational setup! Here's what's been done:

✅ GitHub repositories created
✅ Issue templates set up
✅ Azure resources provisioned
✅ .NET project structure created
✅ Database models and migrations
✅ JWT authentication implemented

**Next tasks (Sprint 1 continuation):**

- Device pairing endpoints
- Media upload to Blob Storage
- Schedule management APIs
- Player heartbeat endpoint

**Estimated time for all tasks above:** 2-3 days
