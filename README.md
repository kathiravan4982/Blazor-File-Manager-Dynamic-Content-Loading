# Change Blazor File Manager content for the different users

**Repository Description**
This repository contains a **Blazor sample application** that demonstrates how to **change the content displayed in the Syncfusion Blazor File Manager for different users**.

The project provides a quick getting‑started setup where the File Manager content can vary based on user context, enabling user‑specific file views within a Blazor application.

## Project Overview
The purpose of this project is to help developers understand how to configure the Syncfusion **Blazor File Manager** so that different users see different file content. This is useful for scenarios that require per‑user file access, role‑based views, or customized content presentation.

The solution is a hosted Blazor WebAssembly app on **.NET 10**, with the following projects:

| Project | Description |
|---|---|
| `Demo.Server` | ASP.NET Core host serving the WASM client and the File Manager API (`api/Mail`) backed by a physical file provider |
| `Demo.Client` | Blazor WebAssembly frontend with the Syncfusion File Manager and DropDownList components |
| `Demo.Shared` | Shared data access layer (EF Core + SQL Server LocalDB `NORTHWND.MDF`) used to track the signed‑in user |

## Features
- Integration of **Syncfusion Blazor File Manager** (v35.1.42)
- Display different file content for different users
- User‑specific file browsing experience
- Hosted Blazor WebAssembly app on **.NET 10** with the latest project folder structure

## Prerequisites
Ensure the following requirements are met before running this project:
- Visual Studio 2022 (v17.12 or later) or Visual Studio Code with the C# Dev Kit
- **.NET 10.0 SDK**
- **SQL Server LocalDB** (ships with Visual Studio) — the sample database `NORTHWND.MDF` is included in `Shared/App_Data`
- Syncfusion Blazor packages (restored automatically from NuGet)
- Valid Syncfusion license key (if required)

## How to run the sample
1. **Clone the repository**
```bash
git clone https://github.com/kathiravan4982/Blazor-File-Manager-Dynamic-Content-Loading.git
```
2. **Open the solution** — open `Demo.sln` in Visual Studio 2022, or the repository folder in VS Code.
3. **Restore the NuGet packages** — rebuild the solution (`dotnet restore` happens automatically on build, or run `dotnet restore`).
4. **Run the Server project** (`Demo.Server` is the startup project):
   - Visual Studio: press `Ctrl+F5`
   - .NET CLI: `dotnet run --project Server`
5. Once the application starts, the Blazor File Manager displays the files of the currently signed‑in user. Use the **Signed in** DropDownList to switch between User 1, User 2, and User 3 — the File Manager content reloads to show that user's folders (`wwwroot/Files/User 1`, `User 2`, `User 3`).

> **Note:** The user selection is persisted in the included `NORTHWND.MDF` SQL Server LocalDB database via Entity Framework Core. The connection string is resolved relative to the repository folder, so no path edits are required after cloning. LocalDB is only available on Windows; on other platforms, update the connection string in `Shared/DataAccess/UserContext.cs` to point to a SQL Server instance.

## Configuration
The logic for displaying different content per user is implemented within the Blazor application. You can extend this logic to:
- Load user‑specific files
- Apply role‑based access rules
- Customize File Manager behavior per user

## Documentation
- Blazor File Manager – Getting Started with WebAssembly App (used for this .NET 10 upgrade):
https://help.syncfusion.com/file-manager-sdk/blazor/getting-started-with-wasm-app
- Blazor File Manager – Getting Started with Blazor Web App:
https://help.syncfusion.com/file-manager-sdk/blazor/getting-started-with-web-app
- Blazor Introduction:
https://blazor.syncfusion.com/documentation/introduction
- General Syncfusion documentation:
https://help.syncfusion.com/

## Additional Resources
- Syncfusion Blazor File Manager product overview:
https://www.syncfusion.com/blazor-components/blazor-file-manager

## Troubleshooting
- Ensure NuGet packages are restored successfully.
- Verify that SQL Server LocalDB is installed and running (`sqllocaldb info` in a terminal). The sample database file is `Shared/App_Data/NORTHWND.MDF`.
- Verify that the Syncfusion license key is registered.
- Rebuild the solution if changes are not reflected.
- Check application logs for runtime errors.

## Support
For detailed API references, user‑specific configuration guidance, and advanced Blazor File Manager scenarios, refer to the Syncfusion Blazor documentation links provided above.
