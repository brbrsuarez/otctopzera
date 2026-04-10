# OTCTOPZERA Launcher (corrigido)

Este pacote já vem apontando para `brbrsuarez/otctopzera`, usando `launcher_config.json` híbrido e suporte a `otclient.exe`.


<img width="699" height="577" alt="image" src="https://github.com/user-attachments/assets/fcb2f7de-9745-4023-ab03-9a520065b7ae" />


# 🎮 Tibia Launcher -- **📱 Modern Interface**: Beautiful PySide6/Qt GUI with real-time progress tracking
- **🔄 Self-Updating Launcher**: Launcher automatically updates itself when new versions available
- **🗺️ Minimap Downloads**: Built-in minimap downloader with multiple options
- **📊 Version Tracking**: Enhanced semantic versioning with clear status indicators
- **💻 Thread-Safe Design**: Modern Qt architecture prevents freezing during downloads
- **🐍 Python-Powered**: Written in Python 3.12+ for easy customization and cross-platform support

A modern, easy-to-configure launcher for Tibia private servers built with **Python** and **PySide6**, featuring automatic updates and a beautiful Qt-based interface.

## 📋 Table of Contents

- [✨ Features](#-features)
- [🚀 Quick Start (For Server Owners)](#-quick-start-for-server-owners)
- [📥 Installation Guide (For Users)](#-installation-guide-for-users)
- [⚙️ Configuration Guide (For Developers)](#%EF%B8%8F-configuration-guide-for-developers)
- [🔧 Advanced Setup](#-advanced-setup)
- [🐛 Troubleshooting](#-troubleshooting)
- [📝 License](#-license)

---

## ✨ Features

- **🔄 Fully Automatic Updates**: Detects and prompts for updates on startup and every 2 hours
- **🎯 Zero-Configuration for Users**: No manual setup required - just run and click "Yes"
- **🛡️ Smart Protected Folders**: Automatically preserves user data during updates (minimap, characters, etc.)
- **📱 Modern Interface**: Beautiful PySide6 GUI with real-time progress tracking
- **🔄 Self-Updating Launcher**: Launcher automatically updates itself when new versions available
- **🗺️ Minimap Downloads**: Built-in minimap downloader with multiple options
- **📊 Version Tracking**: Enhanced semantic versioning with clear status indicators
- **💻 Thread-Safe Design**: Modern Qt architecture prevents freezing during downloads

---

## 🚀 Quick Start (For Server Owners)

### Step 1: Set Up Your GitHub Repository

1. **Create a GitHub repository** for your Tibia client (e.g., `myserver-client`)

2. **Create releases** with your client files:
   - Go to your repository → Releases → Create a new release
   - Upload your client as a ZIP file named `tibia-client.zip`
   - Tag it with a version like `v1.0.0`

### Step 2: Configure the Launcher

1. **Copy the easy config template**:
   ```json
   {
     "server_name": "My Awesome Tibia Server",
     "current_version": "1.0.0",
     "description": "Latest game client with new features!",
     "github_username": "YOUR_USERNAME",
     "github_repository": "YOUR_REPO_NAME",
     "client_zip_filename": "tibia-client.zip",
     
     "enable_auto_update": true,
     "launcher_github_username": "YOUR_USERNAME",
     "launcher_github_repository": "tibialauncher",
     "current_launcher_version": "2.0.0",
     
     "protected_folders": ["minimap", "conf", "characterdata", "screenshots"]
   }
   ```

2. **Fill in your details**:
   - Replace `YOUR_USERNAME` with your GitHub username
   - Replace `YOUR_REPO_NAME` with your repository name
   - Update `server_name` with your server's name

3. **Save as `launcher_config.json`** in your repository root

4. **Commit and push** to GitHub

### Step 3: Distribute the Launcher

1. **Build the launcher** (see Advanced Setup section below)
2. **Give users the launcher executable**
3. **Users run it** - launcher automatically:
   - Detects if Tibia is installed or needs updating
   - Shows current vs latest version
   - Prompts to download/update with one click
   - Continues checking every 2 hours for new updates

---

## 📥 Installation Guide (For Users)

### For Users Getting the Launcher

1. **Download** the launcher executable from your server owner
2. **Run** `tibialauncher.exe`
3. **Launcher automatically detects** if Tibia needs to be installed or updated
4. **Click "Yes"** when prompted to download the latest version automatically
5. **Click "PLAY"** when download completes

### Automatic Update Features

- 🔄 **Smart Detection**: Launcher automatically checks for updates on startup
- 🕐 **Periodic Checks**: Checks for both game and launcher updates every 2 hours
- 🎯 **One-Click Updates**: Just click "Yes" when prompted - no manual downloading
- 📊 **Version Display**: Always shows current vs latest version status
- 🛡️ **Safe Updates**: Your settings, characters, and minimaps are preserved

### System Requirements

- **Windows 10/11** (64-bit recommended)  
- **Python 3.12+** (for development only - not needed for built executables)
- **2GB free space** for game client
- **Internet connection** for downloads

---

## 🔄 How Automatic Updates Work

### For Users (What You'll See)

1. **First Launch**: 
   - Launcher shows "🔍 Checking for updates..."
   - If Tibia not installed: Shows "📋 Current version: Not installed" 
   - Automatically prompts: "Tibia is not installed yet. Would you like to download and install it now?"

2. **Update Available**:
   - Launcher shows "🔄 Update available!" in status
   - Version indicator shows: "📋 Current: 1.1 🌐 Latest: 1.2"
   - Automatically prompts: "A new Tibia version is available! Would you like to download and install it now?"

3. **Up to Date**:
   - Shows "✅ Up to date" status
   - Version indicator shows current version
   - Continues monitoring every 2 hours

4. **During Download**:
   - Progress bar shows download percentage
   - Status updates: "⬇️ Downloading: 45.2%"
   - Protected folders automatically backed up

### Enhanced Version Checking

- **Semantic Versioning**: Supports v1.2.3, 1.2.3, and development versions
- **Real-Time Status**: Always shows current vs latest version comparison  
- **Smart Detection**: Distinguishes between first install and updates
- **Background Monitoring**: Checks every 2 hours without interrupting gameplay

---

## ⚙️ Configuration Guide (For Developers)

### Technology Stack

- **Language**: Python 3.12+
- **GUI Framework**: PySide6 (Qt for Python)
- **Key Libraries**: requests, pathlib, threading
- **Build Tool**: PyInstaller
- **Architecture**: Modern Qt signal-slot system with thread-safe design

### Setting Up Development Environment

1. **Install Python 3.12+**
   ```bash
   # Download from python.org
   # Make sure to check "Add Python to PATH"
   ```

2. **Clone this repository**
   ```bash
   git clone https://github.com/yourusername/tibialauncher.git
   cd tibialauncher
   ```

3. **Create virtual environment** (recommended)
   ```bash
   python -m venv .venv
   .\.venv\Scripts\activate  # Windows
   source .venv/bin/activate  # Linux/Mac
   ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

   > **Note**: The `.venv` folder is excluded from the repository via `.gitignore` - each developer creates their own local environment.

### Running from Source

```bash
python pyside6_gaming_launcher.py
```

---

## 🔧 Advanced Configuration Options

### Configuration File Format

The launcher supports both simple and advanced configuration formats:

**Simple Format (Recommended)**:
```json
{
  "server_name": "My Tibia Server",
  "current_version": "1.0.0", 
  "description": "Latest client with bug fixes",
  "github_username": "myusername",
  "github_repository": "tibia-client",
  "client_zip_filename": "tibia-client.zip",
  "enable_auto_update": true,
  "protected_folders": ["minimap", "conf", "characterdata"]
}
```

**Advanced Format**:
```json
{
  "server_name": "Advanced Tibia Server",
  "current_version": "2.1.0",
  "description": "Major update with new features!",
  "github_username": "myorg", 
  "github_repository": "tibia-client",
  "client_zip_filename": "tibia-client.zip",
  
  "enable_auto_update": true,
  "launcher_github_username": "myorg",
  "launcher_github_repository": "tibialauncher", 
  "current_launcher_version": "2.0.0",
  
  "protected_folders": ["minimap", "conf", "characterdata", "screenshots", "addons"],
  "install_path": "%APPDATA%/Tibia",
  "auto_check_interval_hours": 2,
  "show_version_status": true,
  "enhanced_version_comparison": true
}
```

### Configuration Fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `server_name` | string | Yes | Display name shown in launcher |
| `current_version` | string | Yes | Current client version (semantic versioning) |
| `github_username` | string | Yes | GitHub username/organization |
| `github_repository` | string | Yes | Repository containing client releases |
| `client_zip_filename` | string | Yes | ZIP filename in GitHub releases |
| `description` | string | No | Update description shown to users |
| `enable_auto_update` | boolean | No | Enable launcher self-updates (default: true) |
| `protected_folders` | array | No | Folders preserved during updates |
| `auto_check_interval_hours` | number | No | Hours between update checks (default: 2) |
| `show_version_status` | boolean | No | Show version indicator in UI (default: true) |
| `enhanced_version_comparison` | boolean | No | Use semantic versioning comparison (default: true) |

---

## 🔨 Building Executables

### Quick Build

```bash
# Use the included build script
.\build.bat
```

### Manual Build

```bash
# Single file executable (recommended)
pyinstaller tibialauncher_onefile.spec

# Directory distribution (dev/testing)
pyinstaller --onedir --windowed --icon=images/appicon.ico pyside6_gaming_launcher.py
```

### Code Signing (Optional)

To avoid Windows SmartScreen warnings:

```powershell
# See sign-exe.ps1 for detailed signing setup
.\sign-exe.ps1 dist/tibialauncher.exe
```

---

## 🛠️ Troubleshooting

### Common Issues

**"Update prompt not appearing"**
- Wait 2-3 seconds after launcher startup for automatic check
- Check internet connection
- Verify GitHub repository is accessible
- Check if `silent` mode is disabled in logs

**"Failed to download from GitHub"**
- Check repository name and username in config
- Ensure repository is public or provide access token
- Verify internet connection and firewall settings

**"Version comparison shows wrong status"** 
- Use semantic versioning format (e.g., "1.2.3" or "v1.2.3")
- Check that GitHub release tags match config version
- View launcher logs for detailed version comparison

**"Automatic updates stopped working"**
- Check launcher logs for background thread errors
- Restart launcher to reset 2-hour timer
- Verify GitHub API rate limits not exceeded

**"Protected folders not restored"**
- Check file permissions in install directory
- Ensure sufficient disk space for backups
- Run launcher as administrator if needed
- Check logs for specific folder backup/restore errors

### Debug Mode

Set `TIBIA_DEBUG=true` environment variable for detailed logging.

### Getting Help

1. Check logs in `%APPDATA%/Tibia/logs/`
2. Verify your `launcher_config.json` format
3. Test GitHub repository access
4. Create an issue with logs attached

---

## 📄 File Structure

```
.
├── pyside6_gaming_launcher.py     # Main GUI application
├── launcher_core.py               # Back-compat shim → re-exports from tibialauncher.core
├── tibialauncher_onefile.spec     # PyInstaller build config (onefile)
├── requirements.txt               # Python dependencies
├── build.bat / setup.bat          # Build/setup scripts
├── sign-exe.ps1                   # Optional code signing helper
├── tibialauncher/                 # Python package
│   ├── __init__.py
│   └── core/
│       ├── launcher_core.py       # Core download/update/self-update logic
│       ├── github_downloader.py   # GitHub API + config retrieval
│       └── file_manager.py        # File/backup/extraction utilities
├── config/                        # Config templates/examples
│   ├── launcher_config_template.json
│   └── launcher_config_example.json
└── images/                        # Launcher graphics
   ├── tibia_ot_logo.png          # Main logo
   ├── background-artwork.png     # Background image
   └── appicon.ico                # Application icon
```

---

## 📦 Repository Structure

### What to Include in Your Repository
```
.
├── pyside6_gaming_launcher.py
├── launcher_core.py                        # Back-compat shim
├── tibialauncher/                          # Organized package
│   └── core/ (launcher_core.py, github_downloader.py, file_manager.py)
├── config/                                 # Templates/examples for remote config
│   ├── launcher_config_template.json
│   └── launcher_config_example.json
├── images/
├── requirements.txt
├── build.bat / setup.bat
├── sign-exe.ps1
├── tibialauncher_onefile.spec
└── README.md
```

### What NOT to Include (.gitignore excludes)
- `.venv/` or `venv/` - Virtual environments (machine-specific)
- `__pycache__/` - Python cache files
- `dist/` - Built executables
- `launcher_config.json` - Your actual config (keep private)
- `*_backup.py` - Backup files
- IDE files (`.vscode/`, `.idea/`)

> **For Users**: Clone the repo and create your own `.venv` with `python -m venv .venv`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Make your changes and test thoroughly
4. Submit a pull request with a clear description

---

## 📝 License

This project is open source - feel free to modify and distribute!

---

**🎮 Ready to launch your Tibia server? Get started with the easy config above!**
**🎮 Ready to launch your Tibia server? Get started with the easy config above!**

---

## 🔄 Launcher Self-Update (Packaged EXE)

- When built with PyInstaller (a packaged EXE), the launcher can automatically update itself.
- Requirements in your remote `launcher_config.json`:
   - `enable_auto_update: true`
   - Provide launcher repo info (`launcher_github_username`, `launcher_github_repository`) so latest release can be discovered, or ensure your config format provides a direct `download_url` via the core logic.
   - Optional: `auto_install_launcher_updates: true` to install without prompting.
- Note: When running from source (not frozen), self-update checks are skipped by design.

