This program has yet to be started, as I still have not been able to put the money or the effort into getting my systems clean.  It's mostly a matter of money, as I simply haven't been able to quite afford the simple pieces of hardware which will be required to get everything back in order.  Most of my viruses have been identified at this point.  I use Linux, largly due to the fact that I can't cover myself durring a download of the OS, using IP blockers, and am not a fan of the idea of exposing my identity when I don't choose to do so.  However, I used Windows for years, and it once again, seems to have been the only solution to my problems.  While my personal hardware was not something Microsoft will fix, as they have no real responsibility or right to adjust equipment which is not part of their mechanisms of function, they have in fact identified a series of various viruses which were associated with my problems.  I can complain about it all day, but god bless Windows.

Outside that, this program has some explaination, but the full scope of what I am trying to accomplish has not been expressed.  A lot of my infections happened because of CLI.  When I opened up my computer to everything possible, the end result was everything possible happened to me.  Which is cool.  After I whined and complained a lot, I started to really respect the fact that this much havoc was aimed at me personally.  Makes me feel kind of special.

So... This program... Simple and stupid.  Unlike OpenSnitch, which has a level of complexity that gives you a slight headach.  Tiny Wall by Pados, was always a simple easy to follow design.  There were flaws with Tiny Wall.  It can be breached.  How... I have no idea.  I'm not that smart.  But I did have people get through it, and that is a mystery for smarter men.

But the simplicity is something I strive to attain.  And then we have everything Linux claims to be, but seems to lack in reality.  You don't need a password for example, to install your dependencies if you write the script using things such as Chroot.  There are several ways I have used various advanced CLI programs, to bipass my own personal contribution to the processes of doing this which could otherwise compromise my computer.

Due to this fact, the whole aspect of Linux Tiny Wall, has to include a Linux specific segment.  One which blocks things such as Chroot, without having to segment your OS into Admin and User accounts which block privilages.  That's too much effort.  The blockaids should also incude ways to block other system retrieval processes.  Machine ID information, or any command which can simply be ran in the terminal which identifies the user.

I realized this in Warp, when I was trying to use multiple free accounts.  I tried to get it to cover all my machine ID informaiton, and I kept digging to see what exactly it could bring up.  Eventually we ran into a wall.  It refused to cover my machine ID, and other ID metrics which were imbeded in my chips.  The AI refused to do it.  It said that it would not help me block my machine ID, and that machine ID was imbeded in the silicon, and unable to be covered up.  It wasn't like I was trying to create malicious programs.  I was trying to hide my identity for my own purposes.

And it refused.  It has proven that in my opinion, AI moderation has gone too far.  So... Some little blimps need to be added in.  Pretty simple, once the ones that the system will approve have been added, any person with a litte copy paste skills can copy the templates, and replace things from some blockers, with other blockers.  

The system also may possibly be able to have a password bipass button.  A simple ON OFF switch features, to stop needing to use a password.  I did find out that you could make an OS, which would do this, or even use a program such as Cubic, to make an Ubuntu system which would do this.  But I have not yet explored if I can make it as quick and easy as pushing a button.  This button of course should have password protection of it's own.  So turning on and off your password takes more effort then actually putting in your password.

At any rate, this program pretty much writes it's self, if you sit there with a copy of Tiny Wall, and you simply go back and fourth.  Then add my 2 features which make the process of Linux more secure and less complicated.

If anyone other then me does this, try to keep the idea of having the security features segmented into 2 categories.  Actions, and Identifications.  So you can choose to stop the ability to have actions on your computer taken without your permissions, and you can alternatly, choose to cover your identification calls on another hand.

There are several other possible aspects which can be added to this program, to make it complete, which I have in my time realized are just the only real way to keep making Linux more advanced.  Like combinning various programs with these programs to maximize the efficiency of your defences.  

For this, the addition of things like ClamAV, or USB Guard, are always possible with little to no effort.  You can expand it to be not just a Tiny Wall, which is specific to Windows, but a quick and easy User Friendly verions of a full security program for Linux.  

I like to base a lot of what I do based on Mint.  I am currenlty trying to step up my game, and move to Kali Purple, to hopefully get a better grasp on Linux.  But apparently with driver availability, often times Ubuntu having a corporate focus, has had more time invested on the level of money, then Debian.  I don't know this for sure of course, as I am still trying to understand the differences, and have maybe 2 days experience now on Debian.  

At any rate.. The Mint theory.  Mint is like Ubuntu Windows.  So when you ask yourself what should I do next.. You simply need to ask yourself, how can I make Mint like Windows.  And that pretty much answers your question as to how to make the Ubuntu based open source software, what it needs to be to be compairable to Windows.

Because as much as people like to say ohh poo poo Windows, and yay for Linux.. It's a lie... Linux isn't better.. It's not more secure... It's not more private... It's a lie... 100%.... But... It can be... But.. It's not...





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
