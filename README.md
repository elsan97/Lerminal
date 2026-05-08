# Lerminal - Linux Terminal for Windows with Fake BIOS

Lerminal is a Linux terminal for Windows with fake BIOS that automatically installs OS on virtual disk. Written in assembly (ASM) with auto-installation system.

## Features
- **Fake BIOS** - emulates BIOS with auto-install capability
- **Auto OS installation** - automatically installs Alpine Linux to virtual disk
- **Virtual disk management** - creates and manages virtual disks
- **Terminal interface** - Linux terminal interface for Windows
- **Pure assembly** - maximum performance, minimal overhead
- **Windows compatible** - works on Windows 7/8/10/11

## How it works
1. **Fake BIOS** loads and checks for ISO/virtual disk
2. **Auto-installer** automatically installs Alpine Linux to virtual disk
3. **QEMU** runs the installed system
4. **Terminal** provides Linux command line interface

## Project structure
- `boot.asm` - system bootloader
- `kernel.asm` - terminal kernel
- `disk.asm` - virtual disk management
- `terminal.asm` - terminal interface
- `fakebios.asm` - fake BIOS with auto-install
- `lerminal.asm` - main program
- `autoinstall.sh` - Alpine auto-installer script
- `autosetup.bat` - Windows setup script
- `build.bat` - build script for Windows
- `install.bat` - installer
- `Makefile` - advanced build system

## Quick start
### Option 1: Auto setup (recommended)
```bash
autosetup.bat
```

### Option 2: Manual installation
1. Run `install.bat` (admin rights required)
2. Run `C:\Lerminal\run.bat`
3. Select "Auto-install Alpine Linux"
4. Wait for installation (5-10 minutes)
5. Select "Run installed system"

### Option 3: Manual build
```bash
build.bat
run.bat
```

## Auto-installation process
1. Downloads Alpine Linux ISO (~130 MB)
2. Creates 4GB virtual disk
3. Automatically installs Alpine to disk
4. Configures system with default settings
5. Ready to use Linux terminal

## Requirements
- Windows 7/8/10/11
- NASM in C:\NASM (assembler)
- QEMU (recommended, for virtualization)
- 512 MB RAM minimum
- 5 GB free disk space
- Administrator rights for installation

## Commands after installation
```bash
# Run installed system
qemu-system-x86_64 -drive file="C:\Lerminal\disks\virtual_disk.img",format=raw -m 512M -nographic

# Build fake BIOS
C:\NASM\nasm.exe -f bin fakebios.asm -o fakebios.bin

# Auto-install Alpine
call autoinstall.bat
```

## Fake BIOS features
- Detects ISO and virtual disk
- Auto-partitions disk
- Installs bootloader
- Configures network
- Sets up user accounts
- Reboots to installed system

## Notes
- All messages in English (no encoding issues)
- UTF-8 support in batch files
- Alpine Linux: ~130 MB ISO, ~50 MB installed
- Virtual disk: 4GB default, customizable
- No manual intervention required
