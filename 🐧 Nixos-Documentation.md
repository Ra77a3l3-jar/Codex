# 🐧 NixOS Documentation
*Version: 25.05 | Last Updated: January 2025*

NixOS is a revolutionary Linux distribution built on top of the Nix package manager that offers declarative configuration management, atomic upgrades, and reliable system rollbacks. Unlike traditional Linux distributions, NixOS allows you to configure your entire system through a single configuration file, making system administration reproducible and reliable.

## 📚 Table of Contents

1. [🚀 Introduction & Getting Started](#-introduction--getting-started)
2. [⚙️ Installation & Setup](#️-installation--setup)
3. [📝 Configuration Basics](#-configuration-basics)
4. [📦 Package Management](#-package-management)
5. [🏗️ System Configuration](#️-system-configuration)
6. [🔧 Service Management](#-service-management)
7. [👤 User Management](#-user-management)
8. [🌐 Network Configuration](#-network-configuration)
9. [💾 Storage & Filesystems](#-storage--filesystems)
10. [🖥️ Desktop Environment Setup](#️-desktop-environment-setup)
11. [🐳 Containerization & Virtualization](#-containerization--virtualization)
12. [🔒 Security & Hardening](#-security--hardening)
13. [🚀 Advanced Configuration](#-advanced-configuration)
14. [🛠️ Development Environment](#️-development-environment)
15. [🔍 Troubleshooting](#-troubleshooting)
16. [📖 Glossary](#-glossary)
17. [🔗 Quick Reference](#-quick-reference)
18. [📚 Further Reading](#-further-reading)
19. [🤝 Community Resources](#-community-resources)
20. [💝 Contributing Guidelines](#-contributing-guidelines)

---

## 🚀 Introduction & Getting Started

**📊 Chapter 1 of 20**

**🎯 Learning Objectives:**
- Understand what makes NixOS unique among Linux distributions
- Learn the core concepts of declarative system configuration
- Explore the benefits of reproducible system management
- Get familiar with the Nix language basics

**⏱️ Estimated Reading Time:** 15 minutes

**📋 Prerequisites:** Basic Linux command line knowledge

### What is NixOS?

NixOS is a Linux distribution with a unique approach to package and configuration management. Built on top of the Nix package manager, it treats the operating system configuration as a single declarative specification. This means your entire system can be reproduced from a single configuration file.

Key characteristics of NixOS:

- **Declarative Configuration**: Your entire system is defined in configuration files
- **Atomic Upgrades and Rollbacks**: System changes are atomic and reversible
- **Reproducible Builds**: Systems can be reproduced exactly across different machines
- **Isolation**: Different versions of packages can coexist without conflicts
- **Functional Package Management**: Packages are treated as immutable values

### Why Choose NixOS?

```nix
# Your entire system configuration in one place
{ config, pkgs, ... }:
{
  # Boot loader configuration
  boot.loader.systemd-boot.enable = true;

  # Networking
  networking.hostName = "my-nixos-machine";
  networking.wireless.enable = true;

  # User configuration
  users.users.alice = {
    isNormalUser = true;
    extraGroups = [ "wheel" "networkmanager" ];
  };

  # System packages
  environment.systemPackages = with pkgs; [
    firefox
    vim
    git
  ];
}
```

**Benefits:**

1. **Reliability**: System configuration is version controlled and reproducible
2. **Safety**: Easy rollbacks if something goes wrong
3. **Consistency**: Development, staging, and production environments can be identical
4. **Efficiency**: Share configurations across multiple machines
5. **Flexibility**: Mix different versions of software without conflicts

### Core Concepts

#### The Nix Store
The `/nix/store` is where all packages and their dependencies are stored. Each package has a unique hash-based path that prevents conflicts:

```bash
/nix/store/abc123...-firefox-122.0.1/
/nix/store/def456...-python3-3.11.7/
/nix/store/ghi789...-gcc-13.2.0/
```

#### Configuration.nix
The heart of NixOS is `/etc/nixos/configuration.nix`, where your entire system is defined:

```nix
{ config, pkgs, ... }:
{
  imports = [
    ./hardware-configuration.nix
    ./users.nix
    ./services.nix
  ];

  system.stateVersion = "25.05";

  # Your configuration goes here
}
```

#### Generations
Every time you rebuild your system, NixOS creates a new "generation" - a complete system configuration that you can boot into or roll back to.

### Hello World Example

Let's start with a simple configuration that installs a few essential packages:

```nix
{ config, pkgs, ... }:
{
  # Enable the GNOME Desktop Environment
  services.xserver.enable = true;
  services.xserver.displayManager.gdm.enable = true;
  services.xserver.desktopManager.gnome.enable = true;

  # Install essential packages
  environment.systemPackages = with pkgs; [
    # Text editors
    vim
    nano

    # Development tools
    git
    curl
    wget

    # System utilities
    htop
    tree
    unzip
  ];

  # Enable sound
  sound.enable = true;
  hardware.pulseaudio.enable = true;

  system.stateVersion = "25.05";
}
```

After saving this configuration, rebuild your system:

```bash
sudo nixos-rebuild switch
```

> 💡 **Tip:** Always backup your working configuration before making major changes. NixOS makes this easy with its generation system!

### ⚠️ Common Pitfalls

1. **Forgetting to rebuild**: Changes to configuration.nix don't take effect until you run `nixos-rebuild switch`
2. **Missing imports**: Large configurations should be split into modules with proper imports
3. **Syntax errors**: The Nix language has specific syntax - use `nixos-rebuild dry-build` to check for errors
4. **State version**: Always set the correct `system.stateVersion` for your NixOS release

### ✅ Best Practices

1. **Version control your configuration**: Keep `/etc/nixos/` in a git repository
2. **Use modules**: Split large configurations into logical modules
3. **Test changes**: Use `nixos-rebuild test` before committing with `switch`
4. **Comment your code**: Document why you made specific configuration choices
5. **Start simple**: Begin with a minimal configuration and gradually add complexity

### 🏋️ Exercise 1: Basic Configuration Setup

**Difficulty:** 🟢 Beginner
**Estimated Time:** 20 minutes

Create a basic NixOS configuration that includes:
1. Your preferred desktop environment (GNOME, KDE, or XFCE)
2. A user account with sudo privileges
3. Essential development tools (git, vim, curl)
4. Enable SSH access

<details>
<summary>💡 Click to see hints</summary>

- Use `services.xserver.desktopManager` for desktop environments
- User configuration goes in `users.users.<username>`
- SSH is enabled with `services.openssh.enable`
- Development tools go in `environment.systemPackages`

</details>

<details>
<summary>✅ Click to see solution</summary>

```nix
{ config, pkgs, ... }:
{
  imports = [
    ./hardware-configuration.nix
  ];

  # Bootloader
  boot.loader.systemd-boot.enable = true;
  boot.loader.efi.canTouchEfiVariables = true;

  # Networking
  networking.hostName = "my-nixos-dev";
  networking.networkmanager.enable = true;

  # Desktop Environment - GNOME
  services.xserver.enable = true;
  services.xserver.displayManager.gdm.enable = true;
  services.xserver.desktopManager.gnome.enable = true;

  # User account
  users.users.developer = {
    isNormalUser = true;
    description = "Developer User";
    extraGroups = [ "networkmanager" "wheel" ];
    packages = with pkgs; [
      firefox
      thunderbird
    ];
  };

  # System packages
  environment.systemPackages = with pkgs; [
    # Development tools
    git
    vim
    neovim
    curl
    wget

    # System utilities
    htop
    tree
    unzip
    zip

    # Network tools
    openssh
    rsync
  ];

  # Enable SSH
  services.openssh.enable = true;
  services.openssh.settings = {
    PasswordAuthentication = false;
    KbdInteractiveAuthentication = false;
  };

  # Sound
  sound.enable = true;
  hardware.pulseaudio.enable = true;

  # System version
  system.stateVersion = "25.05";
}
```

**Explanation:**
This configuration demonstrates the fundamental structure of a NixOS system:

- **Bootloader setup**: Uses systemd-boot for UEFI systems
- **Network configuration**: Enables NetworkManager for easy WiFi/Ethernet management
- **Desktop environment**: Sets up GNOME with GDM login manager
- **User management**: Creates a user with administrative privileges
- **Package installation**: Installs essential development and system tools
- **Service configuration**: Enables SSH with key-based authentication only
- **Hardware support**: Enables sound through PulseAudio

The modular approach allows you to easily modify or extend this configuration as your needs grow.

</details>

[🔝 Back to top](#-nixos-documentation)

---

## ⚙️ Installation & Setup

**📊 Chapter 2 of 20**

**🎯 Learning Objectives:**
- Learn different NixOS installation methods
- Understand hardware requirements and compatibility
- Master the installation process step-by-step
- Configure initial system settings

**⏱️ Estimated Reading Time:** 25 minutes

**📋 Prerequisites:** Basic understanding of Linux partitioning and bootloaders

### Hardware Requirements

**Minimum Requirements:**
- CPU: x86_64 or AArch64 processor
- RAM: 1GB (4GB recommended for desktop environments)
- Storage: 8GB (20GB+ recommended)
- Network: Internet connection for package downloads

**Recommended Requirements:**
- CPU: Multi-core x86_64 processor
- RAM: 8GB+ for smooth desktop experience
- Storage: SSD with 50GB+ for comfortable usage
- Network: Reliable broadband connection

### Installation Methods

#### 1. ISO Installation (Most Common)

Download the NixOS ISO from the official website:

```bash
# Download the latest ISO
wget https://channels.nixos.org/nixos-25.05/latest-nixos-minimal-x86_64-linux.iso

# Verify the download
sha256sum latest-nixos-minimal-x86_64-linux.iso
```

Create a bootable USB drive:

```bash
# Replace /dev/sdX with your USB device
sudo dd if=latest-nixos-minimal-x86_64-linux.iso of=/dev/sdX bs=1M status=progress
```

#### 2. Network Installation

For advanced users, NixOS supports network-based installations:

```bash
# Boot from network (PXE)
# Configure your DHCP server to provide:
# - IP address
# - Boot filename: nixos/bzImage
# - TFTP server with NixOS kernel and initrd
```

#### 3. VM Installation

Testing NixOS in a virtual machine:

```bash
# QEMU example
qemu-system-x86_64 \
  -m 2048 \
  -smp 2 \
  -cdrom nixos-minimal.iso \
  -boot d \
  -hda nixos-vm.qcow2
```

### Step-by-Step Installation Process

#### Step 1: Boot from Installation Media

1. Boot from your NixOS USB/DVD
2. Select "NixOS Live CD" from the boot menu
3. Wait for the system to load (this may take a few minutes)

#### Step 2: Configure Networking

```bash
# Check network interfaces
ip addr show

# For WiFi connections
wpa_supplicant -B -i wlp2s0 -c <(wpa_passphrase 'SSID' 'password')

# Verify internet connectivity
ping nixos.org
```

#### Step 3: Partition the Disk

**UEFI System with GPT:**

```bash
# Use parted for partitioning
sudo parted /dev/sda -- mklabel gpt

# Create EFI partition (512MB)
sudo parted /dev/sda -- mkpart ESP fat32 1MiB 512MiB
sudo parted /dev/sda -- set 1 esp on

# Create root partition (remaining space)
sudo parted /dev/sda -- mkpart primary 512MiB 100%

# Format partitions
sudo mkfs.fat -F 32 -n boot /dev/sda1
sudo mkfs.ext4 -L nixos /dev/sda2
```

**Legacy BIOS with MBR:**

```bash
# Create MBR partition table
sudo parted /dev/sda -- mklabel msdos

# Create root partition
sudo parted /dev/sda -- mkpart primary 1MiB 100%

# Format partition
sudo mkfs.ext4 -L nixos /dev/sda1
```

#### Step 4: Mount Filesystems

```bash
# Mount root filesystem
sudo mount /dev/disk/by-label/nixos /mnt

# Create and mount boot directory (UEFI only)
sudo mkdir -p /mnt/boot
sudo mount /dev/disk/by-label/boot /mnt/boot
```

#### Step 5: Generate Configuration

```bash
# Generate hardware configuration
sudo nixos-generate-config --root /mnt

# This creates:
# /mnt/etc/nixos/configuration.nix
# /mnt/etc/nixos/hardware-configuration.nix
```

#### Step 6: Edit Configuration

Edit the generated configuration file:

```bash
sudo nano /mnt/etc/nixos/configuration.nix
```

Example basic configuration:

```nix
{ config, pkgs, ... }:
{
  imports = [ ./hardware-configuration.nix ];

  # Bootloader
  boot.loader.systemd-boot.enable = true;
  boot.loader.efi.canTouchEfiVariables = true;

  # Networking
  networking.hostName = "nixos-desktop";
  networking.networkmanager.enable = true;

  # Locale and timezone
  time.timeZone = "America/New_York";
  i18n.defaultLocale = "en_US.UTF-8";

  # Desktop environment
  services.xserver.enable = true;
  services.xserver.displayManager.gdm.enable = true;
  services.xserver.desktopManager.gnome.enable = true;

  # User account
  users.users.myuser = {
    isNormalUser = true;
    description = "My User";
    extraGroups = [ "networkmanager" "wheel" ];
  };

  # System packages
  environment.systemPackages = with pkgs; [
    firefox
    git
    vim
  ];

  system.stateVersion = "25.05";
}
```

#### Step 7: Install NixOS

```bash
# Start the installation
sudo nixos-install

# Set root password when prompted
# The system will download and install packages
```

#### Step 8: Post-Installation Setup

```bash
# Reboot into your new system
sudo reboot

# After reboot, set user password
sudo passwd myuser

# Update the system
sudo nixos-rebuild switch --upgrade
```

### Installation Troubleshooting

#### Common Issues and Solutions

**1. Boot Issues:**

```bash
# If system won't boot, try recovery mode
# At GRUB menu, select older generation
# Or boot from ISO and chroot into installed system

sudo mount /dev/sda2 /mnt
sudo mount /dev/sda1 /mnt/boot  # UEFI only
sudo nixos-enter --root /mnt
```

**2. Network Issues:**

```bash
# Check network configuration
nmcli device status
nmcli connection show

# Restart NetworkManager
sudo systemctl restart NetworkManager
```

**3. Graphics Issues:**

```nix
# Add to configuration.nix for NVIDIA
hardware.nvidia = {
  modesetting.enable = true;
  open = false;  # Use proprietary driver
  nvidiaSettings = true;
  package = config.boot.kernelPackages.nvidiaPackages.stable;
};

# For AMD graphics
hardware.opengl = {
  enable = true;
  driSupport = true;
  driSupport32Bit = true;
};
```

### ⚠️ Common Pitfalls

1. **Incorrect partitioning**: UEFI systems need an EFI partition, BIOS systems don't
2. **Missing network**: Ensure internet connectivity before installation
3. **Wrong filesystem labels**: Make sure mount points match partition labels
4. **Syntax errors in configuration**: Validate Nix syntax before installation
5. **Insufficient disk space**: Leave plenty of room for the Nix store

### ✅ Best Practices

1. **Test in VM first**: Try NixOS in a virtual machine before bare-metal installation
2. **Backup existing data**: Always backup important data before partitioning
3. **Use descriptive hostnames**: Choose meaningful hostnames for your systems
4. **Document your setup**: Keep notes about hardware-specific configurations
5. **Plan your partitioning**: Consider separate partitions for /home if needed

### 🏋️ Exercise 2: Custom Installation

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 45 minutes

Perform a NixOS installation with the following requirements:
1. UEFI boot with systemd-boot
2. Encrypted root filesystem using LUKS
3. Separate /home partition
4. Configure for both WiFi and Ethernet
5. Install KDE Plasma desktop environment

<details>
<summary>💡 Click to see hints</summary>

- Use `cryptsetup` for LUKS encryption
- Create multiple partitions: EFI, root, home
- WiFi configuration requires `networking.wireless` or `networking.networkmanager`
- KDE uses `services.xserver.desktopManager.plasma5`
- Don't forget to configure `boot.initrd.luks.devices`

</details>

<details>
<summary>✅ Click to see solution</summary>

**Partitioning and Encryption:**

```bash
# Create partitions
sudo parted /dev/sda -- mklabel gpt
sudo parted /dev/sda -- mkpart ESP fat32 1MiB 512MiB
sudo parted /dev/sda -- set 1 esp on
sudo parted /dev/sda -- mkpart primary 512MiB 50GiB
sudo parted /dev/sda -- mkpart primary 50GiB 100%

# Set up LUKS encryption
sudo cryptsetup luksFormat /dev/sda2
sudo cryptsetup luksOpen /dev/sda2 crypted-nixos

sudo cryptsetup luksFormat /dev/sda3
sudo cryptsetup luksOpen /dev/sda3 crypted-home

# Format filesystems
sudo mkfs.fat -F 32 -n boot /dev/sda1
sudo mkfs.ext4 -L nixos /dev/mapper/crypted-nixos
sudo mkfs.ext4 -L home /dev/mapper/crypted-home

# Mount filesystems
sudo mount /dev/disk/by-label/nixos /mnt
sudo mkdir -p /mnt/boot /mnt/home
sudo mount /dev/disk/by-label/boot /mnt/boot
sudo mount /dev/disk/by-label/home /mnt/home
```

**Configuration:**

```nix
{ config, pkgs, ... }:
{
  imports = [ ./hardware-configuration.nix ];

  # Bootloader with LUKS support
  boot.loader.systemd-boot.enable = true;
  boot.loader.efi.canTouchEfiVariables = true;

  # LUKS configuration
  boot.initrd.luks.devices = {
    crypted-nixos = {
      device = "/dev/disk/by-uuid/YOUR-ROOT-UUID";
      preLVM = true;
    };
    crypted-home = {
      device = "/dev/disk/by-uuid/YOUR-HOME-UUID";
    };
  };

  # Filesystems
  fileSystems."/home" = {
    device = "/dev/mapper/crypted-home";
    fsType = "ext4";
  };

  # Networking
  networking.hostName = "nixos-encrypted";
  networking.networkmanager.enable = true;

  # Alternative WiFi-only configuration:
  # networking.wireless.enable = true;
  # networking.wireless.networks = {
  #   "MyWiFi" = {
  #     psk = "password";
  #   };
  # };

  # Locale settings
  time.timeZone = "America/New_York";
  i18n.defaultLocale = "en_US.UTF-8";

  # KDE Plasma Desktop
  services.xserver.enable = true;
  services.xserver.displayManager.sddm.enable = true;
  services.xserver.desktopManager.plasma5.enable = true;

  # Audio
  sound.enable = true;
  hardware.pulseaudio.enable = true;

  # User configuration
  users.users.alice = {
    isNormalUser = true;
    description = "Alice";
    extraGroups = [ "networkmanager" "wheel" ];
    packages = with pkgs; [
      kate
      konsole
      dolphin
    ];
  };

  # System packages
  environment.systemPackages = with pkgs; [
    firefox
    git
    vim
    htop
    tree
    cryptsetup
  ];

  # Security services
  services.openssh.enable = true;
  services.openssh.settings = {
    PasswordAuthentication = false;
    PermitRootLogin = "no";
  };

  system.stateVersion = "25.05";
}
```

**Explanation:**
This advanced installation demonstrates several important concepts:

- **LUKS Encryption**: Both root and home partitions are encrypted, requiring passwords at boot
- **Multi-partition Setup**: Separate partitions allow for different backup and maintenance strategies
- **Network Flexibility**: NetworkManager provides both WiFi and Ethernet support with a GUI
- **Desktop Environment**: KDE Plasma offers a full-featured desktop experience
- **Security Hardening**: SSH is configured for key-based authentication only
- **User Packages**: Per-user packages are installed alongside system packages

The encrypted setup provides strong security for laptops and sensitive systems, while the separate home partition allows for easier system upgrades without affecting user data.

</details>

[🔝 Back to top](#-nixos-documentation)

---

## 📝 Configuration Basics

**📊 Chapter 3 of 20**

**🎯 Learning Objectives:**
- Master the Nix configuration language syntax
- Learn to structure and organize configuration files
- Understand configuration modules and imports
- Practice with real-world configuration examples

**⏱️ Estimated Reading Time:** 30 minutes

**📋 Prerequisites:** Basic NixOS installation completed

### Understanding Nix Configuration Language

NixOS uses the Nix expression language to describe system configurations. This functional language treats configurations as immutable values that can be composed and reused.

#### Basic Syntax

**Attribute Sets:**
```nix
# Simple attribute set
{
  name = "Alice";
  age = 30;
  isActive = true;
}

# Nested attribute sets
{
  user = {
    name = "Alice";
    email = "alice@example.com";
    preferences = {
      theme = "dark";
      language = "en";
    };
  };
}
```

**Lists:**
```nix
# Simple list
[ "firefox" "chrome" "safari" ]

# List of attribute sets
[
  { name = "Alice"; role = "admin"; }
  { name = "Bob"; role = "user"; }
]
```

**Functions:**
```nix
# Simple function
addOne = x: x + 1

# Function with multiple parameters
mkUser = name: email: {
  inherit name email;
  isActive = true;
}

# Using the function
user1 = mkUser "Alice" "alice@example.com"
```

#### Configuration File Structure

The main configuration file `/etc/nixos/configuration.nix` follows this pattern:

```nix
{ config, pkgs, ... }:  # Function parameters
{                       # Configuration attribute set
  # imports - other configuration files to include
  imports = [
    ./hardware-configuration.nix
    ./users.nix
    ./services.nix
  ];

  # Configuration options
  networking.hostName = "my-nixos";

  # System state version (don't change after installation)
  system.stateVersion = "25.05";
}
```

### Configuration Options

NixOS provides thousands of configuration options. Here are the most commonly used categories:

#### System Options

```nix
{
  # System identification
  networking.hostName = "nixos-workstation";
  networking.hostId = "12345678";  # 8-character hex string

  # Time and locale
  time.timeZone = "Europe/London";
  i18n.defaultLocale = "en_GB.UTF-8";
  i18n.extraLocaleSettings = {
    LC_ADDRESS = "en_GB.UTF-8";
    LC_IDENTIFICATION = "en_GB.UTF-8";
    LC_MEASUREMENT = "en_GB.UTF-8";
    LC_MONETARY = "en_GB.UTF-8";
    LC_NAME = "en_GB.UTF-8";
    LC_NUMERIC = "en_GB.UTF-8";
    LC_PAPER = "en_GB.UTF-8";
    LC_TELEPHONE = "en_GB.UTF-8";
    LC_TIME = "en_GB.UTF-8";
  };

  # Console configuration
  console = {
    font = "Lat2-Terminus16";
    keyMap = "us";
  };
}
```

#### Boot Configuration

```nix
{
  # Bootloader options
  boot = {
    loader = {
      systemd-boot = {
        enable = true;
        configurationLimit = 10;  # Keep only 10 generations
      };
      efi.canTouchEfiVariables = true;
      timeout = 5;  # Boot menu timeout
    };

    # Kernel configuration
    kernelPackages = pkgs.linuxPackages_latest;
    kernelParams = [ "quiet" "splash" ];

    # Kernel modules
    kernelModules = [ "kvm-intel" ];
    extraModulePackages = [ ];

    # Initial ramdisk
    initrd = {
      availableKernelModules = [ "xhci_pci" "ahci" "usb_storage" "sd_mod" ];
      kernelModules = [ ];
    };
  };
}
```

#### Package Management

```nix
{
  # System-wide packages
  environment.systemPackages = with pkgs; [
    # Core utilities
    coreutils
    findutils
    gnugrep
    gnused

    # Network tools
    curl
    wget
    openssh

    # Development
    git
    vim
    gcc

    # Desktop applications
    firefox
    thunderbird
    libreoffice
  ];

  # Package overlays (custom package versions)
  nixpkgs.overlays = [
    (final: prev: {
      # Custom package override
      firefox = prev.firefox.override {
        enableGnomeExtensions = true;
      };
    })
  ];

  # Allow unfree packages
  nixpkgs.config.allowUnfree = true;
}
```

### Modular Configuration

Large configurations become unwieldy in a single file. NixOS supports modular configurations through imports:

#### Directory Structure

```
/etc/nixos/
├── configuration.nix          # Main configuration
├── hardware-configuration.nix # Generated hardware config
├── modules/
│   ├── desktop.nix           # Desktop environment
│   ├── development.nix       # Development tools
│   ├── gaming.nix            # Gaming setup
│   └── security.nix          # Security hardening
├── users/
│   ├── alice.nix            # Alice's user config
│   └── bob.nix              # Bob's user config
└── services/
    ├── nginx.nix            # Nginx web server
    ├── postgresql.nix       # PostgreSQL database
    └── monitoring.nix       # System monitoring
```

#### Main Configuration File

```nix
# configuration.nix
{ config, pkgs, ... }:
{
  imports = [
    ./hardware-configuration.nix
    ./modules/desktop.nix
    ./modules/development.nix
    ./modules/security.nix
    ./users/alice.nix
    ./services/nginx.nix
  ];

  # Basic system configuration
  networking.hostName = "nixos-server";
  time.timeZone = "UTC";

  system.stateVersion = "25.05";
}
```

#### Module Examples

**Desktop Module (`modules/desktop.nix`):**
```nix
{ config, pkgs, ... }:
{
  # X11 and desktop environment
  services.xserver = {
    enable = true;
    layout = "us";
    xkbVariant = "";

    displayManager.gdm.enable = true;
    desktopManager.gnome.enable = true;
  };

  # Audio
  sound.enable = true;
  hardware.pulseaudio.enable = true;

  # Fonts
  fonts.packages = with pkgs; [
    noto-fonts
    noto-fonts-cjk
    noto-fonts-emoji
    liberation_ttf
    fira-code
    fira-code-symbols
  ];

  # Desktop packages
  environment.systemPackages = with pkgs; [
    gnome.gnome-tweaks
    gnome.dconf-editor
    firefox
    thunderbird
    libreoffice
    gimp
    vlc
  ];
}
```

**Development Module (`modules/development.nix`):**
```nix
{ config, pkgs, ... }:
{
  # Development packages
  environment.systemPackages = with pkgs; [
    # Version control
    git
    gitg

    # Editors and IDEs
    vim
    neovim
    vscode

    # Programming languages
    python3
    nodejs
    rustc
    cargo
    go

    # Build tools
    gnumake
    cmake
    gcc
    clang

    # Containerization
    docker
    docker-compose

    # Database clients
    postgresql
    sqlite
  ];

  # Docker configuration
  virtualisation.docker = {
    enable = true;
    enableOnBoot = true;
  };

  # Development services
  services.postgresql = {
    enable = true;
    package = pkgs.postgresql_15;
    enableTCPIP = true;
  };
}
```

**User Module (`users/alice.nix`):**
```nix
{ config, pkgs, ... }:
{
  users.users.alice = {
    isNormalUser = true;
    description = "Alice Smith";
    extraGroups = [ "networkmanager" "wheel" "docker" "audio" "video" ];

    # User-specific packages
    packages = with pkgs; [
      kate
      konsole
      okular
      spectacle

      # Development tools
      jetbrains.idea-community
      insomnia
      postman
    ];

    # SSH public keys
    openssh.authorizedKeys.keys = [
      "ssh-rsa AAAAB3NzaC1yc2EAAAA... alice@laptop"
      "ssh-ed25519 AAAAC3NzaC1lZDI1... alice@phone"
    ];
  };

  # User-specific services
  systemd.user.services.backup-documents = {
    description = "Backup Alice's documents";
    serviceConfig = {
      Type = "oneshot";
      ExecStart = "${pkgs.rsync}/bin/rsync -av /home/alice/Documents/ /backup/alice-docs/";
    };
    startAt = "daily";
  };
}
```

### Configuration Best Practices

#### 1. Version Control Integration

```nix
# Keep your configuration in git
{ config, pkgs, ... }:
{
  # Include git information in system
  environment.etc."nixos-config-version".text =
    builtins.readFile (pkgs.runCommand "get-git-revision" {} ''
      cd ${./.}
      ${pkgs.git}/bin/git rev-parse HEAD > $out
    '');

  # System packages include git
  environment.systemPackages = with pkgs; [ git ];
}
```

#### 2. Conditional Configuration

```nix
{ config, pkgs, lib, ... }:
{
  # Conditional based on hostname
  services.nginx.enable = lib.mkIf (config.networking.hostName == "webserver") true;

  # Conditional based on hardware
  hardware.nvidia.modesetting.enable = lib.mkIf config.services.xserver.enable true;

  # Conditional package installation
  environment.systemPackages = with pkgs; [
    vim
    git
  ] ++ lib.optionals config.services.xserver.enable [
    firefox
    thunderbird
  ];
}
```

#### 3. Option Definitions

```nix
{ config, lib, pkgs, ... }:
with lib;
{
  options = {
    mySystem = {
      enableDevelopment = mkEnableOption "development tools and services";

      userName = mkOption {
        type = types.str;
        default = "user";
        description = "Primary user name";
      };

      extraPackages = mkOption {
        type = types.listOf types.package;
        default = [];
        description = "Additional packages to install";
      };
    };
  };

  config = mkIf config.mySystem.enableDevelopment {
    environment.systemPackages = with pkgs; [
      git
      vim
      gcc
    ] ++ config.mySystem.extraPackages;

    users.users.${config.mySystem.userName} = {
      isNormalUser = true;
      extraGroups = [ "wheel" "docker" ];
    };

    virtualisation.docker.enable = true;
  };
}
```

### Configuration Testing and Validation

#### 1. Dry Run Testing

```bash
# Test configuration without applying
sudo nixos-rebuild dry-build

# Test configuration in temporary environment
sudo nixos-rebuild test

# Build and switch (permanent)
sudo nixos-rebuild switch
```

#### 2. Configuration Validation

```bash
# Check Nix expression syntax
nix-instantiate --parse /etc/nixos/configuration.nix

# Evaluate configuration
nix-instantiate --eval '<nixpkgs/nixos>' -A config.system.build.toplevel

# Check for unused imports
nix-instantiate --eval /etc/nixos/configuration.nix --show-trace
```

#### 3. Rollback and Recovery

```bash
# List available generations
sudo nix-env --list-generations --profile /nix/var/nix/profiles/system

# Rollback to previous generation
sudo nixos-rebuild switch --rollback

# Boot specific generation
sudo /nix/var/nix/profiles/system-42-link/bin/switch-to-configuration boot
```

### ⚠️ Common Pitfalls

1. **Syntax Errors**: Nix is strict about syntax - missing semicolons or braces cause build failures
2. **Circular Imports**: Avoid importing files that import each other
3. **Hardcoded Paths**: Use `pkgs` references instead of absolute paths like `/usr/bin/vim`
4. **Missing Dependencies**: Ensure all referenced packages are available
5. **State Version Changes**: Never change `system.stateVersion` after initial installation

### ✅ Best Practices

1. **Use Modules**: Split large configurations into logical modules
2. **Version Control**: Keep your configuration in git with meaningful commits
3. **Document Changes**: Comment complex configurations and workarounds
4. **Test First**: Use `nixos-rebuild test` before permanent changes
5. **Backup Configurations**: Keep backups of working configurations
6. **Consistent Style**: Use consistent indentation and naming conventions

### 🏋️ Exercise 3: Modular Configuration

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 35 minutes

Create a modular NixOS configuration with the following structure:
1. Main configuration that imports modules
2. A desktop module with GNOME and common applications
3. A development module with programming tools
4. A user module for a developer account
5. A services module with SSH and firewall configuration

<details>
<summary>💡 Click to see hints</summary>

- Create separate `.nix` files for each module
- Use `imports = [ ./module-name.nix ];` to include modules
- Each module should be a function returning an attribute set
- Group related configuration options together
- Use descriptive names for modules and options

</details>

<details>
<summary>✅ Click to see solution</summary>

**Directory Structure:**
```
/etc/nixos/
├── configuration.nix
├── hardware-configuration.nix
├── modules/
│   ├── desktop.nix
│   ├── development.nix
│   ├── services.nix
│   └── users.nix
```

**Main Configuration (`configuration.nix`):**
```nix
{ config, pkgs, ... }:
{
  imports = [
    ./hardware-configuration.nix
    ./modules/desktop.nix
    ./modules/development.nix
    ./modules/services.nix
    ./modules/users.nix
  ];

  # System basics
  networking.hostName = "nixos-modular";
  time.timeZone = "America/New_York";
  i18n.defaultLocale = "en_US.UTF-8";

  # Boot configuration
  boot.loader.systemd-boot.enable = true;
  boot.loader.efi.canTouchEfiVariables = true;

  # Networking
  networking.networkmanager.enable = true;

  system.stateVersion = "25.05";
}
```

**Desktop Module (`modules/desktop.nix`):**
```nix
{ config, pkgs, ... }:
{
  # X11 and GNOME
  services.xserver = {
    enable = true;
    displayManager.gdm.enable = true;
    desktopManager.gnome.enable = true;
    layout = "us";
  };

  # Audio
  sound.enable = true;
  hardware.pulseaudio.enable = true;

  # Fonts
  fonts.packages = with pkgs; [
    noto-fonts
    noto-fonts-emoji
    fira-code
    liberation_ttf
  ];

  # Desktop applications
  environment.systemPackages = with pkgs; [
    # GNOME utilities
    gnome.gnome-tweaks
    gnome.dconf-editor

    # Applications
    firefox
    thunderbird
    libreoffice
    gimp
    vlc

    # System utilities
    htop
    tree
    unzip
    wget
  ];

  # GNOME services
  services.gnome = {
    gnome-keyring.enable = true;
    sushi.enable = true;
  };
}
```

**Development Module (`modules/development.nix`):**
```nix
{ config, pkgs, ... }:
{
  # Development packages
  environment.systemPackages = with pkgs; [
    # Editors
    vim
    neovim
    vscode

    # Version control
    git
    gitg

    # Programming languages
    python3
    nodejs
    yarn
    rustc
    cargo
    go

    # Build tools
    gcc
    gnumake
    cmake

    # Containers
    docker
    docker-compose

    # Database tools
    postgresql
    sqlite
    dbeaver
  ];

  # Docker
  virtualisation.docker = {
    enable = true;
    enableOnBoot = true;
  };

  # PostgreSQL
  services.postgresql = {
    enable = true;
    package = pkgs.postgresql_15;
    enableTCPIP = true;
    authentication = pkgs.lib.mkOverride 10 ''
      local all all trust
      host all all 127.0.0.1/32 trust
      host all all ::1/128 trust
    '';
  };

  # Development environment variables
  environment.variables = {
    EDITOR = "vim";
    BROWSER = "firefox";
  };
}
```

**Services Module (`modules/services.nix`):**
```nix
{ config, pkgs, ... }:
{
  # SSH configuration
  services.openssh = {
    enable = true;
    settings = {
      PasswordAuthentication = false;
      KbdInteractiveAuthentication = false;
      PermitRootLogin = "no";
    };
    ports = [ 22 ];
  };

  # Firewall
  networking.firewall = {
    enable = true;
    allowedTCPPorts = [ 22 80 443 ];
    allowedUDPPorts = [ ];
  };

  # Automatic system updates
  system.autoUpgrade = {
    enable = true;
    dates = "04:00";
    allowReboot = false;
  };

  # Automatic garbage collection
  nix.gc = {
    automatic = true;
    dates = "weekly";
    options = "--delete-older-than 7d";
  };

  # System monitoring
  services.prometheus = {
    enable = false;  # Enable if needed
    port = 9090;
  };
}
```

**Users Module (`modules/users.nix`):**
```nix
{ config, pkgs, ... }:
{
  # Developer user
  users.users.dev = {
    isNormalUser = true;
    description = "Developer";
    extraGroups = [
      "wheel"
      "networkmanager"
      "docker"
      "audio"
      "video"
    ];

    packages = with pkgs; [
      # User-specific applications
      kate
      konsole
      firefox

      # Development tools
      jetbrains.idea-community
      postman
    ];

    # SSH keys
    openssh.authorizedKeys.keys = [
      "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAB... dev@workstation"
    ];
  };

  # Guest user (optional)
  users.users.guest = {
    isNormalUser = true;
    description = "Guest User";
    extraGroups = [ "networkmanager" ];

    packages = with pkgs; [
      firefox
      libreoffice
    ];
  };

  # Sudo configuration
  security.sudo.wheelNeedsPassword = false;
}
```

**Explanation:**
This modular approach provides several benefits:

- **Organization**: Related configuration options are grouped logically
- **Reusability**: Modules can be easily enabled/disabled or shared between systems
- **Maintainability**: Each module has a specific purpose and can be updated independently
- **Scalability**: New modules can be added without affecting existing configuration
- **Testing**: Individual modules can be tested in isolation

The structure allows you to:
- Comment out module imports to disable entire feature sets
- Share modules between different NixOS systems
- Collaborate on configurations with team members
- Maintain different variants for different use cases (desktop, server, development)

</details>

[🔝 Back to top](#-nixos-documentation)

---

## 📦 Package Management

**📊 Chapter 4 of 20**

**🎯 Learning Objectives:**
- Master NixOS package management concepts
- Learn to search, install, and manage packages
- Understand package overlays and custom packages
- Practice with package configuration and user environments

**⏱️ Estimated Reading Time:** 25 minutes

**📋 Prerequisites:** Understanding of Nix configuration language basics

### Understanding Nix Package Management

NixOS uses the Nix package manager, which treats packages as immutable values stored in the Nix store. This approach eliminates dependency conflicts and enables atomic upgrades and rollbacks.

#### The Nix Store

All packages are stored in `/nix/store` with unique hash-based names:

```bash
# Example Nix store paths
/nix/store/abc123...-firefox-122.0.1/
/nix/store/def456...-python3-3.11.7/
/nix/store/ghi789...-gcc-13.2.0/
```

Each path represents a specific package build with its exact dependencies.

#### Package Channels

NixOS uses channels to provide sets of packages:

```bash
# List current channels
sudo nix-channel --list

# Add a channel
sudo nix-channel --add https://nixos.org/channels/nixos-25.05 nixos

# Update channels
sudo nix-channel --update

# Available channels:
# nixos-25.05 (stable)
# nixos-unstable (rolling release)
# nixos-25.05-small (minimal package set)
```

### System Package Management

#### Installing System Packages

System packages are declared in `configuration.nix`:

```nix
{ config, pkgs, ... }:
{
  environment.systemPackages = with pkgs; [
    # Core utilities
    vim
    git
    curl
    wget
    htop
    tree

    # Development tools
    gcc
    python3
    nodejs

    # Desktop applications
    firefox
    thunderbird
    libreoffice

    # System administration
    docker
    kubectl
    terraform
  ];
}
```

#### Package Search

Finding packages in the Nix ecosystem:

```bash
# Search packages online
nix search nixpkgs firefox
nix search nixpkgs python

# Search with more details
nix search nixpkgs --json python | jq

# Browse packages at https://search.nixos.org/packages
```

#### Package Information

Getting detailed package information:

```bash
# Show package information
nix show-derivation nixpkgs#firefox

# Show package dependencies
nix-store --query --requisites $(which firefox)

# Show package size
nix path-info -S nixpkgs#firefox

# Show all files in a package
nix-store --query --list $(which firefox)
```

### User Package Management

#### User Environments

Each user can have their own package environment:

```bash
# Install packages for current user
nix-env -i firefox
nix-env -i python3

# List installed packages
nix-env --query --installed

# Remove packages
nix-env --uninstall firefox

# Upgrade user packages
nix-env --upgrade
```

#### Home Manager

Home Manager provides declarative user environment management:

```nix
# Install Home Manager
nix-channel --add https://github.com/nix-community/home-manager/archive/release-25.05.tar.gz home-manager
nix-channel --update
```

**Home Manager Configuration (`~/.config/nixpkgs/home.nix`):**

```nix
{ config, pkgs, ... }:
{
  # Home Manager version
  home.stateVersion = "25.05";

  # User packages
  home.packages = with pkgs; [
    # Development
    vscode
    git
    nodejs
    python3

    # Utilities
    ripgrep
    fd
    bat
    exa

    # Applications
    firefox
    discord
    spotify
  ];

  # Program configurations
  programs = {
    # Git configuration
    git = {
      enable = true;
      userName = "John Doe";
      userEmail = "john@example.com";
      extraConfig = {
        init.defaultBranch = "main";
        pull.rebase = false;
      };
    };

    # Shell configuration
    bash = {
      enable = true;
      bashrcExtra = ''
        export EDITOR=vim
        alias ll='ls -la'
        alias grep='grep --color=auto'
      '';
    };

    # Terminal multiplexer
    tmux = {
      enable = true;
      shortcut = "a";
      extraConfig = ''
        set -g mouse on
        set -g default-terminal "screen-256color"
      '';
    };
  };

  # Service configuration
  services = {
    # GPG agent
    gpg-agent = {
      enable = true;
      defaultCacheTtl = 1800;
      enableSshSupport = true;
    };
  };
}
```

Activate Home Manager:

```bash
# Install and activate
nix-shell '<home-manager>' -A install
home-manager switch
```

### Advanced Package Management

#### Package Overlays

Overlays allow customizing packages without modifying the original package set:

```nix
{ config, pkgs, ... }:
{
  nixpkgs.overlays = [
    # Custom Firefox with specific extensions
    (final: prev: {
      firefox = prev.firefox.override {
        enableGnomeExtensions = true;
        extraNativeMessagingHosts = [ prev.gnome-browser-connector ];
      };
    })

    # Custom Python with additional packages
    (final: prev: {
      python3 = prev.python3.override {
        packageOverrides = pyFinal: pyPrev: {
          myCustomPackage = pyPrev.buildPythonPackage {
            pname = "my-package";
            version = "1.0";
            src = ./my-package;
          };
        };
      };
    })
  ];
}
```

#### Custom Package Definitions

Creating custom packages:

```nix
{ config, pkgs, ... }:
let
  myCustomApp = pkgs.stdenv.mkDerivation rec {
    pname = "my-custom-app";
    version = "1.2.3";

    src = pkgs.fetchFromGitHub {
      owner = "myuser";
      repo = "my-app";
      rev = "v${version}";
      sha256 = "sha256-AAAA...";
    };

    buildInputs = with pkgs; [ gcc cmake ];

    buildPhase = ''
      cmake .
      make
    '';

    installPhase = ''
      mkdir -p $out/bin
      cp my-app $out/bin/
    '';

    meta = with pkgs.lib; {
      description = "My custom application";
      homepage = "https://github.com/myuser/my-app";
      license = licenses.mit;
      maintainers = [ maintainers.myuser ];
      platforms = platforms.linux;
    };
  };
in
{
  environment.systemPackages = [ myCustomApp ];
}
```

#### Development Shells

Create project-specific development environments:

```nix
# shell.nix
{ pkgs ? import <nixpkgs> {} }:
pkgs.mkShell {
  buildInputs = with pkgs; [
    # Language-specific tools
    python3
    python3Packages.pip
    python3Packages.virtualenv

    # Development dependencies
    sqlite
    postgresql
    redis

    # Build tools
    gcc
    cmake
    pkg-config
  ];

  shellHook = ''
    echo "Entering development environment..."
    export PYTHONPATH=$PWD:$PYTHONPATH
    export DATABASE_URL="postgresql://localhost/myapp"

    # Create virtual environment if it doesn't exist
    if [ ! -d "venv" ]; then
      python -m venv venv
    fi
    source venv/bin/activate
  '';
}
```

Enter the development shell:

```bash
nix-shell
# or
nix develop  # Using flakes
```

### Package Configuration

#### Allowing Unfree Packages

Enable proprietary software:

```nix
{ config, pkgs, ... }:
{
  # Allow all unfree packages
  nixpkgs.config.allowUnfree = true;

  # Allow specific unfree packages
  nixpkgs.config.allowUnfreePredicate = pkg: builtins.elem (lib.getName pkg) [
    "vscode"
    "discord"
    "spotify"
    "zoom-us"
  ];

  environment.systemPackages = with pkgs; [
    vscode
    discord
    spotify
    zoom-us
  ];
}
```

#### Package-Specific Configuration

Configure packages with specific options:

```nix
{ config, pkgs, ... }:
{
  environment.systemPackages = with pkgs; [
    # Firefox with specific configuration
    (firefox.override {
      enableGnomeExtensions = true;
      extraNativeMessagingHosts = [ gnome-browser-connector ];
    })

    # Vim with custom plugins
    (vim_configurable.override {
      features = "huge";
      python3Support = true;
      luaSupport = true;
    })

    # Python with specific packages
    (python3.withPackages (ps: with ps; [
      numpy
      pandas
      matplotlib
      requests
      flask
    ]))
  ];
}
```

### Package Management Commands

#### Essential Commands

```bash
# System package management (requires rebuild)
sudo nixos-rebuild switch  # Apply configuration changes

# User package management
nix-env -i package-name    # Install package
nix-env -e package-name    # Remove package
nix-env -u                 # Upgrade all packages
nix-env --rollback         # Rollback to previous generation

# Package information
nix search nixpkgs python # Search packages
nix show nixpkgs#python   # Show package details
which python              # Find package location

# System maintenance
nix-collect-garbage        # Clean up old packages
nix-collect-garbage -d     # Delete old generations
sudo nix-collect-garbage -d # System-wide cleanup
```

#### Advanced Commands

```bash
# Build packages from source
nix-build -A firefox
nix-build '<nixpkgs>' -A python3

# Install packages temporarily
nix-shell -p python3 nodejs
nix run nixpkgs#firefox

# Package dependency analysis
nix-store --query --graph $(which firefox) | dot -Tpng > deps.png
nix why-depends /run/current-system nixpkgs#python3

# Store management
nix-store --verify --check-contents
nix-store --optimise
nix-store --repair-path /nix/store/...
```

### ⚠️ Common Pitfalls

1. **Mixing package managers**: Don't use `apt`, `yum`, or other package managers on NixOS
2. **Forgetting to rebuild**: System packages require `nixos-rebuild switch` to take effect
3. **User vs system packages**: Decide whether packages should be system-wide or user-specific
4. **Channel mismatches**: Keep channels consistent across system and users
5. **Unfree packages**: Remember to explicitly allow unfree packages when needed

### ✅ Best Practices

1. **Use system packages for services**: Install system services and daemons system-wide
2. **Use user packages for applications**: Install user applications per-user when possible
3. **Version your configuration**: Keep package lists in version-controlled configuration
4. **Regular cleanup**: Run garbage collection regularly to save disk space
5. **Test in user environment first**: Test packages as user before adding to system
6. **Document custom packages**: Comment why you need custom packages or overrides

### 🏋️ Exercise 4: Advanced Package Management

**Difficulty:** 🔴 Advanced
**Estimated Time:** 40 minutes

Set up a comprehensive package management configuration that includes:
1. System packages for development and server tools
2. User-specific packages via Home Manager
3. A custom package overlay for a modified version of Git
4. A development shell for a Python web application project
5. Proper unfree package handling

<details>
<summary>💡 Click to see hints</summary>

- System packages go in `environment.systemPackages`
- Home Manager needs to be installed and configured separately
- Overlays modify existing packages in `nixpkgs.overlays`
- Development shells use `mkShell` in a `shell.nix` file
- Unfree packages require `nixpkgs.config.allowUnfree = true`

</details>

<details>
<summary>✅ Click to see solution</summary>

**System Configuration (`/etc/nixos/configuration.nix`):**
```nix
{ config, pkgs, ... }:
{
  # Allow unfree packages
  nixpkgs.config.allowUnfree = true;

  # Custom overlay for modified Git
  nixpkgs.overlays = [
    (final: prev: {
      git = prev.git.override {
        withManual = true;
        pythonSupport = true;
      };

      # Custom development Python
      pythonDev = prev.python3.withPackages (ps: with ps; [
        flask
        django
        requests
        numpy
        pandas
        pytest
        black
        mypy
      ]);
    })
  ];

  # System packages
  environment.systemPackages = with pkgs; [
    # Core system tools
    vim
    git  # Using our custom overlay version
    curl
    wget
    htop
    tree
    unzip

    # Development tools
    gcc
    cmake
    nodejs
    yarn
    pythonDev  # Our custom Python with packages

    # Server tools
    docker
    docker-compose
    nginx
    postgresql
    redis

    # System administration
    systemctl
    journalctl
    nettools
    iotop

    # Unfree packages
    vscode
    discord
    spotify
  ];

  # Docker configuration
  virtualisation.docker = {
    enable = true;
    enableOnBoot = true;
  };

  # PostgreSQL service
  services.postgresql = {
    enable = true;
    package = pkgs.postgresql_15;
    enableTCPIP = true;
  };

  # Redis service
  services.redis = {
    servers."" = {
      enable = true;
      port = 6379;
    };
  };

  system.stateVersion = "25.05";
}
```

**Home Manager Configuration (`~/.config/nixpkgs/home.nix`):**
```nix
{ config, pkgs, ... }:
{
  home.stateVersion = "25.05";

  # User-specific packages
  home.packages = with pkgs; [
    # Development tools
    jetbrains.pycharm-community
    insomnia
    postman
    dbeaver

    # Text editors
    neovim
    emacs

    # Terminal utilities
    ripgrep
    fd
    bat
    exa
    fzf

    # Media and communication
    firefox
    thunderbird
    vlc
    gimp

    # Productivity
    libreoffice
    obsidian
    notion-app-enhanced
  ];

  # Program configurations
  programs = {
    # Git (enhanced configuration)
    git = {
      enable = true;
      userName = "Developer";
      userEmail = "dev@example.com";
      extraConfig = {
        init.defaultBranch = "main";
        pull.rebase = true;
        push.default = "current";
        core.editor = "vim";
        merge.tool = "vimdiff";
        diff.tool = "vimdiff";
      };
      aliases = {
        st = "status";
        co = "checkout";
        br = "branch";
        ci = "commit";
        unstage = "reset HEAD --";
        last = "log -1 HEAD";
        visual = "!gitk";
      };
    };

    # Enhanced shell
    zsh = {
      enable = true;
      enableAutosuggestions = true;
      enableCompletion = true;
      syntaxHighlighting.enable = true;

      shellAliases = {
        ll = "exa -la";
        ls = "exa";
        cat = "bat";
        find = "fd";
        grep = "rg";

        # Development aliases
        dcu = "docker-compose up";
        dcd = "docker-compose down";
        dcb = "docker-compose build";

        # NixOS aliases
        nrs = "sudo nixos-rebuild switch";
        nrt = "sudo nixos-rebuild test";
        hms = "home-manager switch";
      };

      initExtra = ''
        # Custom prompt
        autoload -U promptinit; promptinit
        prompt pure

        # Development environment variables
        export EDITOR=vim
        export BROWSER=firefox
        export PYTHONPATH=$HOME/projects:$PYTHONPATH

        # Docker aliases
        alias docker-clean='docker system prune -af'
        alias docker-reset='docker stop $(docker ps -q) && docker rm $(docker ps -aq)'
      '';
    };

    # Terminal multiplexer
    tmux = {
      enable = true;
      terminal = "screen-256color";
      shortcut = "a";
      keyMode = "vi";

      extraConfig = ''
        # Mouse support
        set -g mouse on

        # Status bar
        set -g status-bg colour235
        set -g status-fg colour136
        set -g status-left-length 20
        set -g status-right-length 50

        # Window navigation
        bind -n M-Left select-pane -L
        bind -n M-Right select-pane -R
        bind -n M-Up select-pane -U
        bind -n M-Down select-pane -D

        # Reload config
        bind r source-file ~/.tmux.conf \; display "Config reloaded!"
      '';
    };

    # File manager
    direnv = {
      enable = true;
      enableZshIntegration = true;
    };
  };

  # Services
  services = {
    # GPG agent
    gpg-agent = {
      enable = true;
      defaultCacheTtl = 1800;
      maxCacheTtl = 7200;
      enableSshSupport = true;
    };
  };
}
```

**Development Shell (`shell.nix` for Python web project):**
```nix
{ pkgs ? import <nixpkgs> {} }:
let
  pythonEnv = pkgs.python3.withPackages (ps: with ps; [
    # Web framework
    flask
    django
    fastapi
    uvicorn

    # Database
    psycopg2
    sqlalchemy
    alembic

    # Testing
    pytest
    pytest-cov
    pytest-mock
    factory-boy

    # Development tools
    black
    isort
    mypy
    pylint

    # Utilities
    requests
    python-dotenv
    click

    # Data processing
    numpy
    pandas
  ]);
in
pkgs.mkShell {
  name = "python-web-dev";

  buildInputs = with pkgs; [
    pythonEnv

    # Database servers
    postgresql
    redis

    # Development tools
    git
    vim
    tmux

    # Node.js for frontend assets
    nodejs
    yarn

    # System tools
    curl
    jq

    # Container tools
    docker
    docker-compose
  ];

  shellHook = ''
    echo "🐍 Python Web Development Environment"
    echo "Python version: $(python --version)"
    echo "Available services: PostgreSQL, Redis"
    echo ""

    # Environment variables
    export FLASK_APP=app.py
    export FLASK_ENV=development
    export DATABASE_URL="postgresql://localhost/webapp_dev"
    export REDIS_URL="redis://localhost:6379"
    export PYTHONPATH=$PWD:$PYTHONPATH

    # Create project directories if they don't exist
    mkdir -p {static,templates,tests,migrations}

    # Start services if not running
    if ! pgrep -x postgres > /dev/null; then
      echo "Starting PostgreSQL..."
      pg_ctl -D ~/.postgresql start
    fi

    if ! pgrep -x redis-server > /dev/null; then
      echo "Starting Redis..."
      redis-server --daemonize yes
    fi

    # Virtual environment setup
    if [ ! -d ".venv" ]; then
      echo "Creating virtual environment..."
      python -m venv .venv
    fi

    echo "To activate: source .venv/bin/activate"
    echo "To run tests: pytest"
    echo "To format code: black ."
  '';
}
```

**Project `.envrc` file (for direnv integration):**
```bash
# .envrc
use nix
export FLASK_APP=app.py
export FLASK_ENV=development
export DATABASE_URL="postgresql://localhost/webapp_dev"
export REDIS_URL="redis://localhost:6379"

# Auto-activate virtual environment if it exists
if [ -d ".venv" ]; then
  source .venv/bin/activate
fi
```

**Usage Instructions:**
```bash
# Enter development shell
nix-shell

# Or with direnv (automatic)
cd project-directory  # Automatically enters shell

# Install Home Manager
home-manager switch

# Apply system configuration
sudo nixos-rebuild switch
```

**Explanation:**
This comprehensive setup demonstrates advanced NixOS package management:

- **System-Level**: Core development tools and services are installed system-wide
- **Custom Overlays**: Git is customized with additional features, and a Python environment is pre-configured
- **User-Level**: Personal applications and configurations through Home Manager
- **Development Environment**: Project-specific shell with all dependencies and services
- **Service Integration**: PostgreSQL and Redis are configured and auto-started
- **Automation**: direnv automatically loads the development environment when entering project directories

The layered approach provides:
- **Reproducibility**: Exact same environment across machines
- **Isolation**: Project dependencies don't interfere with system
- **Convenience**: Automatic environment activation and service management
- **Flexibility**: Easy to modify for different projects or requirements

</details>

[🔝 Back to top](#-nixos-documentation)

---

## 🏗️ System Configuration

**📊 Chapter 5 of 20**

**🎯 Learning Objectives:**
- Master system-level configuration options
- Learn hardware-specific configurations
- Understand boot and kernel management
- Configure system services and daemons

**⏱️ Estimated Reading Time:** 20 minutes

**📋 Prerequisites:** Basic NixOS configuration knowledge

### Boot Configuration

#### Bootloader Options

**UEFI with systemd-boot (recommended):**
```nix
{ config, pkgs, ... }:
{
  boot.loader = {
    systemd-boot = {
      enable = true;
      configurationLimit = 20;  # Keep 20 generations
      editor = false;           # Disable boot entry editing
    };
    efi.canTouchEfiVariables = true;
    timeout = 5;
  };
}
```

**UEFI with GRUB:**
```nix
{
  boot.loader = {
    grub = {
      enable = true;
      version = 2;
      efiSupport = true;
      device = "nodev";
      useOSProber = true;  # Detect other OS installations
    };
    efi.canTouchEfiVariables = true;
  };
}
```

**Legacy BIOS with GRUB:**
```nix
{
  boot.loader.grub = {
    enable = true;
    version = 2;
    device = "/dev/sda";  # Install GRUB to MBR
  };
}
```

#### Kernel Configuration

```nix
{
  boot = {
    # Kernel selection
    kernelPackages = pkgs.linuxPackages_latest;
    # Available options:
    # - pkgs.linuxPackages        (default stable)
    # - pkgs.linuxPackages_latest (latest stable)
    # - pkgs.linuxPackages_lts    (long-term support)
    # - pkgs.linuxPackages_zen    (optimized for desktop)

    # Kernel parameters
    kernelParams = [
      "quiet"                    # Reduce boot messages
      "splash"                   # Show splash screen
      "elevator=deadline"        # I/O scheduler for SSDs
      "intel_iommu=on"          # Enable Intel IOMMU
    ];

    # Kernel modules
    kernelModules = [
      "kvm-intel"     # Intel virtualization
      "vfio-pci"      # PCI passthrough
    ];
    extraModulePackages = with config.boot.kernelPackages; [
      v4l2loopback   # Virtual video device
    ];

    # Kernel sysctl parameters
    kernel.sysctl = {
      "vm.swappiness" = 10;              # Reduce swap usage
      "net.core.rmem_max" = 134217728;   # Network buffer size
      "net.core.wmem_max" = 134217728;
    };

    # Initial ramdisk
    initrd = {
      availableKernelModules = [ "xhci_pci" "ahci" "usb_storage" "sd_mod" ];
      kernelModules = [ "dm-snapshot" ];

      # LUKS encryption support
      luks.devices = {
        root = {
          device = "/dev/disk/by-uuid/your-uuid-here";
          preLVM = true;
        };
      };
    };
  };
}
```

### Hardware Configuration

#### Graphics Configuration

**NVIDIA Graphics:**
```nix
{
  # Enable OpenGL
  hardware.opengl = {
    enable = true;
    driSupport = true;
    driSupport32Bit = true;  # For 32-bit applications
  };

  # NVIDIA drivers
  services.xserver.videoDrivers = [ "nvidia" ];
  hardware.nvidia = {
    modesetting.enable = true;
    powerManagement.enable = false;
    powerManagement.finegrained = false;
    open = false;  # Use proprietary driver
    nvidiaSettings = true;  # Enable nvidia-settings

    package = config.boot.kernelPackages.nvidiaPackages.stable;
    # Available versions:
    # - stable (recommended)
    # - beta
    # - vulkan_beta
    # - legacy_470
    # - legacy_390
  };
}
```

**AMD Graphics:**
```nix
{
  hardware.opengl = {
    enable = true;
    driSupport = true;
    driSupport32Bit = true;

    # AMD-specific packages
    extraPackages = with pkgs; [
      rocm-opencl-icd
      rocm-opencl-runtime
      amdvlk
    ];
    extraPackages32 = with pkgs; [
      driversi686Linux.amdvlk
    ];
  };

  # AMD GPU drivers
  services.xserver.videoDrivers = [ "amdgpu" ];

  # Vulkan support
  hardware.opengl.driSupport = true;
  hardware.opengl.driSupport32Bit = true;
}
```

**Intel Graphics:**
```nix
{
  hardware.opengl = {
    enable = true;
    extraPackages = with pkgs; [
      intel-media-driver  # For newer GPUs (Broadwell+)
      vaapiIntel         # For older GPUs
      vaapiVdpau
      libvdpau-va-gl
    ];
  };

  services.xserver.videoDrivers = [ "intel" ];

  # Intel GPU-specific settings
  environment.variables = {
    VDPAU_DRIVER = "va_gl";
  };
}
```

#### Audio Configuration

**PipeWire (modern, recommended):**
```nix
{
  # Disable PulseAudio
  hardware.pulseaudio.enable = false;

  # Enable real-time audio
  security.rtkit.enable = true;

  # PipeWire configuration
  services.pipewire = {
    enable = true;
    alsa.enable = true;
    alsa.support32Bit = true;
    pulse.enable = true;
    jack.enable = true;  # For professional audio

    # PipeWire configuration
    config.pipewire = {
      "context.properties" = {
        "link.max-buffers" = 16;
        "log.level" = 2;
        "default.clock.rate" = 48000;
        "default.clock.quantum" = 1024;
        "default.clock.min-quantum" = 32;
        "default.clock.max-quantum" = 8192;
      };
    };
  };

  # Additional audio packages
  environment.systemPackages = with pkgs; [
    pavucontrol    # Volume control GUI
    helvum         # PipeWire patchbay
    qpwgraph       # Graph-based patchbay
  ];
}
```

**PulseAudio (traditional):**
```nix
{
  sound.enable = true;
  hardware.pulseaudio = {
    enable = true;
    support32Bit = true;
    package = pkgs.pulseaudioFull;  # Full version with all modules

    # Extra modules
    extraModules = [ pkgs.pulseaudio-modules-bt ];  # Bluetooth support

    # Configuration
    extraConfig = ''
      load-module module-switch-on-connect
      load-module module-native-protocol-tcp auth-ip-acl=127.0.0.1
    '';
  };

  # Bluetooth audio
  hardware.bluetooth = {
    enable = true;
    hsphfpd.enable = true;  # HSP/HFP daemon
  };
}
```

#### Input Devices

**Keyboard and Mouse:**
```nix
{
  services.xserver = {
    enable = true;

    # Keyboard configuration
    layout = "us";
    xkbVariant = "dvorak";  # Keyboard variant
    xkbOptions = "caps:escape,compose:ralt";  # Caps as Escape, Right Alt as Compose

    # Mouse configuration
    libinput = {
      enable = true;
      mouse = {
        accelProfile = "flat";      # Disable mouse acceleration
        accelSpeed = "0";           # Mouse speed
        middleEmulation = false;    # Disable middle click emulation
      };

      touchpad = {
        naturalScrolling = true;    # Reverse scroll direction
        tapping = true;            # Tap to click
        disableWhileTyping = true; # Disable while typing
        scrollMethod = "twofinger"; # Two-finger scrolling
      };
    };
  };

  # Console keyboard layout
  console.keyMap = "dvorak";
}
```

### System Services Configuration

#### Network Time Protocol

```nix
{
  # System time configuration
  time.timeZone = "America/New_York";

  # NTP synchronization
  services.ntp = {
    enable = true;
    servers = [
      "0.nixos.pool.ntp.org"
      "1.nixos.pool.ntp.org"
      "2.nixos.pool.ntp.org"
      "3.nixos.pool.ntp.org"
    ];
  };

  # Or use systemd-timesyncd (lighter alternative)
  services.timesyncd = {
    enable = false;  # Don't enable both NTP and timesyncd
    servers = [ "time.cloudflare.com" ];
  };
}
```

#### System Logging

```nix
{
  # Systemd journal configuration
  services.journald.extraConfig = ''
    SystemMaxUse=500M
    MaxRetentionSec=1week
    MaxFileSec=1day
    ForwardToSyslog=no
  '';

  # Traditional syslog (optional)
  services.rsyslog = {
    enable = false;
    defaultConfig = ''
      *.info;mail.none;authpriv.none;cron.none /var/log/messages
      authpriv.* /var/log/secure
      mail.* -/var/log/maillog
      cron.* /var/log/cron
      *.emerg *
    '';
  };
}
```

#### Power Management

```nix
{
  # Power management
  powerManagement = {
    enable = true;
    cpuFreqGovernor = "ondemand";  # CPU frequency scaling
    powertop.enable = true;        # PowerTOP for power optimization
  };

  # Laptop-specific settings
  services.tlp = {
    enable = true;  # TLP for laptop power management
    settings = {
      CPU_SCALING_GOVERNOR_ON_AC = "performance";
      CPU_SCALING_GOVERNOR_ON_BAT = "powersave";

      CPU_ENERGY_PERF_POLICY_ON_AC = "performance";
      CPU_ENERGY_PERF_POLICY_ON_BAT = "power";

      PLATFORM_PROFILE_ON_AC = "performance";
      PLATFORM_PROFILE_ON_BAT = "low-power";

      START_CHARGE_THRESH_BAT0 = 40;  # Battery charge thresholds
      STOP_CHARGE_THRESH_BAT0 = 80;
    };
  };

  # Auto-suspend configuration
  systemd.sleep.extraConfig = ''
    HibernateDelaySec=30min
    SuspendState=mem
  '';
}
```

### File Systems and Storage

#### File System Configuration

```nix
{
  # Root filesystem
  fileSystems."/" = {
    device = "/dev/disk/by-label/nixos";
    fsType = "ext4";
    options = [ "noatime" ];  # Disable access time updates for performance
  };

  # Boot partition (UEFI)
  fileSystems."/boot" = {
    device = "/dev/disk/by-label/boot";
    fsType = "vfat";
  };

  # Home partition
  fileSystems."/home" = {
    device = "/dev/disk/by-label/home";
    fsType = "ext4";
    options = [ "noatime" "user_xattr" ];
  };

  # Temporary filesystem in RAM
  fileSystems."/tmp" = {
    device = "tmpfs";
    fsType = "tmpfs";
    options = [ "noatime" "nodev" "nosuid" "size=2G" ];
  };

  # External storage auto-mounting
  services.udisks2.enable = true;  # For removable storage
}
```

#### Swap Configuration

```nix
{
  # Traditional swap partition
  swapDevices = [
    { device = "/dev/disk/by-label/swap"; }
  ];

  # Swap file (alternative)
  swapDevices = [
    {
      device = "/swapfile";
      size = 8192;  # 8GB swap file
    }
  ];

  # Encrypted swap
  swapDevices = [
    {
      device = "/dev/disk/by-label/swap";
      encrypted = {
        enable = true;
        keyFile = "/mnt-root/root/swap.key";
        label = "swap";
      };
    }
  ];

  # Zram swap (compressed RAM swap)
  zramSwap = {
    enable = true;
    algorithm = "zstd";    # Compression algorithm
    memoryPercent = 25;    # Use 25% of RAM for zram
  };
}
```

### ⚠️ Common Pitfalls

1. **Bootloader conflicts**: Don't enable multiple bootloaders simultaneously
2. **Graphics driver issues**: Ensure compatible drivers for your GPU
3. **Audio conflicts**: Don't enable both PulseAudio and PipeWire
4. **Kernel module dependencies**: Some modules require specific kernel parameters
5. **File system options**: Incorrect mount options can cause boot failures

### ✅ Best Practices

1. **Hardware detection**: Use `nixos-generate-config` to detect hardware initially
2. **Driver testing**: Test graphics drivers in a VM or with `nixos-rebuild test` first
3. **Service conflicts**: Research service interactions before enabling multiple similar services
4. **Performance tuning**: Monitor system performance and adjust settings incrementally
5. **Documentation**: Keep notes about hardware-specific configurations

### 🏋️ Exercise 5: Complete System Configuration

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 30 minutes

Configure a complete NixOS system with:
1. UEFI boot with systemd-boot, keeping 15 generations
2. Latest kernel with custom parameters for better performance
3. NVIDIA graphics with proprietary drivers
4. PipeWire audio system with professional audio support
5. Optimized power management for a desktop system
6. Custom file system layout with separate /home and tmpfs /tmp

<details>
<summary>💡 Click to see hints</summary>

- Use `boot.loader.systemd-boot.configurationLimit` for generation limit
- Kernel parameters go in `boot.kernelParams`
- NVIDIA configuration requires `hardware.nvidia` and `services.xserver.videoDrivers`
- PipeWire needs `services.pipewire` with JACK support enabled
- Desktop power management should use "performance" governor
- File systems are configured in `fileSystems.<mountpoint>`

</details>

<details>
<summary>✅ Click to see solution</summary>

```nix
{ config, pkgs, ... }:
{
  imports = [
    ./hardware-configuration.nix
  ];

  # Boot Configuration
  boot = {
    loader = {
      systemd-boot = {
        enable = true;
        configurationLimit = 15;  # Keep 15 generations
        editor = false;           # Security: disable boot editing
      };
      efi = {
        canTouchEfiVariables = true;
        efiSysMountPoint = "/boot";
      };
      timeout = 3;  # Quick boot
    };

    # Latest kernel with performance optimizations
    kernelPackages = pkgs.linuxPackages_latest;
    kernelParams = [
      "quiet"                           # Reduce boot messages
      "splash"                          # Show splash screen
      "elevator=mq-deadline"            # Better scheduler for SSDs
      "intel_iommu=on"                 # Enable IOMMU
      "iommu=pt"                       # Pass-through mode
      "default_hugepagesz=1G"          # Large page support
      "hugepagesz=1G"
      "hugepages=8"                    # 8GB huge pages
      "transparent_hugepage=always"    # Enable THP
      "preempt=voluntary"              # Better desktop responsiveness
    ];

    # Kernel modules
    kernelModules = [
      "kvm-intel"      # Intel virtualization
      "vfio-pci"       # GPU passthrough support
      "coretemp"       # CPU temperature monitoring
    ];

    # Kernel sysctl optimizations
    kernel.sysctl = {
      # Memory management
      "vm.swappiness" = 5;                    # Minimize swap usage
      "vm.dirty_ratio" = 15;                  # Dirty page writeback
      "vm.dirty_background_ratio" = 10;
      "vm.vfs_cache_pressure" = 50;           # Inode/dentry cache pressure

      # Network optimizations
      "net.core.rmem_max" = 134217728;        # Max receive buffer
      "net.core.wmem_max" = 134217728;        # Max send buffer
      "net.core.netdev_max_backlog" = 5000;   # Network device backlog
      "net.ipv4.tcp_congestion_control" = "bbr"; # Better congestion control

      # Security
      "kernel.kptr_restrict" = 2;             # Hide kernel addresses
      "kernel.dmesg_restrict" = 1;            # Restrict dmesg access
      "net.ipv4.ip_forward" = 0;              # Disable IP forwarding
    };

    # Initial ramdisk
    initrd = {
      availableKernelModules = [
        "xhci_pci" "ahci" "nvme" "usb_storage" "sd_mod"
      ];
      kernelModules = [ "dm-snapshot" ];
    };
  };

  # File System Configuration
  fileSystems = {
    "/" = {
      device = "/dev/disk/by-label/nixos";
      fsType = "ext4";
      options = [
        "noatime"         # Disable access time updates
        "nodiratime"      # Disable directory access time updates
        "discard"         # Enable TRIM for SSDs
      ];
    };

    "/boot" = {
      device = "/dev/disk/by-label/boot";
      fsType = "vfat";
    };

    "/home" = {
      device = "/dev/disk/by-label/home";
      fsType = "ext4";
      options = [
        "noatime"
        "nodiratime"
        "discard"
        "user_xattr"      # Extended attributes support
      ];
    };

    # Temporary filesystem in RAM for better performance
    "/tmp" = {
      device = "tmpfs";
      fsType = "tmpfs";
      options = [
        "noatime"
        "nodev"
        "nosuid"
        "size=4G"         # 4GB tmpfs
        "mode=1777"       # Proper permissions
      ];
    };
  };

  # Swap configuration
  swapDevices = [
    {
      device = "/dev/disk/by-label/swap";
      priority = 1;  # Higher priority
    }
  ];

  # Alternative: zram for better performance
  # zramSwap = {
  #   enable = true;
  #   algorithm = "zstd";
  #   memoryPercent = 20;
  # };

  # Graphics Configuration - NVIDIA
  hardware.opengl = {
    enable = true;
    driSupport = true;
    driSupport32Bit = true;  # For Steam and 32-bit games

    extraPackages = with pkgs; [
      vaapiVdpau
      libvdpau-va-gl
    ];
  };

  services.xserver.videoDrivers = [ "nvidia" ];
  hardware.nvidia = {
    modesetting.enable = true;
    powerManagement.enable = false;        # Desktop system
    powerManagement.finegrained = false;
    open = false;                          # Use proprietary driver
    nvidiaSettings = true;                 # Enable nvidia-settings GUI

    package = config.boot.kernelPackages.nvidiaPackages.stable;

    # Force composition pipeline (reduces tearing)
    forceFullCompositionPipeline = true;
  };

  # Audio Configuration - PipeWire with Professional Audio
  hardware.pulseaudio.enable = false;  # Disable PulseAudio
  security.rtkit.enable = true;         # Real-time scheduling

  services.pipewire = {
    enable = true;
    alsa.enable = true;
    alsa.support32Bit = true;
    pulse.enable = true;       # PulseAudio compatibility
    jack.enable = true;        # Professional audio support

    # Professional audio configuration
    config.pipewire = {
      "context.properties" = {
        "link.max-buffers" = 16;
        "log.level" = 2;
        "default.clock.rate" = 48000;       # Professional sample rate
        "default.clock.quantum" = 512;      # Low latency
        "default.clock.min-quantum" = 32;
        "default.clock.max-quantum" = 2048;
      };
    };

    # JACK configuration for pro audio
    config.pipewire-pulse = {
      "pulse.properties" = {
        "pulse.min.req" = "32/48000";       # Low latency settings
        "pulse.default.req" = "512/48000";
        "pulse.max.req" = "2048/48000";
        "pulse.min.quantum" = "32/48000";
        "pulse.max.quantum" = "2048/48000";
      };
    };
  };

  # Power Management - Desktop Optimized
  powerManagement = {
    enable = true;
    cpuFreqGovernor = "performance";  # Always max performance for desktop
  };

  # Additional power settings
  services.thermald.enable = true;    # Thermal management
  services.auto-cpufreq.enable = false;  # Don't use auto CPU frequency on desktop

  # System time
  time.timeZone = "America/New_York";
  services.ntp.enable = true;

  # Basic system configuration
  networking.hostName = "nixos-performance";
  networking.networkmanager.enable = true;

  # Desktop Environment
  services.xserver = {
    enable = true;
    displayManager.gdm.enable = true;
    desktopManager.gnome.enable = true;

    # Input configuration
    layout = "us";
    libinput = {
      enable = true;
      mouse.accelProfile = "flat";  # Disable mouse acceleration
    };
  };

  # Performance monitoring tools
  environment.systemPackages = with pkgs; [
    # System monitoring
    htop
    iotop
    nvtop          # NVIDIA GPU monitoring
    lm_sensors     # Hardware sensors
    stress-ng      # System stress testing

    # Audio tools
    pavucontrol    # PulseAudio/PipeWire volume control
    helvum         # PipeWire patchbay
    qjackctl       # JACK connection kit

    # Performance tools
    perf-tools
    sysstat        # System activity reporter
  ];

  # System services
  services.fstrim.enable = true;  # Automatic SSD TRIM

  system.stateVersion = "25.05";
}
```

**Explanation:**
This configuration optimizes NixOS for a high-performance desktop system:

- **Boot Optimization**: Latest kernel with performance-focused parameters and limited generation retention
- **Memory Management**: Tuned virtual memory settings and huge pages support for better performance
- **Graphics**: NVIDIA proprietary drivers with composition pipeline to reduce screen tearing
- **Audio**: PipeWire with professional audio support and low-latency settings for audio production
- **Storage**: Optimized mount options with TRIM support and tmpfs for temporary files
- **Power**: Desktop-focused settings prioritizing performance over power saving
- **Monitoring**: Comprehensive tools for system and hardware monitoring

The system is configured for maximum performance while maintaining stability and professional audio capabilities.

</details>

[🔝 Back to top](#-nixos-documentation)

---

## 🔧 Service Management

**📊 Chapter 6 of 20**

**🎯 Learning Objectives:**
- Master systemd service management in NixOS
- Learn to configure and customize system services
- Understand service dependencies and ordering
- Practice creating custom services

**⏱️ Estimated Reading Time:** 20 minutes

**📋 Prerequisites:** Basic system configuration knowledge

### Understanding Systemd in NixOS

NixOS uses systemd as its init system and service manager. Services are configured declaratively in your NixOS configuration, making them reproducible and version-controlled.

#### Basic Service Configuration

```nix
{ config, pkgs, ... }:
{
  # Enable common services
  services = {
    # SSH daemon
    openssh = {
      enable = true;
      settings = {
        PasswordAuthentication = false;
        KbdInteractiveAuthentication = false;
        PermitRootLogin = "no";
      };
      ports = [ 22 ];
    };

    # Web server
    nginx = {
      enable = true;
      recommendedGzipSettings = true;
      recommendedOptimisation = true;
      recommendedProxySettings = true;
      recommendedTlsSettings = true;

      virtualHosts."example.com" = {
        enableACME = true;
        forceSSL = true;
        root = "/var/www/example.com";
      };
    };

    # Database
    postgresql = {
      enable = true;
      package = pkgs.postgresql_15;
      enableTCPIP = true;
      authentication = pkgs.lib.mkOverride 10 ''
        local all all trust
        host all all 127.0.0.1/32 md5
        host all all ::1/128 md5
      '';
      initialScript = pkgs.writeText "backend-initScript" ''
        CREATE ROLE myuser WITH LOGIN PASSWORD 'mypassword' CREATEDB;
        CREATE DATABASE mydatabase;
        GRANT ALL PRIVILEGES ON DATABASE mydatabase TO myuser;
      '';
    };
  };
}
```

#### Service Management Commands

```bash
# Service status
systemctl status nginx
systemctl status postgresql

# Start/stop/restart services
sudo systemctl start nginx
sudo systemctl stop nginx
sudo systemctl restart nginx
sudo systemctl reload nginx

# Enable/disable services at boot
sudo systemctl enable nginx
sudo systemctl disable nginx

# View service logs
journalctl -u nginx
journalctl -u nginx -f  # Follow logs
journalctl -u nginx --since "1 hour ago"

# List all services
systemctl list-units --type=service
systemctl list-units --type=service --state=active
```

### Custom Service Creation

#### Simple Custom Service

```nix
{ config, pkgs, ... }:
{
  # Custom backup service
  systemd.services.backup-home = {
    description = "Backup home directory";
    serviceConfig = {
      Type = "oneshot";
      User = "backup";
      ExecStart = "${pkgs.rsync}/bin/rsync -av /home/ /backup/home/";
      StandardOutput = "journal";
      StandardError = "journal";
    };
  };

  # Timer for regular backups
  systemd.timers.backup-home = {
    description = "Run backup-home service daily";
    wantedBy = [ "timers.target" ];
    timerConfig = {
      OnCalendar = "daily";
      Persistent = true;
      RandomizedDelaySec = "30min";
    };
  };

  # Create backup user
  users.users.backup = {
    isSystemUser = true;
    group = "backup";
    createHome = true;
    home = "/var/lib/backup";
  };
  users.groups.backup = {};
}
```

#### Advanced Custom Service

```nix
{ config, pkgs, lib, ... }:
let
  myapp = pkgs.writeScriptBin "myapp" ''
    #!${pkgs.bash}/bin/bash
    echo "Starting My Application..."
    while true; do
      echo "Application is running at $(date)"
      sleep 60
    done
  '';
in
{
  systemd.services.myapp = {
    description = "My Custom Application";
    documentation = [ "https://github.com/user/myapp" ];

    # Dependencies
    wants = [ "network-online.target" ];
    after = [ "network-online.target" "postgresql.service" ];
    requires = [ "postgresql.service" ];

    serviceConfig = {
      Type = "simple";
      User = "myapp";
      Group = "myapp";

      # Command to run
      ExecStart = "${myapp}/bin/myapp";
      ExecReload = "${pkgs.coreutils}/bin/kill -HUP $MAINPID";

      # Restart behavior
      Restart = "always";
      RestartSec = "10s";

      # Security settings
      NoNewPrivileges = true;
      PrivateTmp = true;
      ProtectSystem = "strict";
      ProtectHome = true;
      ReadWritePaths = [ "/var/lib/myapp" ];

      # Resource limits
      MemoryMax = "512M";
      CPUQuota = "50%";

      # Environment
      Environment = [
        "NODE_ENV=production"
        "DATABASE_URL=postgresql://localhost/myapp"
      ];
      EnvironmentFile = "/etc/myapp/environment";

      # Working directory
      WorkingDirectory = "/var/lib/myapp";

      # Logging
      StandardOutput = "journal";
      StandardError = "journal";
      SyslogIdentifier = "myapp";
    };

    # Enable by default
    wantedBy = [ "multi-user.target" ];
  };

  # Create service user
  users.users.myapp = {
    isSystemUser = true;
    group = "myapp";
    createHome = true;
    home = "/var/lib/myapp";
  };
  users.groups.myapp = {};

  # Create configuration directory
  environment.etc."myapp/environment".text = ''
    LOG_LEVEL=info
    API_KEY=secret-key-here
  '';
}
```

### Service Dependencies and Ordering

#### Dependency Types

```nix
{
  systemd.services.myservice = {
    # Weak dependency - start if available
    wants = [ "network.target" ];

    # Strong dependency - fail if not available
    requires = [ "postgresql.service" ];

    # Ordering - start after these services
    after = [ "network.target" "postgresql.service" ];

    # Ordering - start before these services
    before = [ "multi-user.target" ];

    # Conflicts - don't run with these services
    conflicts = [ "other-service.service" ];

    # Bind to - stop when these services stop
    bindTo = [ "parent-service.service" ];
  };
}
```

### Common Service Configurations

#### Web Applications

```nix
{ config, pkgs, ... }:
{
  services.nginx = {
    enable = true;

    virtualHosts = {
      "api.example.com" = {
        forceSSL = true;
        enableACME = true;
        locations."/" = {
          proxyPass = "http://127.0.0.1:3000";
          proxyWebsockets = true;
          extraConfig = ''
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header X-Forwarded-Proto $scheme;
          '';
        };
      };

      "static.example.com" = {
        forceSSL = true;
        enableACME = true;
        root = "/var/www/static";
        extraConfig = ''
          expires 1y;
          add_header Cache-Control "public, immutable";
        '';
      };
    };
  };

  # Automatic SSL certificates
  security.acme = {
    acceptTerms = true;
    defaults.email = "admin@example.com";
  };
}
```

#### Database Services

```nix
{
  services = {
    # PostgreSQL
    postgresql = {
      enable = true;
      package = pkgs.postgresql_15;
      enableTCPIP = true;
      port = 5432;

      settings = {
        shared_buffers = "256MB";
        effective_cache_size = "1GB";
        maintenance_work_mem = "64MB";
        checkpoint_completion_target = 0.9;
        wal_buffers = "16MB";
        default_statistics_target = 100;
        random_page_cost = 1.1;
        effective_io_concurrency = 200;
      };

      identMap = ''
        mymap postgres postgres
        mymap myuser myuser
      '';

      authentication = ''
        local all postgres peer map=mymap
        local all myuser peer map=mymap
        host all all 127.0.0.1/32 md5
        host all all ::1/128 md5
      '';
    };

    # Redis
    redis.servers."" = {
      enable = true;
      port = 6379;
      settings = {
        maxmemory = "256MB";
        maxmemory-policy = "allkeys-lru";
        save = [ "900 1" "300 10" "60 10000" ];
      };
    };

    # MongoDB
    mongodb = {
      enable = true;
      package = pkgs.mongodb-4_4;
      enableAuth = true;
      initialRootPassword = "secretpassword";
    };
  };
}
```

#### Monitoring Services

```nix
{
  services = {
    # Prometheus monitoring
    prometheus = {
      enable = true;
      port = 9090;

      config = {
        global = {
          scrape_interval = "15s";
        };

        scrape_configs = [
          {
            job_name = "prometheus";
            static_configs = [{
              targets = [ "localhost:9090" ];
            }];
          }
          {
            job_name = "node";
            static_configs = [{
              targets = [ "localhost:9100" ];
            }];
          }
        ];
      };
    };

    # Node exporter
    prometheus.exporters.node = {
      enable = true;
      port = 9100;
      enabledCollectors = [
        "systemd"
        "processes"
      ];
    };

    # Grafana dashboards
    grafana = {
      enable = true;
      settings = {
        server = {
          http_addr = "127.0.0.1";
          http_port = 3000;
        };

        security = {
          admin_user = "admin";
          admin_password = "secure-password";
        };
      };

      provision = {
        enable = true;
        datasources.settings.datasources = [{
          name = "Prometheus";
          type = "prometheus";
          access = "proxy";
          url = "http://localhost:9090";
        }];
      };
    };
  };
}
```

### Service Security and Hardening

#### Security Options

```nix
{
  systemd.services.secure-service = {
    serviceConfig = {
      # User/Group isolation
      User = "secure-user";
      Group = "secure-group";
      DynamicUser = true;  # Create temporary user

      # Filesystem restrictions
      ProtectSystem = "strict";
      ProtectHome = true;
      ProtectKernelTunables = true;
      ProtectKernelModules = true;
      ProtectControlGroups = true;

      # Network restrictions
      RestrictAddressFamilies = [ "AF_INET" "AF_INET6" ];
      IPAddressAllow = [ "127.0.0.1" "10.0.0.0/8" ];

      # Capability restrictions
      CapabilityBoundingSet = [ "CAP_NET_BIND_SERVICE" ];
      AmbientCapabilities = [ "CAP_NET_BIND_SERVICE" ];

      # System call filtering
      SystemCallFilter = [ "@system-service" ];
      SystemCallErrorNumber = "EPERM";

      # Namespace isolation
      PrivateNetwork = false;
      PrivateTmp = true;
      PrivateDevices = true;

      # Resource limits
      MemoryMax = "1G";
      CPUQuota = "50%";
      TasksMax = 100;

      # Additional security
      NoNewPrivileges = true;
      LockPersonality = true;
      RestrictRealtime = true;
      RestrictSUIDSGID = true;
      RemoveIPC = true;
    };
  };
}
```

### ⚠️ Common Pitfalls

1. **Missing dependencies**: Services fail if required dependencies aren't properly specified
2. **Permission issues**: Services running as wrong user can't access required files
3. **Port conflicts**: Multiple services trying to bind to the same port
4. **Resource limits**: Services killed by systemd due to resource constraints
5. **Environment variables**: Missing or incorrect environment configuration

### ✅ Best Practices

1. **Use systemd security features**: Enable appropriate protection and restriction options
2. **Proper user isolation**: Run services as dedicated users, not root
3. **Resource limits**: Set appropriate memory and CPU limits
4. **Monitoring**: Include health checks and monitoring for important services
5. **Graceful shutdown**: Handle SIGTERM properly for clean shutdowns
6. **Configuration management**: Keep service configuration in version control

### 🏋️ Exercise 6: Custom Service with Monitoring

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 35 minutes

Create a custom web application service that includes:
1. A simple web server that serves a health endpoint
2. Proper systemd service configuration with security hardening
3. Nginx reverse proxy configuration
4. Prometheus monitoring endpoint
5. Automatic log rotation and management

<details>
<summary>💡 Click to see hints</summary>

- Use `pkgs.writeScriptBin` to create a simple web server script
- Configure service dependencies with `after` and `requires`
- Use security options like `ProtectSystem` and `PrivateTmp`
- Configure nginx with `services.nginx.virtualHosts`
- Use `services.prometheus` for monitoring configuration

</details>

<details>
<summary>✅ Click to see solution</summary>

```nix
{ config, pkgs, lib, ... }:
let
  # Simple web application
  webapp = pkgs.writeScriptBin "webapp" ''
    #!${pkgs.python3}/bin/python3

    import http.server
    import socketserver
    import json
    import os
    from urllib.parse import urlparse

    PORT = int(os.environ.get('PORT', 8080))

    class HealthHandler(http.server.BaseHTTPRequestHandler):
        def do_GET(self):
            parsed_path = urlparse(self.path)

            if parsed_path.path == '/health':
                self.send_response(200)
                self.send_header('Content-type', 'application/json')
                self.end_headers()
                response = {
                    'status': 'healthy',
                    'service': 'webapp',
                    'version': '1.0.0'
                }
                self.wfile.write(json.dumps(response).encode())

            elif parsed_path.path == '/metrics':
                self.send_response(200)
                self.send_header('Content-type', 'text/plain')
                self.end_headers()
                metrics = '''# HELP webapp_requests_total Total requests
    # TYPE webapp_requests_total counter
    webapp_requests_total 42

    # HELP webapp_uptime_seconds Service uptime
    # TYPE webapp_uptime_seconds gauge
    webapp_uptime_seconds 300
    '''
                self.wfile.write(metrics.encode())

            elif parsed_path.path == '/':
                self.send_response(200)
                self.send_header('Content-type', 'text/html')
                self.end_headers()
                html = '''<!DOCTYPE html>
    <html><head><title>Custom Web App</title></head>
    <body>
        <h1>Custom Web Application</h1>
        <p>Service is running!</p>
        <ul>
            <li><a href="/health">Health Check</a></li>
            <li><a href="/metrics">Metrics</a></li>
        </ul>
    </body></html>'''
                self.wfile.write(html.encode())

            else:
                self.send_response(404)
                self.end_headers()
                self.wfile.write(b'Not Found')

        def log_message(self, format, *args):
            # Log to systemd journal
            print(f"[{self.address_string()}] {format % args}")

    if __name__ == "__main__":
        with socketserver.TCPServer(("127.0.0.1", PORT), HealthHandler) as httpd:
            print(f"Serving at port {PORT}")
            httpd.serve_forever()
  '';
in
{
  # Custom web application service
  systemd.services.webapp = {
    description = "Custom Web Application";
    documentation = [ "https://example.com/webapp" ];

    # Dependencies
    wants = [ "network-online.target" ];
    after = [ "network-online.target" ];

    # Service configuration
    serviceConfig = {
      Type = "simple";
      User = "webapp";
      Group = "webapp";

      # Application command
      ExecStart = "${webapp}/bin/webapp";
      ExecReload = "${pkgs.coreutils}/bin/kill -HUP $MAINPID";

      # Restart policy
      Restart = "always";
      RestartSec = "10s";
      StartLimitIntervalSec = "60s";
      StartLimitBurst = 3;

      # Environment
      Environment = [
        "PORT=8080"
        "PYTHONUNBUFFERED=1"
      ];

      # Security hardening
      NoNewPrivileges = true;
      ProtectSystem = "strict";
      ProtectHome = true;
      ProtectKernelTunables = true;
      ProtectKernelModules = true;
      ProtectControlGroups = true;

      # Network restrictions
      RestrictAddressFamilies = [ "AF_INET" "AF_INET6" ];
      IPAddressAllow = [ "127.0.0.1" "::1" ];

      # Filesystem restrictions
      PrivateTmp = true;
      PrivateDevices = true;
      ReadWritePaths = [ "/var/lib/webapp" "/var/log/webapp" ];

      # Resource limits
      MemoryMax = "256M";
      CPUQuota = "50%";
      TasksMax = 50;

      # Working directory
      WorkingDirectory = "/var/lib/webapp";

      # Logging
      StandardOutput = "journal";
      StandardError = "journal";
      SyslogIdentifier = "webapp";
    };

    # Enable by default
    wantedBy = [ "multi-user.target" ];
  };

  # Create service user and directories
  users.users.webapp = {
    isSystemUser = true;
    group = "webapp";
    createHome = true;
    home = "/var/lib/webapp";
  };
  users.groups.webapp = {};

  # Create log directory
  systemd.tmpfiles.rules = [
    "d /var/log/webapp 0755 webapp webapp -"
    "d /var/lib/webapp 0755 webapp webapp -"
  ];

  # Nginx reverse proxy
  services.nginx = {
    enable = true;
    recommendedGzipSettings = true;
    recommendedOptimisation = true;
    recommendedProxySettings = true;
    recommendedTlsSettings = true;

    virtualHosts."webapp.local" = {
      locations = {
        "/" = {
          proxyPass = "http://127.0.0.1:8080";
          extraConfig = ''
            proxy_set_header Host $host;
            proxy_set_header X-Real-IP $remote_addr;
            proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header X-Forwarded-Proto $scheme;

            # Health check configuration
            proxy_connect_timeout 5s;
            proxy_send_timeout 10s;
            proxy_read_timeout 10s;
          '';
        };

        "/health" = {
          proxyPass = "http://127.0.0.1:8080/health";
          extraConfig = ''
            access_log off;
            proxy_connect_timeout 2s;
            proxy_send_timeout 2s;
            proxy_read_timeout 2s;
          '';
        };
      };

      extraConfig = ''
        # Security headers
        add_header X-Frame-Options DENY;
        add_header X-Content-Type-Options nosniff;
        add_header X-XSS-Protection "1; mode=block";

        # Rate limiting
        limit_req_zone $binary_remote_addr zone=webapp:10m rate=10r/s;
        limit_req zone=webapp burst=20 nodelay;
      '';
    };
  };

  # Prometheus monitoring
  services.prometheus = {
    enable = true;
    port = 9090;

    config = {
      global = {
        scrape_interval = "15s";
        evaluation_interval = "15s";
      };

      scrape_configs = [
        {
          job_name = "prometheus";
          static_configs = [{
            targets = [ "localhost:9090" ];
          }];
        }

        {
          job_name = "webapp";
          static_configs = [{
            targets = [ "localhost:8080" ];
          }];
          metrics_path = "/metrics";
          scrape_interval = "10s";
        }

        {
          job_name = "nginx";
          static_configs = [{
            targets = [ "localhost:9113" ];
          }];
        }
      ];

      rule_files = [];

      alerting = {
        alertmanagers = [{
          static_configs = [{
            targets = [];
          }];
        }];
      };
    };
  };

  # Nginx Prometheus exporter
  services.prometheus.exporters.nginx = {
    enable = true;
    port = 9113;
  };

  # Log rotation for webapp
  services.logrotate = {
    enable = true;
    settings = {
      webapp = {
        files = [ "/var/log/webapp/*.log" ];
        frequency = "daily";
        rotate = 7;
        compress = true;
        delaycompress = true;
        missingok = true;
        notifempty = true;
        create = "644 webapp webapp";
        postrotate = ''
          systemctl reload webapp || true
        '';
      };
    };
  };

  # Firewall configuration
  networking.firewall = {
    enable = true;
    allowedTCPPorts = [ 80 443 9090 ];  # HTTP, HTTPS, Prometheus
  };

  # System packages for monitoring
  environment.systemPackages = with pkgs; [
    curl
    jq
    htop
  ];
}
```

**Testing the Configuration:**

```bash
# Apply the configuration
sudo nixos-rebuild switch

# Check service status
systemctl status webapp
systemctl status nginx
systemctl status prometheus

# Test the web application
curl http://localhost:8080/health
curl http://localhost:8080/metrics
curl -H "Host: webapp.local" http://localhost/

# Check logs
journalctl -u webapp -f
journalctl -u nginx -f

# Monitor with Prometheus
# Open http://localhost:9090 in browser
```

**Explanation:**

This comprehensive service setup demonstrates:

- **Custom Application**: Python-based web server with health and metrics endpoints
- **Security Hardening**: Extensive systemd security options and resource limits
- **Service Management**: Proper dependencies, restart policies, and user isolation
- **Reverse Proxy**: Nginx configuration with security headers and rate limiting
- **Monitoring**: Prometheus scraping with custom metrics and nginx exporter
- **Log Management**: Automated log rotation with proper permissions
- **Resource Management**: Memory and CPU limits with proper restart policies

The configuration provides a production-ready service template that can be adapted for real applications.

</details>

[🔝 Back to top](#-nixos-documentation)

---

## 👤 User Management

**📊 Chapter 7 of 20**

**🎯 Learning Objectives:**
- Master user and group management in NixOS
- Learn authentication and authorization configuration
- Understand home directory management
- Configure user environments and permissions

**⏱️ Estimated Reading Time:** 18 minutes

**📋 Prerequisites:** Basic NixOS configuration knowledge

### Basic User Management

#### Creating Users

```nix
{ config, pkgs, ... }:
{
  users.users = {
    # Regular user
    alice = {
      isNormalUser = true;
      description = "Alice Smith";
      extraGroups = [ "wheel" "networkmanager" "audio" "video" ];
      packages = with pkgs; [
        firefox
        thunderbird
        kate
      ];
      shell = pkgs.bash;

      # SSH public keys
      openssh.authorizedKeys.keys = [
        "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAB... alice@laptop"
        "ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI... alice@desktop"
      ];
    };

    # System user for services
    webapp = {
      isSystemUser = true;
      group = "webapp";
      createHome = true;
      home = "/var/lib/webapp";
      shell = pkgs.bash;
    };

    # User with custom UID
    developer = {
      isNormalUser = true;
      uid = 1001;
      group = "developers";
      extraGroups = [ "wheel" "docker" ];
      createHome = true;
      home = "/home/developer";
    };
  };

  # Define groups
  users.groups = {
    webapp = {};
    developers = {
      gid = 2001;
    };
  };
}
```

#### User Properties and Options

```nix
{
  users.users.john = {
    # Basic properties
    isNormalUser = true;           # Regular user account
    isSystemUser = false;          # Not a system service user
    uid = 1000;                   # User ID (optional)
    group = "users";              # Primary group
    extraGroups = [               # Additional groups
      "wheel"                     # sudo access
      "networkmanager"            # network configuration
      "audio"                     # audio devices
      "video"                     # video devices
      "docker"                    # Docker daemon
      "libvirtd"                  # virtualization
    ];

    # Account details
    description = "John Doe";
    shell = pkgs.zsh;             # Default shell
    createHome = true;            # Create home directory
    home = "/home/john";          # Home directory path

    # Password and authentication
    hashedPassword = "$6$...";    # Hashed password
    initialPassword = "changeme"; # Plain text (insecure)
    passwordFile = "/etc/nixos/secrets/john-password"; # File containing password

    # SSH configuration
    openssh.authorizedKeys = {
      keys = [
        "ssh-rsa AAAAB3... john@work"
        "ssh-ed25519 AAAAC3... john@home"
      ];
      keyFiles = [ "/etc/nixos/keys/john.pub" ];
    };

    # User packages
    packages = with pkgs; [
      vim
      git
      firefox
    ];

    # Subgroups and permissions
    subUidRanges = [
      { startUid = 100000; count = 65536; }
    ];
    subGidRanges = [
      { startGid = 100000; count = 65536; }
    ];
  };
}
```

### Authentication Configuration

#### Password Policies

```nix
{
  # Password requirements
  security.pam.services = {
    # Configure password quality
    passwd.rules.password = {
      order = config.security.pam.services.passwd.rules.password.order;
      control = "requisite";
      module = "${pkgs.libpwquality}/lib/security/pam_pwquality.so";
      args = [
        "retry=3"
        "minlen=12"
        "difok=3"
        "dcredit=-1"    # At least 1 digit
        "lcredit=-1"    # At least 1 lowercase
        "ucredit=-1"    # At least 1 uppercase
        "ocredit=-1"    # At least 1 special char
      ];
    };

    # Login attempts
    login.rules.auth = {
      order = config.security.pam.services.login.rules.auth.order - 1;
      control = "required";
      module = "${pkgs.pam}/lib/security/pam_tally2.so";
      args = [
        "deny=3"        # Max 3 failed attempts
        "unlock_time=300" # 5 minutes lockout
      ];
    };
  };

  # Account policies
  security.pam.loginLimits = [
    { domain = "@users"; type = "soft"; item = "nproc"; value = "1000"; }
    { domain = "@users"; type = "hard"; item = "nproc"; value = "2000"; }
    { domain = "@wheel"; type = "soft"; item = "nofile"; value = "4096"; }
    { domain = "@wheel"; type = "hard"; item = "nofile"; value = "8192"; }
  ];
}
```

#### SSH Authentication

```nix
{
  services.openssh = {
    enable = true;
    settings = {
      # Authentication methods
      PasswordAuthentication = false;
      KbdInteractiveAuthentication = false;
      PubkeyAuthentication = true;

      # Root login
      PermitRootLogin = "no";

      # User restrictions
      AllowUsers = [ "alice" "bob" ];
      DenyUsers = [ "guest" ];
      AllowGroups = [ "wheel" "ssh-users" ];

      # Connection limits
      MaxAuthTries = 3;
      MaxSessions = 10;
      MaxStartups = "10:30:100";

      # Security options
      Protocol = 2;
      HostKeyAlgorithms = "rsa-sha2-512,rsa-sha2-256,ssh-ed25519";
      KexAlgorithms = "curve25519-sha256@libssh.org,diffie-hellman-group16-sha512";
      Ciphers = "chacha20-poly1305@openssh.com,aes256-gcm@openssh.com,aes256-ctr";
      MACs = "hmac-sha2-256-etm@openssh.com,hmac-sha2-512-etm@openssh.com";
    };

    # Host keys
    hostKeys = [
      {
        path = "/etc/ssh/ssh_host_ed25519_key";
        type = "ed25519";
        bits = 4096;
      }
      {
        path = "/etc/ssh/ssh_host_rsa_key";
        type = "rsa";
        bits = 4096;
      }
    ];
  };

  # Create SSH users group
  users.groups.ssh-users = {};
}
```

#### Multi-Factor Authentication

```nix
{
  # Google Authenticator (TOTP)
  security.pam.services.sshd.googleAuthenticator = {
    enable = true;
    issuer = "MyNixOS";
    rateLimit = 3;
    windowSize = 17;  # Allow some time drift
    secretFile = "/var/lib/google-authenticator";
  };

  # YubiKey authentication
  security.pam.yubico = {
    enable = true;
    debug = false;
    mode = "challenge";
    id = "12345";
    key = "base64key==";
  };

  # U2F/FIDO2 authentication
  security.pam.u2f = {
    enable = true;
    debug = false;
    cue = true;
    control = "sufficient";
    authFile = "/etc/u2f_mappings";
  };
}
```

### Sudo Configuration

#### Basic Sudo Setup

```nix
{
  # Enable sudo
  security.sudo = {
    enable = true;

    # Wheel group has sudo access
    wheelNeedsPassword = true;  # Require password for sudo

    # Custom sudo rules
    extraRules = [
      # Allow wheel group to run any command
      {
        users = [ "alice" ];
        commands = [
          {
            command = "ALL";
            options = [ "NOPASSWD" ];  # No password for alice
          }
        ];
      }

      # Allow specific commands without password
      {
        groups = [ "operators" ];
        commands = [
          {
            command = "/run/current-system/sw/bin/systemctl restart nginx";
            options = [ "NOPASSWD" ];
          }
          {
            command = "/run/current-system/sw/bin/systemctl status *";
            options = [ "NOPASSWD" ];
          }
        ];
      }

      # Time-limited sudo access
      {
        users = [ "temp-admin" ];
        commands = [
          {
            command = "ALL";
            options = [ "PASSWD" "TIMEOUT=300" ];  # 5 minute timeout
          }
        ];
      }
    ];

    # Sudo configuration options
    extraConfig = ''
      # Security options
      Defaults secure_path="/run/wrappers/bin:/nix/var/nix/profiles/default/bin:/run/current-system/sw/bin"
      Defaults env_reset
      Defaults env_keep="COLORS DISPLAY HOSTNAME HISTSIZE KDEDIR LS_COLORS"
      Defaults env_keep+="MAIL PS1 PS2 QTDIR USERNAME LANG LC_ADDRESS LC_CTYPE"
      Defaults env_keep+="LC_COLLATE LC_IDENTIFICATION LC_MEASUREMENT LC_MESSAGES"

      # Logging
      Defaults logfile=/var/log/sudo.log
      Defaults log_input, log_output

      # Password timeout
      Defaults passwd_timeout=1
      Defaults timestamp_timeout=15

      # Require password for dangerous commands
      Defaults!/usr/bin/su always_set_home
      Defaults!/usr/bin/sudo always_set_home
    '';
  };
}
```

### Home Directory Management

#### Automatic Home Directory Setup

```nix
{
  # Global home directory settings
  users.defaultUserShell = pkgs.zsh;

  # Skeleton files for new users
  environment.etc = {
    "skel/.bashrc".source = pkgs.writeText "bashrc" ''
      # Default .bashrc for new users
      export PATH=$HOME/.local/bin:$PATH
      export EDITOR=vim

      # Aliases
      alias ll='ls -la'
      alias la='ls -A'
      alias l='ls -CF'

      # History settings
      export HISTSIZE=1000
      export HISTFILESIZE=2000
      export HISTCONTROL=ignoreboth
    '';

    "skel/.vimrc".source = pkgs.writeText "vimrc" ''
      " Basic vim configuration for new users
      syntax on
      set number
      set tabstop=4
      set shiftwidth=4
      set expandtab
      set autoindent
      set hlsearch
      set incsearch
    '';

    "skel/.gitconfig".source = pkgs.writeText "gitconfig" ''
      [user]
          name = New User
          email = user@example.com
      [init]
          defaultBranch = main
      [pull]
          rebase = false
      [core]
          editor = vim
    '';
  };

  # User-specific home directory management
  users.users.alice = {
    isNormalUser = true;
    createHome = true;
    home = "/home/alice";

    # Copy skeleton files
    useDefaultShell = true;
  };
}
```

#### Home Manager Integration

```nix
{
  # System-wide Home Manager
  imports = [
    <home-manager/nixos>
  ];

  home-manager.users.alice = { pkgs, ... }: {
    home.stateVersion = "25.05";

    # User packages
    home.packages = with pkgs; [
      firefox
      thunderbird
      vscode
    ];

    # Program configurations
    programs = {
      git = {
        enable = true;
        userName = "Alice Smith";
        userEmail = "alice@example.com";
      };

      zsh = {
        enable = true;
        enableAutosuggestions = true;
        enableCompletion = true;
        syntaxHighlighting.enable = true;

        shellAliases = {
          ll = "ls -la";
          la = "ls -A";
          l = "ls -CF";
        };
      };

      vim = {
        enable = true;
        extraConfig = ''
          syntax on
          set number
          set tabstop=4
          set shiftwidth=4
          set expandtab
        '';
      };
    };

    # Services
    services = {
      gpg-agent = {
        enable = true;
        enableSshSupport = true;
      };
    };
  };
}
```

### User Environment Configuration

#### Shell Configuration

```nix
{
  # Global shell settings
  programs = {
    # Bash configuration
    bash = {
      enableCompletion = true;
      enableLsColors = true;
      shellAliases = {
        ll = "ls -la";
        la = "ls -A";
        l = "ls -CF";
        grep = "grep --color=auto";
        fgrep = "fgrep --color=auto";
        egrep = "egrep --color=auto";
      };

      interactiveShellInit = ''
        # History settings
        export HISTSIZE=10000
        export HISTFILESIZE=20000
        export HISTCONTROL=ignoreboth:erasedups

        # Editor
        export EDITOR=vim
        export VISUAL=vim

        # Colors
        export TERM=xterm-256color
      '';
    };

    # Zsh configuration
    zsh = {
      enable = true;
      enableCompletion = true;
      autosuggestions.enable = true;
      syntaxHighlighting.enable = true;

      shellAliases = {
        ll = "ls -la";
        la = "ls -A";
        l = "ls -CF";
      };

      ohMyZsh = {
        enable = true;
        theme = "robbyrussell";
        plugins = [
          "git"
          "sudo"
          "docker"
          "kubectl"
        ];
      };
    };

    # Fish shell
    fish = {
      enable = true;
      shellAliases = {
        ll = "ls -la";
        la = "ls -A";
        l = "ls -CF";
      };

      interactiveShellInit = ''
        set -g theme_color_scheme terminal-dark
        set -g fish_prompt_pwd_dir_length 1
        set -g theme_display_user yes
        set -g theme_hide_hostname no
      '';
    };
  };

  # Default shell for new users
  users.defaultUserShell = pkgs.zsh;
}
```

#### Environment Variables

```nix
{
  # Global environment variables
  environment.variables = {
    EDITOR = "vim";
    BROWSER = "firefox";
    TERM = "xterm-256color";
    PAGER = "less";
    LESS = "-R";
  };

  # Session variables (for desktop environments)
  environment.sessionVariables = {
    # Development
    CARGO_HOME = "$HOME/.cargo";
    RUSTUP_HOME = "$HOME/.rustup";
    GOPATH = "$HOME/go";

    # XDG directories
    XDG_CONFIG_HOME = "$HOME/.config";
    XDG_DATA_HOME = "$HOME/.local/share";
    XDG_CACHE_HOME = "$HOME/.cache";

    # Application settings
    NIXPKGS_ALLOW_UNFREE = "1";
    MOZ_ENABLE_WAYLAND = "1";
  };

  # User-specific environment
  users.users.developer = {
    isNormalUser = true;
    extraGroups = [ "wheel" "docker" ];

    # User environment variables
    environment.variables = {
      DEVELOPMENT_MODE = "1";
      DEBUG_LEVEL = "info";
    };
  };
}
```

### Access Control and Permissions

#### File Permissions and ACLs

```nix
{
  # Enable ACL support
  boot.supportedFilesystems = [ "ext4" ];

  # Mount options for ACL support
  fileSystems."/home" = {
    device = "/dev/disk/by-label/home";
    fsType = "ext4";
    options = [ "defaults" "acl" "user_xattr" ];
  };

  # System groups with specific purposes
  users.groups = {
    # Web developers
    webdev = {
      gid = 3001;
    };

    # Database administrators
    dba = {
      gid = 3002;
    };

    # Backup operators
    backup = {
      gid = 3003;
    };
  };

  # Set up shared directories with proper permissions
  systemd.tmpfiles.rules = [
    # Web development directory
    "d /var/www 0755 root webdev -"
    "Z /var/www 0775 root webdev -"

    # Database directory
    "d /var/lib/database 0750 postgres dba -"

    # Backup directory
    "d /backup 0750 root backup -"
    "d /backup/daily 0750 root backup -"
    "d /backup/weekly 0750 root backup -"
  ];
}
```

### ⚠️ Common Pitfalls

1. **Sudo configuration errors**: Incorrect sudo rules can lock you out of admin access
2. **SSH key formatting**: Malformed SSH keys prevent authentication
3. **Group permissions**: Users not added to required groups can't access resources
4. **Home directory permissions**: Incorrect permissions can prevent user login
5. **Password complexity**: Overly strict password policies can cause user frustration

### ✅ Best Practices

1. **Use SSH keys**: Disable password authentication and use key-based auth
2. **Principle of least privilege**: Give users only the permissions they need
3. **Regular audit**: Review user accounts and permissions regularly
4. **Backup authentication**: Always have multiple ways to gain admin access
5. **Document access**: Keep records of who has what level of access
6. **Test changes**: Use `nixos-rebuild test` before making permanent user changes

### 🏋️ Exercise 7: Complete User Management Setup

**Difficulty:** 🟡 Intermediate
**Estimated Time:** 30 minutes

Configure a comprehensive user management system with:
1. Three different user types: admin, developer, and regular user
2. SSH key-based authentication with fail2ban protection
3. Sudo configuration with different privilege levels
4. Home Manager setup for the developer user
5. Shared directories with proper group permissions
6. Password policies and account lockout protection

<details>
<summary>💡 Click to see hints</summary>

- Use `users.users` for user definitions and `users.groups` for groups
- Configure SSH in `services.openssh` with key-based auth only
- Set up sudo rules in `security.sudo.extraRules`
- Use Home Manager in `home-manager.users.<username>`
- Create shared directories with `systemd.tmpfiles.rules`
- Configure PAM for password policies in `security.pam`

</details>

<details>
<summary>✅ Click to see solution</summary>

```nix
{ config, pkgs, lib, ... }:
{
  # User Groups
  users.groups = {
    # Administrative group
    sysadmin = { gid = 2001; };

    # Development team
    developers = { gid = 2002; };

    # Project groups
    webdev = { gid = 3001; };
    database = { gid = 3002; };

    # Service accounts
    webapp = {};
    monitoring = {};
  };

  # User Accounts
  users.users = {
    # System administrator
    admin = {
      isNormalUser = true;
      description = "System Administrator";
      uid = 1000;
      group = "users";
      extraGroups = [
        "wheel" "networkmanager" "audio" "video" "sysadmin"
        "docker" "libvirtd"
      ];

      shell = pkgs.zsh;
      createHome = true;

      # SSH keys only - no password login
      openssh.authorizedKeys.keys = [
        "ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI... admin@workstation"
        "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAB... admin@laptop"
      ];

      packages = with pkgs; [
        vim
        tmux
        htop
        git
        curl
        wget
      ];
    };

    # Developer user
    developer = {
      isNormalUser = true;
      description = "Software Developer";
      uid = 1001;
      group = "users";
      extraGroups = [
        "developers" "webdev" "docker" "audio" "video"
        "networkmanager"
      ];

      shell = pkgs.zsh;
      createHome = true;

      openssh.authorizedKeys.keys = [
        "ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAI... developer@laptop"
      ];

      packages = with pkgs; [
        git
        vim
        nodejs
        python3
      ];
    };

    # Regular user
    user = {
      isNormalUser = true;
      description = "Regular User";
      uid = 1002;
      group = "users";
      extraGroups = [ "audio" "video" "networkmanager" ];

      shell = pkgs.bash;
      createHome = true;

      # Regular user can use password login
      initialPassword = "changeMe123!";

      packages = with pkgs; [
        firefox
        thunderbird
        libreoffice
      ];
    };

    # Service accounts
    webapp = {
      isSystemUser = true;
      group = "webapp";
      createHome = true;
      home = "/var/lib/webapp";
      shell = pkgs.bash;
    };

    monitoring = {
      isSystemUser = true;
      group = "monitoring";
      createHome = true;
      home = "/var/lib/monitoring";
      shell = pkgs.bash;
    };
  };

  # SSH Configuration
  services.openssh = {
    enable = true;
    settings = {
      # Security settings
      PasswordAuthentication = true;  # Allow for regular users
      KbdInteractiveAuthentication = false;
      PubkeyAuthentication = true;
      PermitRootLogin = "no";

      # User restrictions
      AllowUsers = [ "admin" "developer" "user" ];
      DenyUsers = [ "root" ];

      # Connection limits
      MaxAuthTries = 3;
      MaxSessions = 10;
      ClientAliveInterval = 600;
      ClientAliveCountMax = 0;

      # Protocol settings
      Protocol = 2;
      X11Forwarding = false;
      AllowTcpForwarding = "local";
    };

    # Custom SSH configuration
    extraConfig = ''
      # Admin users can use key authentication only
      Match User admin
          PasswordAuthentication no
          AuthorizedKeysFile /home/admin/.ssh/authorized_keys

      # Developer users can use key authentication only
      Match User developer
          PasswordAuthentication no
          AuthorizedKeysFile /home/developer/.ssh/authorized_keys

      # Regular users can use password authentication
      Match User user
          PasswordAuthentication yes
          MaxAuthTries 5
    '';
  };

  # Fail2Ban for SSH protection
  services.fail2ban = {
    enable = true;
    maxretry = 3;
    findtime = 600;
    bantime = 3600;

    jails = {
      sshd = {
        enabled = true;
        filter = "sshd";
        logpath = "/var/log/auth.log";
        maxretry = 3;
        findtime = 600;
        bantime = 3600;
        action = "iptables[name=SSH, port=ssh, protocol=tcp]";
      };
    };
  };

  # Sudo Configuration
  security.sudo = {
    enable = true;
    wheelNeedsPassword = true;

    extraRules = [
      # Full admin access without password
      {
        users = [ "admin" ];
        commands = [
          {
            command = "ALL";
            options = [ "NOPASSWD" ];
          }
        ];
      }

      # Developer access to specific services
      {
        groups = [ "developers" ];
        commands = [
          {
            command = "/run/current-system/sw/bin/systemctl restart nginx";
            options = [ "NOPASSWD" ];
          }
          {
            command = "/run/current-system/sw/bin/systemctl restart webapp";
            options = [ "NOPASSWD" ];
          }
          {
            command = "/run/current-system/sw/bin/systemctl status *";
            options = [ "NOPASSWD" ];
          }
          {
            command = "/run/current-system/sw/bin/journalctl";
            options = [ "NOPASSWD" ];
          }
          {
            command = "/run/current-system/sw/bin/docker";
            options = [ "NOPASSWD" ];
          }
        ];
      }

      # System administration group
      {
        groups = [ "sysadmin" ];
        commands = [
          {
            command = "ALL";
            options = [ "PASSWD" "TIMEOUT=300" ];
          }
        ];
      }
    ];

    extraConfig = ''
      # Security options
      Defaults secure_path="/run/wrappers/bin:/nix/var/nix/profiles/default/bin:/run/current-system/sw/bin"
      Defaults env_reset
      Defaults env_keep="COLORS DISPLAY HOSTNAME HISTSIZE LANG LC_*"

      # Logging
      Defaults logfile=/var/log/sudo.log
      Defaults log_input, log_output

      # Password timeout
      Defaults passwd_timeout=5
      Defaults timestamp_timeout=15

      # Require password for dangerous commands
      Defaults!/run/current-system/sw/bin/su always_set_home
      Defaults!/run/current-system/sw/bin/passwd always_set_home
    '';
  };

  # PAM Configuration for Password Policies
  security.pam.services = {
    # Password quality requirements
    passwd.rules.password = {
      order = 100;
      control = "requisite";
      module = "${pkgs.libpwquality}/lib/security/pam_pwquality.so";
      args = [
        "retry=3"
        "minlen=12"
        "difok=3"
        "dcredit=-1"    # At least 1 digit
        "lcredit=-1"    # At least 1 lowercase
        "ucredit=-1"    # At least 1 uppercase
        "ocredit=-1"    # At least 1 special char
        "maxrepeat=2"   # Max 2 consecutive identical chars
      ];
    };

    # Account lockout for failed logins
    login.rules.auth = {
      order = 50;
      control = "required";
      module = "${pkgs.pam}/lib/security/pam_faillock.so";
      args = [
        "preauth"
        "deny=5"
        "unlock_time=900"  # 15 minutes lockout
        "fail_interval=900"
      ];
    };
  };

  # Login limits
  security.pam.loginLimits = [
    { domain = "@users"; type = "soft"; item = "nproc"; value = "1024"; }
    { domain = "@users"; type = "hard"; item = "nproc"; value = "2048"; }
    { domain = "@developers"; type = "soft"; item = "nofile"; value = "4096"; }
    { domain = "@developers"; type = "hard"; item = "nofile"; value = "8192"; }
    { domain = "@sysadmin"; type = "soft"; item = "nofile"; value = "8192"; }
    { domain = "@sysadmin"; type = "hard"; item = "nofile"; value = "16384"; }
  ];

  # Home Manager for Developer User
  imports = [ <home-manager/nixos> ];

  home-manager.users.developer = { pkgs, ... }: {
    home.stateVersion = "25.05";

    # Developer packages
    home.packages = with pkgs; [
      # Editors and IDEs
      vscode
      vim
      neovim

      # Development tools
      git
      nodejs
      yarn
      python3
      rustc
      cargo
      go

      # Utilities
      ripgrep
      fd
      bat
      exa
      fzf
      tmux

      # Containers
      docker
      docker-compose
    ];

    # Program configurations
    programs = {
      git = {
        enable = true;
        userName = "Software Developer";
        userEmail = "developer@company.com";
        extraConfig = {
          init.defaultBranch = "main";
          pull.rebase = true;
          core.editor = "vim";
          push.default = "current";
        };
        aliases = {
          st = "status";
          co = "checkout";
          br = "branch";
          ci = "commit";
          unstage = "reset HEAD --";
          last = "log -1 HEAD";
        };
      };

      zsh = {
        enable = true;
        enableAutosuggestions = true;
        enableCompletion = true;
        syntaxHighlighting.enable = true;

        shellAliases = {
          ll = "exa -la";
          ls = "exa";
          cat = "bat";
          find = "fd";
          grep = "rg";

          # Development shortcuts
          dcu = "docker-compose up -d";
          dcd = "docker-compose down";
          dcl = "docker-compose logs -f";

          # Git shortcuts
          gs = "git status";
          ga = "git add";
          gc = "git commit";
          gp = "git push";
          gl = "git log --oneline -10";
        };

        oh-my-zsh = {
          enable = true;
          theme = "robbyrussell";
          plugins = [
            "git"
            "docker"
            "docker-compose"
            "nodejs"
            "python"
            "rust"
            "golang"
          ];
        };
      };

      tmux = {
        enable = true;
        shortcut = "a";
        terminal = "screen-256color";
        keyMode = "vi";

        extraConfig = ''
          # Mouse support
          set -g mouse on

          # Status bar
          set -g status-bg colour235
          set -g status-fg colour136
          set -g status-left-length 20
          set -g status-right-length 50
          set -g status-left '[#S] '
          set -g status-right '#H %Y-%m-%d %H:%M'

          # Window navigation
          bind -n M-Left select-pane -L
          bind -n M-Right select-pane -R
          bind -n M-Up select-pane -U
          bind -n M-Down select-pane -D

          # Split windows
          bind | split-window -h
          bind - split-window -v
        '';
      };

      vim = {
        enable = true;
        extraConfig = ''
          syntax on
          set number
          set relativenumber
          set tabstop=4
          set shiftwidth=4
          set expandtab
          set autoindent
          set smartindent
          set hlsearch
          set incsearch
          set ignorecase
          set smartcase
          set wildmenu
          set wildmode=list:longest
          set backspace=indent,eol,start

          " Color scheme
          colorscheme desert

          " Key mappings
          let mapleader = ","
          nnoremap <leader>w :w<CR>
          nnoremap <leader>q :q<CR>
          nnoremap <leader>h :nohl<CR>
        '';
      };
    };

    # Services
    services = {
      gpg-agent = {
        enable = true;
        defaultCacheTtl = 1800;
        enableSshSupport = true;
      };
    };
  };

  # Shared Directories with Proper Permissions
  systemd.tmpfiles.rules = [
    # Web development directory
    "d /var/www 0755 root webdev -"
    "d /var/www/html 0775 root webdev -"
    "d /var/www/logs 0775 root webdev -"

    # Development projects directory
    "d /srv/projects 0775 root developers -"
    "d /srv/projects/web 0775 root webdev -"
    "d /srv/projects/api 0775 root developers -"

    # Database directory
    "d /var/lib/database 0750 postgres database -"
    "d /var/lib/database/backups 0750 postgres database -"

    # Shared tools directory
    "d /opt/shared 0755 root developers -"
    "d /opt/shared/bin 0755 root developers -"
    "d /opt/shared/scripts 0755 root developers -"

    # Log directories
    "d /var/log/applications 0755 root developers -"
    "d /var/log/webapp 0755 webapp webapp -"
    "d /var/log/monitoring 0755 monitoring monitoring -"
  ];

  # Shell Configuration
  programs = {
    zsh = {
      enable = true;
      enableCompletion = true;
      autosuggestions.enable = true;
      syntaxHighlighting.enable = true;
    };

    bash = {
      enableCompletion = true;
      enableLsColors = true;
    };
  };

  # Global Environment Variables
  environment.variables = {
    EDITOR = "vim";
    BROWSER = "firefox";
    PAGER = "less";
    LESS = "-R";
  };

  # Session variables for development
  environment.sessionVariables = {
    # Development paths
    GOPATH = "$HOME/go";
    CARGO_HOME = "$HOME/.cargo";
    RUSTUP_HOME = "$HOME/.rustup";

    # Project directories
    PROJECT_HOME = "/srv/projects";
    WEB_ROOT = "/var/www";
  };

  system.stateVersion = "25.05";
}
```

**Testing the Configuration:**

```bash
# Apply configuration
sudo nixos-rebuild switch

# Test user accounts
su - admin
su - developer
su - user

# Test SSH access (from another machine)
ssh admin@nixos-machine
ssh developer@nixos-machine

# Test sudo access
sudo systemctl status nginx  # Should work for admin
sudo -u developer systemctl restart webapp  # Should work for developer

# Check shared directories
ls -la /var/www
ls -la /srv/projects

# View logs
sudo journalctl -u fail2ban
sudo tail /var/log/sudo.log

# Test Home Manager
home-manager switch  # As developer user
```

**Explanation:**

This comprehensive user management setup provides:

- **Role-Based Access**: Three distinct user types with appropriate permissions
- **Security**: SSH key authentication, fail2ban protection, and strong password policies
- **Development Environment**: Home Manager configuration with development tools and aliases
- **Shared Resources**: Properly permissioned directories for collaboration
- **Monitoring**: Logging and auditing of administrative actions
- **Flexibility**: Easy to extend with additional users and permissions

The configuration balances security with usability, providing a foundation for a multi-user development environment.

</details>

[🔝 Back to top](#-nixos-documentation)

---

## 🌐 Network Configuration

**📊 Chapter 8 of 20**

**🎯 Learning Objectives:**
- Master network configuration in NixOS
- Learn wireless and wired network setup
- Configure firewalls and network security
- Set up VPN and advanced networking

**⏱️ Estimated Reading Time:** 25 minutes

**📋 Prerequisites:** Basic system configuration knowledge

### Basic Network Configuration

#### NetworkManager (Desktop Systems)

```nix
{ config, pkgs, ... }:
{
  # Enable NetworkManager for easy network management
  networking = {
    networkmanager = {
      enable = true;
      wifi = {
        powersave = false;  # Disable WiFi power saving
        scanRandMacAddress = true;  # Privacy enhancement
      };

      # DNS configuration
      dns = "systemd-resolved";

      # Additional NetworkManager settings
      extraConfig = ''
        [main]
        rc-manager=resolvconf

        [connectivity]
        uri=http://nmcheck.gnome.org/check_network_connectivity.txt
        interval=300
      '';
    };

    # Hostname
    hostName = "nixos-desktop";
    hostId = "12345678";  # Required for ZFS

    # Domain configuration
    domain = "local";
    search = [ "local" "example.com" ];

    # Enable IPv6
    enableIPv6 = true;
  };

  # DNS resolution
  services.resolved = {
    enable = true;
    dnssec = "true";
    domains = [ "~." ];
    fallbackDns = [ "1.1.1.1" "8.8.8.8" ];
    extraConfig = ''
      DNS=1.1.1.1#cloudflare-dns.com 8.8.8.8#dns.google
      DNSOverTLS=yes
      MulticastDNS=yes
      LLMNR=yes
      Cache=yes
      CacheFromLocalhost=no
    '';
  };
}
```

#### Static IP Configuration

```nix
{
  networking = {
    # Disable NetworkManager for static configuration
    networkmanager.enable = false;

    # Use systemd-networkd
    useNetworkd = true;
    useDHCP = false;

    # Interface configuration
    interfaces = {
      enp0s3 = {
        ipv4.addresses = [{
          address = "192.168.1.100";
          prefixLength = 24;
        }];
        ipv6.addresses = [{
          address = "2001:db8::1";
          prefixLength = 64;
        }];
      };

      wlp2s0 = {
        useDHCP = true;  # WiFi uses DHCP
      };
    };

    # Default gateway
    defaultGateway = {
      address = "192.168.1.1";
      interface = "enp0s3";
    };

    # IPv6 default gateway
    defaultGateway6 = {
      address = "2001:db8::1";
      interface = "enp0s3";
    };

    # DNS servers
    nameservers = [ "1.1.1.1" "8.8.8.8" ];
  };

  # systemd-networkd configuration
  systemd.network = {
    enable = true;

    networks."10-lan" = {
      matchConfig.Name = "enp0s3";
      networkConfig = {
        DHCP = "no";
        IPv6AcceptRA = false;
      };
      address = [
        "192.168.1.100/24"
        "2001:db8::1/64"
      ];
      routes = [
        { routeConfig.Gateway = "192.168.1.1"; }
      ];
      dns = [ "1.1.1.1" "8.8.8.8" ];
      domains = [ "local" ];
    };
  };
}
```

### Wireless Configuration

#### WPA Supplicant

```nix
{
  networking.wireless = {
    enable = true;
    userControlled.enable = true;  # Allow users to control WiFi

    # Network configurations
    networks = {
      "MyHomeWiFi" = {
        psk = "supersecretpassword";
        priority = 1;
      };

      "OfficeWiFi" = {
        psk = "officepassword";
        priority = 2;
      };

      # Enterprise WPA2 network
      "EnterpriseWiFi" = {
        auth = ''
          key_mgmt=WPA-EAP
          eap=PEAP
          identity="username"
          password="password"
          phase2="auth=MSCHAPV2"
        '';
      };

      # Open network
      "PublicWiFi" = {};
    };

    # Additional wpa_supplicant configuration
    extraConfig = ''
      ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=wheel
      update_config=1
      country=US

      # Security settings
      pmf=1
      scan_ssid=1

      # Power management
      p2p_disabled=1
    '';
  };

  # WiFi regulatory domain
  hardware.wirelessRegulatoryDatabase = true;
}
```

### Firewall Configuration

#### Basic Firewall Setup

```nix
{
  networking.firewall = {
    enable = true;

    # Open TCP ports
    allowedTCPPorts = [ 22 80 443 ];

    # Open UDP ports
    allowedUDPPorts = [ 53 67 68 ];

    # Open port ranges
    allowedTCPPortRanges = [
      { from = 1714; to = 1764; }  # KDE Connect
    ];
    allowedUDPPortRanges = [
      { from = 1714; to = 1764; }  # KDE Connect
    ];

    # Allow specific interfaces
    trustedInterfaces = [ "lo" "docker0" ];

    # Custom rules
    extraCommands = ''
      # Allow SSH from specific networks
      iptables -A nixos-fw -p tcp --dport 22 -s 192.168.1.0/24 -j ACCEPT
      iptables -A nixos-fw -p tcp --dport 22 -s 10.0.0.0/8 -j ACCEPT

      # Rate limit SSH connections
      iptables -A nixos-fw -p tcp --dport 22 -m state --state NEW -m recent --set
      iptables -A nixos-fw -p tcp --dport 22 -m state --state NEW -m recent --update --seconds 60 --hitcount 4 -j DROP

      # Block specific IP ranges
      iptables -A nixos-fw -s 192.168.0.0/16 -j DROP
      iptables -A nixos-fw -s 172.16.0.0/12 -j DROP
    '';

    # Cleanup rules
    extraStopCommands = ''
      iptables -D nixos-fw -p tcp --dport 22 -s 192.168.1.0/24 -j ACCEPT 2>/dev/null || true
    '';
  };
}
```

#### Advanced Firewall with nftables

```nix
{
  networking = {
    # Disable iptables-based firewall
    firewall.enable = false;

    # Enable nftables
    nftables = {
      enable = true;

      ruleset = ''
        table inet filter {
          chain input {
            type filter hook input priority 0; policy drop;

            # Allow loopback
            iif lo accept

            # Allow established connections
            ct state established,related accept

            # Allow ICMP
            ip protocol icmp accept
            ip6 nexthdr ipv6-icmp accept

            # Allow SSH from trusted networks
            ip saddr { 192.168.1.0/24, 10.0.0.0/8 } tcp dport 22 accept

            # Allow web traffic
            tcp dport { 80, 443 } accept

            # Rate limit SSH
            tcp dport 22 limit rate 4/minute accept

            # Log dropped packets
            log prefix "nftables dropped: " drop
          }

          chain forward {
            type filter hook forward priority 0; policy drop;

            # Allow forwarding for Docker
            iifname "docker0" accept
            oifname "docker0" ct state related,established accept
          }

          chain output {
            type filter hook output priority 0; policy accept;
          }
        }

        table inet nat {
          chain prerouting {
            type nat hook prerouting priority -100;

            # Port forwarding example
            tcp dport 8080 dnat to 192.168.1.10:80
          }

          chain postrouting {
            type nat hook postrouting priority 100;

            # Masquerade for Docker
            oifname "eth0" masquerade
          }
        }
      '';
    };
  };
}
```

### VPN Configuration

#### WireGuard VPN

```nix
{
  # Enable WireGuard
  networking.wireguard.interfaces = {
    wg0 = {
      # Interface configuration
      ips = [ "10.100.0.2/24" ];
      listenPort = 51820;

      # Private key (keep secure!)
      privateKeyFile = "/etc/nixos/secrets/wireguard-private";

      peers = [
        {
          # VPN server
          publicKey = "server-public-key-here";
          allowedIPs = [ "10.100.0.0/24" "192.168.1.0/24" ];
          endpoint = "vpn.example.com:51820";
          persistentKeepalive = 25;
        }

        {
          # Another peer
          publicKey = "peer-public-key-here";
          allowedIPs = [ "10.100.0.3/32" ];
          endpoint = "peer.example.com:51820";
        }
      ];

      # Post-up and pre-down scripts
      postSetup = ''
        ${pkgs.iptables}/bin/iptables -A FORWARD -i wg0 -j ACCEPT
        ${pkgs.iptables}/bin/iptables -t nat -A POSTROUTING -s 10.100.0.0/24 -o eth0 -j MASQUERADE
      '';

      postShutdown = ''
        ${pkgs.iptables}/bin/iptables -D FORWARD -i wg0 -j ACCEPT
        ${pkgs.iptables}/bin/iptables -t nat -D POSTROUTING -s 10.100.0.0/24 -o eth0 -j MASQUERADE
      '';
    };
  };

  # Allow WireGuard traffic through firewall
  networking.firewall = {
    allowedUDPPorts = [ 51820 ];
    trustedInterfaces = [ "wg0" ];
  };

  # Enable IP forwarding for VPN
  boot.kernel.sysctl = {
    "net.ipv4.ip_forward" = 1;
    "net.ipv6.conf.all.forwarding" = 1;
  };
}
```

#### OpenVPN Client

```nix
{
  services.openvpn.servers = {
    homeVPN = {
      config = ''
        client
        dev tun
        proto udp
        remote vpn.example.com 1194
        resolv-retry infinite
        nobind
        persist-key
        persist-tun
        ca /etc/openvpn/ca.crt
        cert /etc/openvpn/client.crt
        key /etc/openvpn/client.key
        tls-auth /etc/openvpn/ta.key 1
        cipher AES-256-CBC
        verb 3
        auth SHA256
        compress lz4-v2
        push "compress lz4-v2"
      '';
      autoStart = false;  # Start manually
    };

    officeVPN = {
      config = ''
        client
        dev tun
        proto tcp
        remote office-vpn.company.com 443
        resolv-retry infinite
        nobind
        persist-key
        persist-tun
        ca /etc/openvpn/office-ca.crt
        auth-user-pass /etc/openvpn/office-credentials
        tls-auth /etc/openvpn/office-ta.key 1
        cipher AES-256-GCM
        verb 3
        auth SHA256
        compress lz4-v2
      '';
      autoStart = true;   # Start automatically
    };
  };

  # Firewall rules for OpenVPN
  networking.firewall = {
    trustedInterfaces = [ "tun0" "tun1" ];
  };
}
```

### Network Services

#### DHCP Server

```nix
{
  services.dhcpd4 = {
    enable = true;
    interfaces = [ "eth0" ];

    configFile = pkgs.writeText "dhcpd.conf" ''
      option domain-name "local";
      option domain-name-servers 8.8.8.8, 1.1.1.1;
      option routers 192.168.1.1;
      option broadcast-address 192.168.1.255;
      option subnet-mask 255.255.255.0;

      subnet 192.168.1.0 netmask 255.255.255.0 {
        range 192.168.1.10 192.168.1.100;

        # Static leases
        host server {
          hardware ethernet 00:11:22:33:44:55;
          fixed-address 192.168.1.10;
        }

        host printer {
          hardware ethernet AA:BB:CC:DD:EE:FF;
          fixed-address 192.168.1.20;
        }
      }

      default-lease-time 600;
      max-lease-time 7200;

      log-facility local7;
    '';
  };
}
```

#### DNS Server (Unbound)

```nix
{
  services.unbound = {
    enable = true;

    settings = {
      server = {
        interface = [ "127.0.0.1" "192.168.1.1" ];
        port = 53;

        # Access control
        access-control = [
          "127.0.0.0/8 allow"
          "192.168.1.0/24 allow"
          "10.0.0.0/8 allow"
          "0.0.0.0/0 refuse"
        ];

        # Privacy and security
        hide-identity = true;
        hide-version = true;
        harden-glue = true;
        harden-dnssec-stripped = true;
        use-caps-for-id = true;

        # Performance
        num-threads = 2;
        msg-cache-slabs = 4;
        rrset-cache-slabs = 4;
        infra-cache-slabs = 4;
        key-cache-slabs = 4;

        # Cache settings
        cache-min-ttl = 300;
        cache-max-ttl = 86400;
        prefetch = true;

        # Local zone
        local-zone = [ "local. static" ];
        local-data = [
          "router.local. IN A 192.168.1.1"
          "server.local. IN A 192.168.1.10"
          "nas.local. IN A 192.168.1.20"
        ];
      };

      # Upstream DNS
      forward-zone = [
        {
          name = ".";
          forward-addr = [
            "1.1.1.1@853#cloudflare-dns.com"
            "8.8.8.8@853#dns.google"
          ];
          forward-tls-upstream = true;
        }
      ];
    };
  };

  # Open DNS port
  networking.firewall.allowedTCPPorts = [ 53 ];
  networking.firewall.allowedUDPPorts = [ 53 ];
}
```

### Network Monitoring

#### Network Monitoring Tools

```nix
{
  environment.systemPackages = with pkgs; [
    # Network analysis
    wireshark
    tcpdump
    nmap
    netcat-gnu

    # Bandwidth monitoring
    iftop
    nethogs
    bandwhich

    # Network testing
    speedtest-cli
    mtr
    traceroute
    dig

    # WiFi tools
    wavemon
    iw
    wireless-tools
  ];

  # Wireshark for non-root users
  programs.wireshark = {
    enable = true;
    package = pkgs.wireshark;
  };

  # Network monitoring service
  services.prometheus.exporters.node = {
    enable = true;
    port = 9100;
    enabledCollectors = [
      "conntrack"
      "netdev"
      "netstat"
      "sockstat"
    ];
  };
}
```

### ⚠️ Common Pitfalls

1. **NetworkManager conflicts**: Don't enable both NetworkManager and systemd-networkd
2. **Firewall rules**: Test firewall changes carefully to avoid locking yourself out
3. **WiFi drivers**: Some WiFi cards need proprietary firmware
4. **DNS conflicts**: Multiple DNS services can cause resolution issues
5. **VPN routing**: Incorrect routing can break network connectivity

### ✅ Best Practices

1. **Use NetworkManager for desktops**: It provides the best user experience
2. **Static IPs for servers**: Use systemd-networkd for server configurations
3. **Firewall security**: Follow the principle of least privilege
4. **Monitor network performance**: Use appropriate monitoring tools
5. **Document network setup**: Keep records of IP assignments and configurations
6. **Test configurations**: Always test network changes before applying permanently

### 🏋️ Exercise 8: Advanced Network Setup

**Difficulty:** 🔴 Advanced
**Estimated Time:** 45 minutes

Configure a comprehensive network setup including:
1. Static IP configuration with systemd-networkd
2. WireGuard VPN server and client
3. Local DNS server with custom domains
4. Advanced firewall rules with nftables
5. Network monitoring and logging

<details>
<summary>💡 Click to see hints</summary>

- Use `systemd.network` for static IP configuration
- Configure WireGuard in `networking.wireguard.interfaces`
- Set up Unbound DNS server with local zones
- Use `networking.nftables` for advanced firewall rules
- Enable network monitoring with Prometheus exporters

</details>

<details>
<summary>✅ Click to see solution</summary>

```nix
{ config, pkgs, ... }:
{
  # Network Configuration
  networking = {
    hostName = "nixos-gateway";
    hostId = "abcd1234";
    domain = "homelab.local";

    # Disable NetworkManager, use systemd-networkd
    networkmanager.enable = false;
    useNetworkd = true;
    useDHCP = false;

    # Enable IPv6
    enableIPv6 = true;

    # Interface configuration
    interfaces = {
      # LAN interface - static IP
      enp1s0 = {
        ipv4.addresses = [{
          address = "192.168.1.1";
          prefixLength = 24;
        }];
        ipv6.addresses = [{
          address = "fd00::1";
          prefixLength = 64;
        }];
      };

      # WAN interface - DHCP
      enp2s0 = {
        useDHCP = true;
      };
    };

    # Enable IP forwarding
    kernel.sysctl = {
      "net.ipv4.ip_forward" = 1;
      "net.ipv6.conf.all.forwarding" = 1;
      "net.ipv4.conf.all.send_redirects" = 0;
      "net.ipv4.conf.default.send_redirects" = 0;
    };
  };

  # systemd-networkd configuration
  systemd.network = {
    enable = true;

    # LAN network
    networks."10-lan" = {
      matchConfig.Name = "enp1s0";
      networkConfig = {
        DHCP = "no";
        IPForward = true;
        IPMasquerade = true;
        IPv6SendRA = true;
        DHCPServer = true;
      };

      address = [
        "192.168.1.1/24"
        "fd00::1/64"
      ];

      dhcpServerConfig = {
        DNS = "192.168.1.1";
        NTP = "192.168.1.1";
        EmitDNS = true;
        EmitNTP = true;
      };

      dhcpServerStaticLeases = [
        {
          dhcpServerStaticLeaseConfig = {
            MACAddress = "aa:bb:cc:dd:ee:ff";
            Address = "192.168.1.10";
          };
        }
      ];

      ipv6SendRAConfig = {
        Managed = false;
        OtherInformation = false;
        RouterLifetimeSec = 300;
        DNS = "fd00::1";
      };
    };

    # WAN network
    networks."20-wan" = {
      matchConfig.Name = "enp2s0";
      networkConfig = {
        DHCP = "ipv4";
        IPForward = true;
      };
      dhcpV4Config = {
        UseDNS = false;  # Use our own DNS
        UseNTP = true;
      };
    };
  };

  # WireGuard VPN Configuration
  networking.wireguard.interfaces = {
    wg0 = {
      # Server configuration
      ips = [ "10.100.0.1/24" ];
      listenPort = 51820;

      # Generate with: wg genkey
      privateKeyFile = "/etc/nixos/secrets/wg-server-private";

      peers = [
        # Client 1
        {
          publicKey = "CLIENT1_PUBLIC_KEY_HERE";
          allowedIPs = [ "10.100.0.2/32" ];
        }

        # Client 2
        {
          publicKey = "CLIENT2_PUBLIC_KEY_HERE";
          allowedIPs = [ "10.100.0.3/32" ];
        }

        # Mobile client
        {
          publicKey = "MOBILE_PUBLIC_KEY_HERE";
          allowedIPs = [ "10.100.0.10/32" ];
        }
      ];

      # Post-setup commands
      postSetup = ''
        # Allow VPN traffic forwarding
        ${pkgs.iptables}/bin/iptables -A FORWARD -i wg0 -j ACCEPT
        ${pkgs.iptables}/bin/iptables -A FORWARD -o wg0 -j ACCEPT
        ${pkgs.iptables}/bin/iptables -t nat -A POSTROUTING -s 10.100.0.0/24 -o enp2s0 -j MASQUERADE
      '';

      postShutdown = ''
        ${pkgs.iptables}/bin/iptables -D FORWARD -i wg0 -j ACCEPT
        ${pkgs.iptables}/bin/iptables -D FORWARD -o wg0 -j ACCEPT
        ${pkgs.iptables}/bin/iptables -t nat -D POSTROUTING -s 10.100.0.0/24 -o enp2s0 -j MASQUERADE
      '';
    };

    # Client configuration for connecting to external VPN
    wg1 = {
      ips = [ "10.200.0.15/24" ];
      privateKeyFile = "/etc/nixos/secrets/wg-client-private";

      peers = [{
        publicKey = "EXTERNAL_VPN_PUBLIC_KEY";
        allowedIPs = [ "0.0.0.0/0" "::/0" ];
        endpoint = "external-vpn.example.com:51820";
        persistentKeepalive = 25;
      }];
    };
  };

  # DNS Server Configuration
  services.unbound = {
    enable = true;

    settings = {
      server = {
        interface = [
          "127.0.0.1"
          "192.168.1.1"
          "fd00::1"
          "10.100.0.1"
        ];
        port = 53;

        # Access control
        access-control = [
          "127.0.0.0/8 allow"
          "192.168.1.0/24 allow"
          "10.100.0.0/24 allow"
          "fd00::/64 allow"
          "::1/128 allow"
          "0.0.0.0/0 refuse"
        ];

        # Security settings
        hide-identity = true;
        hide-version = true;
        harden-glue = true;
        harden-dnssec-stripped = true;
        harden-below-nxdomain = true;
        harden-referral-path = true;
        use-caps-for-id = true;
        qname-minimisation = true;

        # Performance settings
        num-threads = 4;
        msg-cache-slabs = 8;
        rrset-cache-slabs = 8;
        infra-cache-slabs = 8;
        key-cache-slabs = 8;
        cache-min-ttl = 300;
        cache-max-ttl = 86400;
        prefetch = true;
        prefetch-key = true;

        # Local domain
        local-zone = [
          "homelab.local. static"
          "1.168.192.in-addr.arpa. static"
        ];

        local-data = [
          # Gateway/Router
          "gateway.homelab.local. IN A 192.168.1.1"
          "router.homelab.local. IN A 192.168.1.1"

          # Servers
          "nas.homelab.local. IN A 192.168.1.10"
          "media.homelab.local. IN A 192.168.1.11"
          "monitoring.homelab.local. IN A 192.168.1.12"

          # Services
          "nextcloud.homelab.local. IN A 192.168.1.10"
          "jellyfin.homelab.local. IN A 192.168.1.11"
          "grafana.homelab.local. IN A 192.168.1.12"

          # Reverse DNS
          "1.1.168.192.in-addr.arpa. IN PTR gateway.homelab.local."
          "10.1.168.192.in-addr.arpa. IN PTR nas.homelab.local."
          "11.1.168.192.in-addr.arpa. IN PTR media.homelab.local."
          "12.1.168.192.in-addr.arpa. IN PTR monitoring.homelab.local."
        ];

        # Block ads and malware
        local-zone = [
          "doubleclick.net refuse"
          "googleadservices.com refuse"
          "googlesyndication.com refuse"
          "googletagmanager.com refuse"
        ];

        # Logging
        verbosity = 1;
        log-queries = false;
        log-replies = false;
        log-local-actions = true;
        log-servfail = true;
      };

      # Forward zones
      forward-zone = [
        {
          name = ".";
          forward-addr = [
            "1.1.1.1@853#cloudflare-dns.com"
            "1.0.0.1@853#cloudflare-dns.com"
            "8.8.8.8@853#dns.google"
            "8.8.4.4@853#dns.google"
          ];
          forward-tls-upstream = true;
        }
      ];
    };
  };

  # Advanced Firewall with nftables
  networking = {
    firewall.enable = false;  # Disable iptables firewall

    nftables = {
      enable = true;

      ruleset = ''
        # Clear all prior state
        flush ruleset

        table inet filter {
          # Rate limiting for SSH
          set ssh_ratelimit {
            type ipv4_addr
            size 65535
            flags dynamic,timeout
            timeout 1m
          }

          # Blocked IPs
          set blocklist {
            type ipv4_addr
            size 65535
            flags dynamic,timeout
            timeout 1h
          }

          chain input {
            type filter hook input priority filter; policy drop;

            # Allow loopback
            iifname lo accept

            # Allow established connections
            ct state { established, related } accept

            # Drop invalid packets
            ct state invalid drop

            # Allow ICMP
            ip protocol icmp icmp type { destination-unreachable, router-advertisement, time-exceeded, parameter-problem } accept
            ip protocol icmp icmp type echo-request limit rate 5/second accept
            ip6 nexthdr ipv6-icmp accept

            # Block known bad IPs
            ip saddr @blocklist drop

            # SSH with rate limiting
            tcp dport 22 ip saddr @ssh_ratelimit drop
            tcp dport 22 ct state new add @ssh_ratelimit { ip saddr limit rate 3/minute } accept
            tcp dport 22 accept

            # DNS (from LAN and VPN only)
            iifname { "enp1s0", "wg0" } tcp dport 53 accept
            iifname { "enp1s0", "wg0" } udp dport 53 accept

            # DHCP server
            iifname "enp1s0" udp dport 67 accept

            # WireGuard
            udp dport 51820 accept

            # Allow from LAN
            iifname "enp1s0" ip saddr 192.168.1.0/24 accept

            # Allow from VPN
            iifname "wg0" ip saddr 10.100.0.0/24 accept

            # Web services (if hosting)
            # tcp dport { 80, 443 } accept

            # Log dropped packets (sample)
            limit rate 5/minute log prefix "nftables dropped: " level info

            # Final drop
            drop
          }

          chain forward {
            type filter hook forward priority filter; policy drop;

            # Allow established connections
            ct state { established, related } accept

            # Drop invalid packets
            ct state invalid drop

            # Allow LAN to WAN
            iifname "enp1s0" oifname "enp2s0" accept

            # Allow VPN to LAN and WAN
            iifname "wg0" oifname { "enp1s0", "enp2s0" } accept

            # Allow LAN to VPN
            iifname "enp1s0" oifname "wg0" accept

            # Log forwarded traffic (sample)
            limit rate 10/minute log prefix "nftables forward: " level debug

            drop
          }

          chain output {
            type filter hook output priority filter; policy accept;
          }
        }

        table inet nat {
          chain prerouting {
            type nat hook prerouting priority dstnat;

            # Port forwarding examples
            # iifname "enp2s0" tcp dport 8080 dnat to 192.168.1.10:80
            # iifname "enp2s0" tcp dport 2222 dnat to 192.168.1.10:22
          }

          chain postrouting {
            type nat hook postrouting priority srcnat;

            # Masquerade LAN traffic
            oifname "enp2s0" ip saddr 192.168.1.0/24 masquerade

            # Masquerade VPN traffic
            oifname "enp2s0" ip saddr 10.100.0.0/24 masquerade
          }
        }
      '';
    };
  };

  # Network Time Protocol
  services.ntp = {
    enable = true;
    servers = [
      "0.pool.ntp.org"
      "1.pool.ntp.org"
      "2.pool.ntp.org"
      "3.pool.ntp.org"
    ];
  };

  # Network Monitoring
  services.prometheus = {
    enable = true;
    port = 9090;
    listenAddress = "192.168.1.1";

    config = {
      global = {
        scrape_interval = "15s";
        evaluation_interval = "15s";
      };

      scrape_configs = [
        {
          job_name = "node";
          static_configs = [{
            targets = [ "localhost:9100" ];
          }];
        }

        {
          job_name = "unbound";
          static_configs = [{
            targets = [ "localhost:9167" ];
          }];
        }

        {
          job_name = "wireguard";
          static_configs = [{
            targets = [ "localhost:9586" ];
          }];
        }
      ];
    };
  };

  # Node exporter for system metrics
  services.prometheus.exporters.node = {
    enable = true;
    port = 9100;
    enabledCollectors = [
      "systemd"
      "processes"
      "network_route"
      "netdev"
      "netstat"
      "conntrack"
      "sockstat"
    ];
  };

  # Unbound exporter for DNS metrics
  services.prometheus.exporters.unbound = {
    enable = true;
    port = 9167;
  };

  # WireGuard exporter
  services.prometheus.exporters.wireguard = {
    enable = true;
    port = 9586;
    withRemoteip = true;
  };

  # Grafana for visualization
  services.grafana = {
    enable = true;
    settings = {
      server = {
        http_addr = "192.168.1.1";
        http_port = 3000;
      };

      security = {
        admin_user = "admin";
        admin_password = "secure-grafana-password";
      };
    };

    provision = {
      enable = true;
      datasources.settings.datasources = [{
        name = "Prometheus";
        type = "prometheus";
        access = "proxy";
        url = "http://localhost:9090";
        isDefault = true;
      }];
    };
  };

  # Logging
  services.journald.extraConfig = ''
    SystemMaxUse=1G
    MaxRetentionSec=1month
    ForwardToSyslog=no
  '';

  # Network monitoring tools
  environment.systemPackages = with pkgs; [
    # Network analysis
    wireshark
    tcpdump
    nmap
    netcat-gnu

    # Bandwidth monitoring
    iftop
    nethogs
    bandwhich

    # Network testing
    speedtest-cli
    mtr
    traceroute
    dig
    host

    # WireGuard tools
    wireguard-tools

    # System monitoring
    htop
    iotop
    lsof
  ];

  # Enable Wireshark for network analysis
  programs.wireshark = {
    enable = true;
    package = pkgs.wireshark;
  };

  # Create network monitoring user
  users.users.netmon = {
    isSystemUser = true;
    group = "netmon";
    createHome = true;
    home = "/var/lib/netmon";
  };
  users.groups.netmon = {};

  # Network service status script
  environment.etc."scripts/network-status.sh" = {
    text = ''
      #!/bin/bash
      echo "=== Network Status Report ==="
      echo
      echo "=== Interfaces ==="
      ip addr show
      echo
      echo "=== Routes ==="
      ip route show
      echo
      echo "=== DNS Resolution ==="
      systemd-resolve --status
      echo
      echo "=== Active Connections ==="
      ss -tulpn
      echo
      echo "=== WireGuard Status ==="
      wg show
      echo
      echo "=== Firewall Status ==="
      nft list ruleset
    '';
    mode = "0755";
  };

  system.stateVersion = "25.05";
}
```

**Testing the Configuration:**

```bash
# Apply configuration
sudo nixos-rebuild switch

# Test network connectivity
ping -c 4 8.8.8.8
ping -c 4 google.com

# Test DNS resolution
dig @192.168.1.1 nas.homelab.local
nslookup gateway.homelab.local 192.168.1.1

# Test WireGuard
wg show
ping 10.100.0.2  # Test VPN client

# Monitor network traffic
sudo tcpdump -i enp1s0
bandwhich

# Check firewall rules
sudo nft list ruleset

# Test services
systemctl status unbound
systemctl status wg-quick-wg0
systemctl status prometheus

# Network status overview
sudo /etc/scripts/network-status.sh

# Monitor with Grafana
# Open http://192.168.1.1:3000 in browser
```

**Explanation:**

This comprehensive network configuration provides:

- **Gateway Functionality**: Acts as a router/gateway for the local network
- **Static IP Configuration**: Uses systemd-networkd for reliable network setup
- **DHCP Server**: Provides IP addresses to LAN clients with static leases
- **DNS Server**: Local DNS resolution with ad blocking and caching
- **VPN Server**: WireGuard server for secure remote access
- **Advanced Firewall**: nftables with rate limiting and logging
- **Network Monitoring**: Comprehensive monitoring with Prometheus and Grafana
- **Performance Optimization**: Tuned for gateway/router performance

The setup creates a fully functional network gateway with enterprise-level features suitable for home labs or small offices.

</details>

[🔝 Back to top](#-nixos-documentation)

---

## 🔍 Troubleshooting

**📊 Chapter 15 of 20**

**🎯 Learning Objectives:**
- Master NixOS debugging and troubleshooting techniques
- Learn to diagnose system and configuration issues
- Understand recovery procedures and rollback strategies
- Practice systematic problem-solving approaches

**⏱️ Estimated Reading Time:** 20 minutes

**📋 Prerequisites:** Basic NixOS configuration and system management knowledge

### System Boot Issues

#### Boot Failures and Recovery

**Boot Menu Recovery:**
```bash
# At GRUB/systemd-boot menu:
# 1. Select "NixOS - Configuration X (version)" for previous generation
# 2. Or select "NixOS (rollback)" option

# From recovery system:
sudo nixos-rebuild switch --rollback

# Manual generation selection:
sudo /nix/var/nix/profiles/system-42-link/bin/switch-to-configuration boot
```

**Emergency Shell:**
```bash
# Add to kernel command line at boot:
# systemd.unit=emergency.target
# or
# systemd.unit=rescue.target
# or
# init=/bin/bash

# Mount root filesystem read-write:
mount -o remount,rw /

# Fix configuration and rebuild:
nixos-rebuild switch
```

**Chroot Recovery:**
```bash
# Boot from NixOS installation media
# Mount your system:
sudo mount /dev/sda1 /mnt  # Root partition
sudo mount /dev/sda2 /mnt/boot  # Boot partition (if separate)

# Chroot into system:
sudo nixos-enter --root /mnt

# Fix issues and rebuild:
nixos-rebuild switch

# Exit and reboot:
exit
sudo reboot
```

#### Configuration Errors

**Syntax Errors:**
```bash
# Check configuration syntax:
nix-instantiate --parse /etc/nixos/configuration.nix

# Detailed error information:
nixos-rebuild dry-build --show-trace

# Test configuration without applying:
nixos-rebuild dry-run
```

**Debugging Configuration:**
```nix
# Enable debugging output
{
  system.nixos.debug = true;

  # Verbose boot messages
  boot.kernelParams = [ "debug" ];
  boot.initrd.verbose = true;

  # Enable core dumps
  systemd.coredump.enable = true;

  # Extended logging
  services.journald.extraConfig = ''
    SystemMaxUse=2G
    MaxRetentionSec=1month
    ForwardToSyslog=yes
  '';
}
```

### Service and Application Issues

#### Service Debugging

**Service Status and Logs:**
```bash
# Check service status
systemctl status service-name
systemctl is-active service-name
systemctl is-enabled service-name

# View service logs
journalctl -u service-name
journalctl -u service-name -f  # Follow logs
journalctl -u service-name --since "1 hour ago"
journalctl -u service-name --lines 100

# Service dependencies
systemctl list-dependencies service-name
systemctl list-dependencies --reverse service-name

# Failed services
systemctl --failed
systemctl list-units --state=failed
```

**Service Configuration Issues:**
```bash
# Validate service configuration
systemd-analyze verify service-name.service

# Check service environment
systemctl show-environment
systemctl show service-name

# Debug service startup
systemctl daemon-reload
systemctl restart service-name
journalctl -u service-name -f
```

#### Application Crashes

**Core Dump Analysis:**
```bash
# Enable core dumps globally
echo 'kernel.core_pattern = /var/crash/core.%e.%p.%t' | sudo tee -a /etc/sysctl.conf
sudo sysctl -p

# Analyze core dumps
gdb application-binary core-file
```

**Memory Issues:**
```bash
# Check memory usage
free -h
cat /proc/meminfo
ps aux --sort=-%mem | head

# Check for OOM kills
dmesg | grep -i "killed process"
journalctl -k | grep -i "out of memory"

# Memory debugging with valgrind
valgrind --tool=memcheck --leak-check=full ./application
```

### Package and Dependency Issues

#### Package Installation Problems

**Package Conflicts:**
```bash
# Check package conflicts
nix-env --dry-run -i package-name

# Show package dependencies
nix-store --query --requisites $(which program)
nix-store --query --references $(which program)

# Check for broken packages
nix-store --verify --check-contents
nix-store --repair-path /nix/store/package-path
```

**Dependency Resolution:**
```bash
# Show why a package is installed
nix why-depends /run/current-system nixpkgs#package-name

# Dependency graph
nix-store --query --graph $(which program) | dot -Tpng > deps.png

# Package information
nix search nixpkgs package-name
nix show nixpkgs#package-name
```

#### Build Failures

**Build Debugging:**
```bash
# Build with verbose output
nix build --verbose nixpkgs#package-name

# Keep failed build directory
nix build --keep-failed nixpkgs#package-name

# Interactive debugging
nix develop nixpkgs#package-name
nix-shell '<nixpkgs>' -A package-name
```

### Network Issues

#### Network Connectivity

**Basic Network Diagnosis:**
```bash
# Check network interfaces
ip addr show
ip link show

# Check routing
ip route show
ip -6 route show

# DNS resolution
nslookup domain.com
dig domain.com
systemd-resolve --status

# Network connectivity
ping -c 4 8.8.8.8
ping -c 4 google.com
traceroute google.com
mtr google.com
```

**Service-Specific Network Issues:**
```bash
# Check listening ports
ss -tulpn
netstat -tulpn

# Check firewall rules
iptables -L -n -v  # For iptables
nft list ruleset   # For nftables

# Test specific ports
telnet hostname port
nc -zv hostname port

# Network traffic analysis
tcpdump -i interface
wireshark
```

### Hardware Issues

#### Hardware Detection

**Hardware Information:**
```bash
# System information
lshw
dmidecode
lscpu
lsmem

# PCI devices
lspci -v
lsusb -v

# Hardware sensors
sensors
lm-sensors

# Disk health
smartctl -a /dev/sda
lsblk
fdisk -l
```

**Driver Issues:**
```bash
# Check loaded modules
lsmod
modinfo module-name

# Hardware detection
hwinfo --short
inxi -Fxz

# Kernel messages
dmesg | grep -i error
dmesg | grep -i warning
journalctl -k
```

### Performance Issues

#### System Performance Analysis

**Resource Monitoring:**
```bash
# CPU usage
top
htop
iostat

# Memory analysis
free -h
cat /proc/meminfo
vmstat 1

# Disk I/O
iotop
iostat -x 1

# Network traffic
iftop
nethogs
ss -i
```

**Performance Profiling:**
```bash
# System profiling
perf top
perf record -g ./application
perf report

# Trace system calls
strace -p pid
strace -o trace.log ./application

# Process analysis
pstree
ps aux --sort=-%cpu
ps aux --sort=-%mem
```

### Configuration Recovery

#### Backup and Restore

**Configuration Backup:**
```bash
# Backup configuration
sudo cp -r /etc/nixos /backup/nixos-$(date +%Y%m%d)

# Version control integration
cd /etc/nixos
git init
git add .
git commit -m "Initial configuration"
git remote add origin https://github.com/user/nixos-config.git
git push -u origin main
```

**System Recovery:**
```bash
# List available generations
nix-env --list-generations --profile /nix/var/nix/profiles/system

# Rollback to previous generation
sudo nixos-rebuild switch --rollback

# Switch to specific generation
sudo nix-env --switch-generation 42 --profile /nix/var/nix/profiles/system
sudo /nix/var/nix/profiles/system/bin/switch-to-configuration switch

# Delete old generations
sudo nix-collect-garbage --delete-old
sudo nix-collect-garbage -d
```

### ⚠️ Common Issues and Solutions

1. **"File system full"**
   - Clean Nix store: `nix-collect-garbage -d`
   - Check disk usage: `du -sh /nix/store`
   - Optimize store: `nix-store --optimise`

2. **"Configuration.nix syntax error"**
   - Check syntax: `nix-instantiate --parse /etc/nixos/configuration.nix`
   - Use previous generation to recover
   - Fix indentation and missing semicolons

3. **"Service failed to start"**
   - Check logs: `journalctl -u service-name`
   - Verify dependencies: `systemctl list-dependencies service-name`
   - Check permissions and file paths

4. **"Package not found"**
   - Update channels: `sudo nix-channel --update`
   - Search correct name: `nix search nixpkgs package`
   - Check package availability in current channel

5. **"Out of memory"**
   - Check swap configuration
   - Monitor memory usage: `free -h`
   - Look for memory leaks: `journalctl -k | grep -i "out of memory"`

### ✅ Troubleshooting Best Practices

1. **Systematic approach**: Start with basic checks before diving deep
2. **Log analysis**: Always check logs first (`journalctl`, `dmesg`)
3. **Incremental changes**: Make small changes and test frequently
4. **Use test mode**: Use `nixos-rebuild test` before permanent changes
5. **Keep backups**: Always backup working configurations
6. **Document issues**: Keep notes of problems and solutions
7. **Use generations**: Leverage NixOS generation system for quick recovery

[🔝 Back to top](#-nixos-documentation)

---

## 📖 Glossary

**📊 Chapter 16 of 20**

**A**
- **Attribute Set**: Key-value pairs in Nix expressions, similar to dictionaries or objects in other languages
- **Atomic Upgrade**: System updates that either complete fully or fail without partial changes

**B**
- **Boot Loader**: Software that loads the operating system kernel (systemd-boot, GRUB)
- **Build**: Process of creating packages from source code and dependencies

**C**
- **Channel**: Repository of pre-built packages and system configurations
- **Configuration.nix**: Main NixOS system configuration file
- **Closure**: Complete set of dependencies needed for a package or system

**D**
- **Derivation**: Build recipe that describes how to build a package
- **Declarative**: System configuration described as desired state rather than imperative commands
- **Dry Run**: Test configuration changes without actually applying them

**E**
- **Expression**: Nix language code that evaluates to a value
- **Environment**: Collection of packages available to a user or system

**F**
- **Flake**: Self-contained Nix project with locked dependencies
- **Functional**: Programming paradigm where functions don't have side effects

**G**
- **Generation**: Snapshot of system configuration that can be rolled back to
- **Garbage Collection**: Automatic cleanup of unused packages and dependencies

**H**
- **Hash**: Cryptographic fingerprint used to identify packages uniquely
- **Home Manager**: Tool for managing user environments declaratively

**I**
- **Immutable**: Data that cannot be changed after creation
- **Imperative**: Traditional system administration with step-by-step commands

**L**
- **Lambda**: Anonymous function in Nix expressions

**M**
- **Module**: Reusable configuration component that can be imported

**N**
- **Nix**: Functional package manager and language
- **NixOS**: Linux distribution built on Nix
- **Nixpkgs**: Collection of packages and functions for Nix

**O**
- **Option**: Configuration parameter that can be set in NixOS modules
- **Overlay**: Mechanism to override or extend packages in nixpkgs

**P**
- **Package**: Software application with all its dependencies
- **Pure**: Functions that always produce the same output for the same input

**R**
- **Rebuild**: Process of applying configuration changes to the system
- **Reproducible**: Ability to recreate identical systems from the same configuration
- **Rollback**: Revert to a previous system generation

**S**
- **Store**: File system location (/nix/store) where all packages are stored
- **System**: Complete NixOS configuration including kernel, services, and packages
- **Systemd**: Init system and service manager used by NixOS

**T**
- **Test**: Apply configuration temporarily without making it permanent

**U**
- **Unfree**: Software with non-free licenses that must be explicitly allowed

[🔝 Back to top](#-nixos-documentation)

---

## 🔗 Quick Reference

**📊 Chapter 17 of 20**

### Essential Commands

**System Management:**
```bash
# Apply configuration
sudo nixos-rebuild switch
sudo nixos-rebuild test          # Temporary
sudo nixos-rebuild dry-build     # Check only

# Rollback
sudo nixos-rebuild switch --rollback

# Update system
sudo nixos-rebuild switch --upgrade

# Generation management
nix-env --list-generations --profile /nix/var/nix/profiles/system
sudo nix-collect-garbage -d
```

**Package Management:**
```bash
# Search packages
nix search nixpkgs firefox

# Install user packages
nix-env -i firefox
nix-env -e firefox              # Remove
nix-env -u                      # Upgrade all

# Package information
nix show nixpkgs#firefox
which firefox
```

**Service Management:**
```bash
# Service status
systemctl status nginx
systemctl start|stop|restart nginx
systemctl enable|disable nginx

# Logs
journalctl -u nginx
journalctl -f                   # Follow logs
```

### Configuration Snippets

**Basic System:**
```nix
{
  boot.loader.systemd-boot.enable = true;
  networking.hostName = "nixos";
  time.timeZone = "UTC";

  users.users.myuser = {
    isNormalUser = true;
    extraGroups = [ "wheel" ];
  };

  environment.systemPackages = with pkgs; [
    vim git curl
  ];

  services.openssh.enable = true;
  system.stateVersion = "25.05";
}
```

**Desktop Environment:**
```nix
{
  services.xserver = {
    enable = true;
    displayManager.gdm.enable = true;
    desktopManager.gnome.enable = true;
  };

  sound.enable = true;
  hardware.pulseaudio.enable = true;
}
```

**Development Environment:**
```nix
{
  environment.systemPackages = with pkgs; [
    git vim vscode
    nodejs python3 rustc cargo
    docker docker-compose
  ];

  virtualisation.docker.enable = true;
  users.users.dev.extraGroups = [ "docker" ];
}
```

### Troubleshooting Quick Fixes

**Boot Issues:**
- Select previous generation at boot menu
- Add `systemd.unit=rescue.target` to kernel params
- Boot from install media and `nixos-enter`

**Configuration Errors:**
```bash
nix-instantiate --parse /etc/nixos/configuration.nix
nixos-rebuild dry-build --show-trace
```

**Service Problems:**
```bash
systemctl status service-name
journalctl -u service-name -f
systemd-analyze verify service-name
```

**Storage Full:**
```bash
sudo nix-collect-garbage -d
nix-store --optimise
du -sh /nix/store
```

### File Locations

- System config: `/etc/nixos/configuration.nix`
- Hardware config: `/etc/nixos/hardware-configuration.nix`
- User config: `~/.config/nixpkgs/config.nix`
- Nix store: `/nix/store/`
- System generations: `/nix/var/nix/profiles/system-*`

[🔝 Back to top](#-nixos-documentation)

---

## 📚 Further Reading

**📊 Chapter 18 of 20**

### Official Resources

**Documentation:**
- [NixOS Manual](https://nixos.org/manual/nixos/stable/) - Official comprehensive guide
- [Nix Pills](https://nixos.org/guides/nix-pills/) - In-depth Nix language tutorial
- [NixOS Options](https://search.nixos.org/options) - Searchable configuration options
- [Nixpkgs Manual](https://nixos.org/manual/nixpkgs/stable/) - Package collection guide

**Learning Resources:**
- [Nix Tutorial](https://nixos.org/learn.html) - Getting started guide
- [NixOS Wiki](https://nixos.wiki/) - Community-maintained wiki
- [Zero to Nix](https://zero-to-nix.com/) - Beginner-friendly introduction
- [Nix by Example](https://nixbyexample.com/) - Practical examples

### Books and Guides

**Technical Books:**
- "Learning Nix and NixOS" by Domen Kožar
- "NixOS in Action" by Burke Libbey
- "Functional DevOps with Nix" - Various authors

**Community Guides:**
- [Awesome Nix](https://github.com/nix-community/awesome-nix) - Curated list of resources
- [NixOS Cookbook](https://github.com/nixos/nixos-cookbook) - Practical recipes
- [Home Manager Manual](https://nix-community.github.io/home-manager/) - User environment management

### Advanced Topics

**Specialized Areas:**
- [Nix Flakes](https://nixos.wiki/wiki/Flakes) - Modern Nix workflow
- [Cross Compilation](https://nixos.wiki/wiki/Cross_Compiling) - Building for different architectures
- [NixOS on ARM](https://nixos.wiki/wiki/NixOS_on_ARM) - Running on ARM devices
- [NixOS Containers](https://nixos.org/manual/nixos/stable/#ch-containers) - System containers

**Development:**
- [Contributing to Nixpkgs](https://nixos.org/manual/nixpkgs/stable/#chap-contributing) - Adding packages
- [Writing NixOS Modules](https://nixos.org/manual/nixos/stable/#sec-writing-modules) - Custom modules
- [Hydra CI](https://nixos.org/hydra/) - Continuous integration system

[🔝 Back to top](#-nixos-documentation)

---

## 🤝 Community Resources

**📊 Chapter 19 of 20**

### Online Communities

**Forums and Discussion:**
- [NixOS Discourse](https://discourse.nixos.org/) - Official community forum
- [r/NixOS](https://www.reddit.com/r/NixOS/) - Reddit community
- [Nix Community Discord](https://discord.gg/RbvHtGa) - Real-time chat
- [Matrix/IRC](https://nixos.org/community/) - #nixos channels

**Development:**
- [GitHub - NixOS/nixpkgs](https://github.com/NixOS/nixpkgs) - Main repository
- [GitHub - NixOS/nixos](https://github.com/NixOS/nixos) - NixOS specific code
- [Nix Community](https://github.com/nix-community) - Community projects

### Getting Help

**Support Channels:**
1. **NixOS Discourse** - Best for detailed questions and discussions
2. **IRC/Matrix** - Real-time help and quick questions
3. **GitHub Issues** - Bug reports and feature requests
4. **Stack Overflow** - Tagged questions with `nixos` or `nix`

**Before Asking:**
- Search existing discussions and documentation
- Provide system information (`nixos-version`)
- Include relevant configuration snippets
- Describe expected vs actual behavior

### Contributing

**Ways to Contribute:**
- **Documentation**: Improve manuals, wiki, and guides
- **Packages**: Add new packages or update existing ones
- **Bug Reports**: Test and report issues
- **Code Review**: Help review pull requests
- **Community Support**: Answer questions and help newcomers

**Getting Started:**
1. Read contributing guidelines
2. Start with small documentation fixes
3. Package software you use
4. Join community discussions
5. Attend local meetups or conferences

### Events and Conferences

**Regular Events:**
- **NixCon** - Annual NixOS conference
- **Local Meetups** - Check discourse for regional groups
- **Summer of Nix** - Seasonal contribution program
- **RFC Discussions** - Request for Comments processes

[🔝 Back to top](#-nixos-documentation)

---

## 💝 Contributing Guidelines

**📊 Chapter 20 of 20**

### How to Contribute to NixOS

**Types of Contributions:**
1. **Bug Fixes** - Fix broken packages or configurations
2. **New Packages** - Add software to nixpkgs
3. **Documentation** - Improve manuals and guides
4. **Testing** - Verify packages work correctly
5. **Code Review** - Review community contributions

### Package Contributions

**Adding New Packages:**
```nix
# Example package definition
{ lib, stdenv, fetchurl, cmake, pkg-config }:

stdenv.mkDerivation rec {
  pname = "myapp";
  version = "1.2.3";

  src = fetchurl {
    url = "https://github.com/user/myapp/archive/v${version}.tar.gz";
    sha256 = "sha256-AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA=";
  };

  nativeBuildInputs = [ cmake pkg-config ];
  buildInputs = [ ];

  meta = with lib; {
    description = "My awesome application";
    homepage = "https://github.com/user/myapp";
    license = licenses.mit;
    maintainers = with maintainers; [ myusername ];
    platforms = platforms.linux;
  };
}
```

**Submission Process:**
1. Fork the nixpkgs repository
2. Create a feature branch
3. Add your package definition
4. Test the package builds
5. Submit a pull request
6. Respond to review feedback

### Documentation Contributions

**Documentation Standards:**
- Use clear, concise language
- Provide working examples
- Include troubleshooting tips
- Follow existing formatting conventions
- Test all code examples

**Areas Needing Help:**
- Beginner tutorials
- Advanced configuration guides
- Hardware-specific documentation
- Service configuration examples
- Troubleshooting guides

### Code Style Guidelines

**Nix Code Style:**
```nix
# Good formatting
{
  services.nginx = {
    enable = true;
    virtualHosts."example.com" = {
      forceSSL = true;
      enableACME = true;
    };
  };

  # Use consistent indentation (2 spaces)
  # Group related options together
  # Use descriptive variable names
}
```

**Commit Messages:**
```
component: brief description

Longer explanation of the change, including:
- What was changed and why
- Any breaking changes
- References to issues or RFCs

Fixes #1234
```

### Testing Contributions

**Testing New Packages:**
```bash
# Build the package
nix-build -A mypackage

# Test in clean environment
nix-shell -p mypackage --run mypackage

# Test installation
nix-env -i mypackage
```

**System Testing:**
```bash
# Test configuration changes
nixos-rebuild test

# Verify services work
systemctl status myservice

# Check logs for errors
journalctl -u myservice
```

### Maintaining Packages

**Responsibilities:**
- Respond to issues and bug reports
- Update packages when new versions are released
- Test packages on different architectures
- Review related pull requests
- Keep package metadata current

**Update Process:**
1. Monitor upstream releases
2. Test new versions thoroughly
3. Update package definition
4. Check for breaking changes
5. Submit update pull request

### Community Guidelines

**Code of Conduct:**
- Be respectful and inclusive
- Help newcomers learn
- Provide constructive feedback
- Focus on technical merit
- Maintain professional communication

**Best Practices:**
- Start small with simple contributions
- Ask for help when needed
- Learn from feedback
- Stay engaged with the community
- Share knowledge with others

### Recognition

**Contribution Recognition:**
- Maintainer status for active contributors
- Recognition in release notes
- Community appreciation
- Learning opportunities
- Network with like-minded developers

**Long-term Benefits:**
- Deep understanding of NixOS internals
- Influence on project direction
- Professional development opportunities
- Strong open-source portfolio
- Valuable technical skills

---

## 🎉 Conclusion

Congratulations! You've completed this comprehensive NixOS documentation covering everything from basic installation to
