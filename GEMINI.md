# Downgrader111 - Avalonia UI Project

## Project Overview
Downgrader111 is a cross-platform desktop application built using the **Avalonia UI** framework and **.NET**. It follows the Model-View-ViewModel (MVVM) architectural pattern.

### Tech Stack
- **Framework:** Avalonia UI
- **Language:** C#
- **Core Runtime:** .NET 10.0
- **Desktop Runtime:** .NET 10.0 (Windows specific target configured)
- **MVVM Library:** ReactiveUI (included via Avalonia.ReactiveUI)

## Project Structure
The solution is divided into two main projects:

1.  **`Downgrader111` (Core)**
    -   Contains the shared application logic, ViewModels, Views, and Styles.
    -   Target Framework: `net10.0`
    -   Key Directories:
        -   `ViewModels/`: Contains the logic for the UI (e.g., `MainViewModel.cs`).
        -   `Views/`: Contains the UI definitions (AXAML files like `MainView.axaml`).
        -   `Assets/`: Static assets like icons.

2.  **`Downgrader111.Desktop` (Head)**
    -   The entry point for the desktop application.
    -   Target Framework: `net10.0-windows10.0.19041.0`
    -   Contains `Program.cs` which sets up the Avalonia AppBuilder.

## Development Commands

### Building the Project
To build the entire solution:
```bash
dotnet build
```

### Running the Application
To run the desktop application:
```bash
dotnet run --project Downgrader111.Desktop
```

### Testing
*Currently, no separate test project was detected in the root listing. Ensure to add one if testing logic becomes necessary.*

## Coding Conventions
-   **MVVM:** Strict adherence to MVVM is encouraged. Logic should reside in ViewModels (`ViewModels/`), and UI in Views (`Views/`).
-   **ReactiveUI:** The project references `Avalonia.ReactiveUI`. Use `ReactiveObject` for ViewModels to support property change notifications.
-   **Compiled Bindings:** `AvaloniaUseCompiledBindingsByDefault` is set to `true`. Use specific types in XAML `x:DataType` for better performance and compile-time checking.
-   **Nullability:** Nullable reference types are enabled (`<Nullable>enable</Nullable>`).

## Key Files
-   `Downgrader111.slnx`: The solution file managing the project references.
-   `Downgrader111/App.axaml`: The main application definition and global styles/resources.
-   `Downgrader111/ViewModels/ViewModelBase.cs`: The base class for all ViewModels.
