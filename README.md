# Downgrader111

A user-friendly tool for Fallout 4 players to switch between different game versions using delta patches.

## About

Fallout 4 players often have different preferences for which version of the game they want to play. Some prefer older versions for mod compatibility, while others need the latest updates. Downgrader111 makes switching between versions simple and safe.

### Supported Applications
- **Fallout 4** - The main game executable and related files
- **Creation Kit** - Bethesda's official modding tool for Fallout 4

## Features

- Clean, modern interface built with Avalonia UI
- Apply delta patches to upgrade or downgrade game versions
- Automatic backup of original files before patching
- Version detection for installed games
- Progress tracking during patch operations
- Support for both Steam and GOG installations

## Requirements

- Windows 10/11 (64-bit)
- .NET 10.0 Runtime
- Fallout 4 and optionally Creation Kit installed

## Installation

1. Download the latest release from the [Releases](../../releases) page
2. Extract to a folder of your choice
3. Run `Downgrader111.Desktop.exe`

## Usage

1. Launch Downgrader111
2. The application will automatically detect your Fallout 4 installation
3. Select your desired target version
4. Click "Apply Patch" and wait for the process to complete
5. Launch Fallout 4 as usual

## Building from Source

### Prerequisites
- [.NET 10.0 SDK](https://dotnet.microsoft.com/download)

### Build
```bash
git clone https://github.com/yourusername/Downgrader111.git
cd Downgrader111
dotnet build
```

### Run
```bash
dotnet run --project Downgrader111.Desktop
```

## How It Works

Downgrader111 uses delta patching technology to efficiently convert game files between versions. Instead of downloading entire game files, only the differences (deltas) between versions are needed, resulting in much smaller download sizes.

## License

[GPL-3.0 or later](LICENSE)

## Disclaimer

This tool is provided as-is for personal use. Always ensure you own a legitimate copy of Fallout 4. Bethesda Game Studios and Bethesda Softworks are trademarks of ZeniMax Media Inc. This project is not affiliated with or endorsed by Bethesda or ZeniMax.
