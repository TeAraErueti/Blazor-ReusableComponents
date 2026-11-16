# Blazor Reusable Components – Razor Class Library

## Overview

This project demonstrates how to create and use a reusable Razor component library in ASP.NET Core Blazor.

The project was developed as part of a Microsoft Learn tutorial for BYU–Idaho CSE325. It demonstrates how to build a reusable modal dialog component, package it as a NuGet package, and consume it in a separate Blazor Web App.

## Project Objectives

- Create a reusable Razor Class Library.
- Develop a reusable modal dialog component using Razor.
- Apply component-specific CSS styling.
- Configure and package a Razor Class Library as a NuGet package.
- Reference and use the reusable component in a separate Blazor Web App.

## Technologies Used

- C#
- ASP.NET Core Blazor
- Razor Components
- .NET 8
- HTML and CSS
- NuGet Package Manager
- Visual Studio Code
- Git and GitHub

## Project Structure

The solution contains two main projects:

### 1. FirstClassLibrary

A Razor Class Library containing the reusable components.

Key files:

- `Modal.razor` – The reusable modal dialog component.
- `Modal.razor.css` – Component-specific styling.
- `FirstClassLibrary.csproj` – Project configuration and NuGet package metadata.

### 2. MyBlazorApp

A Blazor Web App that consumes and displays the reusable modal component.

Key files:

- `Components/Pages/Home.razor` – Displays the modal component.
- `Components/_Imports.razor` – Imports the reusable component namespace.
- `MyBlazorApp.csproj` – Contains the NuGet package reference.

## Modal Component Features

The reusable `Modal` component includes:

- Customisable dialog title.
- Configurable Cancel and Confirm button text.
- Child content that can be supplied by the parent component.
- Show and hide functionality.
- Cancel and Confirm event callbacks.
- Custom CSS styling and animations.

### Example Usage

```razor
<Modal Title="My first Modal dialog" Show="true">
    <p>
        This is my first modal dialog
    </p>
</Modal>
```

## NuGet Package

The Razor Class Library is packaged using NuGet.

**Package ID:** `My.FirstClassLibrary`

**Version:** `0.1.0`

The package is used by `MyBlazorApp` to access the reusable modal component without requiring a direct project reference.

## Running the Application

### Prerequisites

- .NET 8 SDK or later.
- Visual Studio Code or another compatible development environment.

### Build the Razor Class Library

From the solution root directory, run:

```powershell
dotnet pack FirstClassLibrary -c Release
```

This generates the NuGet package in:

`FirstClassLibrary/bin/Release`

### Run the Blazor Web App

The application consumes the local NuGet package. When setting up a fresh clone, make sure the local package source is configured for NuGet restore.

Navigate to the application directory:

```powershell
cd MyBlazorApp
```

Restore dependencies using the local package folder and NuGet.org:

```powershell
dotnet restore --source ../FirstClassLibrary/bin/Release --source https://api.nuget.org/v3/index.json
```

Run the application:

```powershell
dotnet run
```

Open the localhost address displayed in the terminal to view the application.

## Learning Outcomes

Through this project, I gained practical experience in:

- Creating reusable Razor components.
- Developing and styling component libraries.
- Working with component parameters and event callbacks.
- Creating NuGet packages.
- Integrating reusable components into Blazor applications.
- Managing projects and source code using Git and GitHub.

## Author

**Te Ara Erueti**

GitHub: [@TeAraErueti](https://github.com/TeAraErueti)

---

*Developed as part of BYU–Idaho CSE325 coursework.*
