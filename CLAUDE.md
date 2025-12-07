# Downgrader111 - Development Guide

## Project Overview

Downgrader111 is an Avalonia UI application that allows Fallout 4 players to apply delta patches to switch between different versions of the game and the Creation Kit (Bethesda's official modding tool).

## Technology Stack

- **Framework**: .NET 10.0
- **UI Framework**: Avalonia 11.3.9
- **Architecture**: MVVM (Model-View-ViewModel) using ReactiveUI
- **Theme**: Fluent Design

## Project Structure

```
Downgrader111/
├── Downgrader111/           # Shared library (ViewModels, Models, Services)
│   ├── Assets/              # Application resources (icons, images)
│   ├── Models/              # Data models
│   ├── ViewModels/          # MVVM ViewModels
│   ├── Views/               # Avalonia XAML views
│   └── Services/            # Business logic and patching services
├── Downgrader111.Desktop/   # Desktop-specific entry point
└── Directory.Build.props    # Shared MSBuild properties
```

## Architecture Guidelines

### MVVM Pattern
- **Models**: Plain data classes representing patch metadata, version info, etc.
- **ViewModels**: Inherit from `ReactiveObject`, use `ReactiveCommand` for actions
- **Views**: AXAML files with compiled bindings (`{CompiledBinding}`)

### Naming Conventions
- ViewModels: `*ViewModel.cs` (e.g., `MainWindowViewModel.cs`)
- Views: `*View.axaml` or `*Window.axaml`
- Services: `I*Service.cs` for interfaces, `*Service.cs` for implementations

## Build & Run

```bash
# Build the solution
dotnet build

# Run the desktop application
dotnet run --project Downgrader111.Desktop
```

## Key Features to Implement

1. **Version Detection**: Detect current Fallout 4 and Creation Kit versions
2. **Patch Management**: Download and manage delta patches
3. **Patch Application**: Apply/revert patches using binary diff algorithms
4. **Backup System**: Backup original files before patching
5. **Progress Reporting**: Show detailed progress during patch operations

## Development Notes

- Use `ObservableCollection<T>` for lists bound to UI
- Prefer `async/await` for all I/O operations
- Delta patching will use xdelta3 or similar algorithm
- Consider Steam and GOG installation paths for auto-detection
