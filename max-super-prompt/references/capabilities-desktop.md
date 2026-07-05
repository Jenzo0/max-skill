# 💻 Desktop Application Capabilities

> Load this module for desktop app development, cross-platform GUI, or system programming.
> Load trigger: Code / Architect mode with desktop-related request.

## Cross-Platform Desktop
- **Tauri v2**: Rust backend + web frontend, small binary, secure IPC
- **Electron**: Chromium + Node.js, auto-update, native modules, context isolation
- **Wails**: Go backend + web frontend, native menus, system tray
- **.NET MAUI**: Windows + macOS, MVVM, platform-specific APIs

## Native Windows
- **WinUI 3 / Windows App SDK**: Modern WinRT XAML, Fluent Design
- **WPF**: XAML + MVVM, data binding, styles and templates, commands
- **WinForms**: Rapid legacy app dev, drag-drop designer, .NET 8 support
- **UWP**: Universal Windows Platform, AppContainer sandbox
- **PowerShell**: Automation, system administration, GUI with WinForms/WPF

## Native macOS
- **SwiftUI / AppKit**: macOS native, NSDocument, NSToolbar, menu bar apps
- **XIB/Nib**: Legacy Interface Builder, auto layout
- **macOS Extensions**: Today widgets, share extensions, Finder Sync
- **Notarization**: Apple notary service, hardened runtime, entitlements

## System Programming (Low-Level)
- **Rust**: System utilities, CLI tools, cross-compilation, zero-cost abstractions
- **C/C++**: Win32 API, COM, POSIX, GTK/Qt bindings, hardware interfacing
- **Go**: CLI tools, cross-platform builds, embedded FS, system services
- **Zig**: Drop-in C replacement, cross-compilation, no hidden control flow

## Distribution & Packaging
- **Installers**: MSI (WiX), Inno Setup, NSIS, Squirrel (Electron), DMG (macOS)
- **Auto-Update**: Sparkle (macOS), Squirrel (Windows), Tauri updater
- **Signing**: Authenticode (Windows), Apple Developer ID (macOS), notarization
- **Portable Apps**: Single executable, no install, AppImage (Linux), .app (macOS)

## Shell & Automation
- **PowerShell**: Modules, DSC, remoting, REST API integration
- **Batch/CMD**: Legacy scripting, registry modification, scheduled tasks
- **Shell Extensions**: Context menu handlers, property sheets, thumbnail providers
- **Daemons/Services**: Windows Services, launchd (macOS), systemd (Linux)
- **Task Scheduling**: Windows Task Scheduler, cron, launchd plists

## Performance & Optimization
- **Memory**: Memory-mapped files, sparse allocation, GC tuning (.NET, Go)
- **Concurrency**: Thread pools, async/await, SIMD, GPU compute (CUDA, Metal)
- **Startup**: Lazy initialization, splash screens, background compilation
- **Profiling**: PerfView (Windows), Instruments (macOS), pprof (Go), samply (Rust)
- **Binary Size**: Stripping symbols, UPX compression, LTO, dead code elimination

## Security
- **Sandboxing**: AppContainer, Seatbelt (macOS), seccomp (Linux)
- **Code Integrity**: Authenticode signing, code injection prevention, ASLR
- **Privileges**: UAC (Windows), sudo elevation, privilege separation
- **Data Protection**: DPAPI (Windows), Keychain (macOS), libsodium cross-platform
- **Anti-Tampering**: Checksums, digital signatures, code obfuscation
