# Linux Tiny Wall

A Linux-based application designed similar to Tiny Wall for Windows, providing granular control over command execution and system protection.

## Overview

Linux Tiny Wall is a security-focused application that blocks various potentially dangerous Linux commands which may take over a user's machine or be used for malicious purposes. It also prevents commands responsible for collecting various system IDs and sensitive system information.

## Features

- **Command Blocking**: Prevent execution of dangerous commands that could compromise system security
- **System ID Protection**: Block commands that collect system identification information
- **Granular Control**: Fine-grained control over which commands are allowed or blocked
- **User-Friendly Interface**: Easy-to-use controls for managing command restrictions
- **Logging**: Track blocked command attempts for security monitoring

## Quick Start

### Installation

#### Prerequisites
- Linux system (Ubuntu, Debian, Fedora, or compatible)
- Python 3.7+
- sudo/root access for installation

#### One-Line Installation
```bash
bash <(curl -s https://raw.githubusercontent.com/terrycarry21/linux-tiny-wall/master/install.sh) && source ~/.bashrc
```

#### Manual Installation
```bash
# Clone the repository
git clone https://github.com/terrycarry21/linux-tiny-wall.git
cd linux-tiny-wall

# Run installation script
sudo bash install.sh

# Source bashrc to enable command blocking
source ~/.bashrc
```

### Launching Linux Tiny Wall
```bash
linux-tiny-wall
```

Or if using the GUI:
```bash
sudo python3 /opt/linux-tiny-wall/app/main.py
```

## Dependencies

The installation script will automatically install all required dependencies:

### System Packages
- python3
- python3-dev
- libssl-dev
- curl

### Python Dependencies
- (Will be installed via pip during setup)

### Installation Commands
```bash
# Ubuntu/Debian
sudo apt-get update && sudo apt-get install -y python3 python3-dev libssl-dev curl

# Fedora/RHEL
sudo dnf install -y python3 python3-devel openssl-devel curl

# Arch
sudo pacman -S python3 base-devel openssl curl
```

## Usage

### Basic Commands
```bash
# Start the application
linux-tiny-wall start

# View blocked commands log
linux-tiny-wall log

# Add a command to the blocklist
linux-tiny-wall block add <command>

# Remove a command from blocklist
linux-tiny-wall block remove <command>

# View current blocklist
linux-tiny-wall list
```

## Protected Commands

Linux Tiny Wall blocks commands such as:
- `id`, `whoami` - System identification
- `uname` - System information
- `lsb_release` - Distribution information
- `cat /proc/...` - System file access
- `chmod 777` / `chmod 000` - Permission manipulation
- And other potentially dangerous operations

## Configuration

Configuration file: `/etc/linux-tiny-wall/config.json`

### Example Configuration
```json
{
  "enabled": true,
  "log_blocked_commands": true,
  "log_location": "/var/log/linux-tiny-wall.log",
  "blocklist": [
    "id",
    "whoami",
    "uname"
  ]
}
```

## Troubleshooting

### Application Won't Start
```bash
# Check if dependencies are installed
python3 -c "import sys; print(sys.version)"

# Verify installation
sudo /opt/linux-tiny-wall/app/main.py --help
```

### Commands Not Being Blocked
```bash
# Check if Linux Tiny Wall is enabled
linux-tiny-wall status

# Verify bashrc is sourced
source ~/.bashrc

# Check logs
tail -f /var/log/linux-tiny-wall.log
```

### Permission Denied Errors
```bash
# Ensure proper permissions
sudo chown -R root:root /opt/linux-tiny-wall
sudo chmod -R 755 /opt/linux-tiny-wall
```

## Uninstallation

```bash
sudo bash /opt/linux-tiny-wall/uninstall.sh
```

Or manually:
```bash
sudo rm -rf /opt/linux-tiny-wall
sudo rm -f /etc/linux-tiny-wall/config.json
# Remove from ~/.bashrc if added
```

## Project Status

- Status: In Development
- Version: 0.1.0 (Initial Release)
- Last Updated: November 27, 2025

## Author

Terry Carry (terrycarry21)

## License

This project is part of the Magi suite of tools.

## Support

For issues, questions, or contributions, please visit:
https://github.com/terrycarry21/linux-tiny-wall

---

**Note**: This is a security tool. Use carefully and test thoroughly in your environment before deploying to production systems.
