# 💻 Desktop Application Capabilities

> Load trigger: Code/Architect mode with desktop-related request.

## Cross-Platform Desktop

| Framework | Language | Binary Size | Strengths |
|---|---|---|---|
| Tauri v2 | Rust + Web frontend | ~5MB | Small binary, secure IPC, system tray |
| Electron | Node.js + Chromium | ~100MB+ | Massive ecosystem, auto-update, mature |
| Wails | Go + Web frontend | ~15MB | Native menus, system tray, simple bundling |
| .NET MAUI | C# + XAML | ~50MB | Windows + macOS native, MVVM |

## Native Windows

| Technology | Best For |
|---|---|
| WinUI 3 / Windows App SDK | Modern Fluent Design apps |
| WPF (.NET) | Enterprise desktop apps, data-heavy forms |
| WinForms | Rapid legacy app development |
| UWP | AppContainer sandbox, Store distribution |

## Native macOS

| Technology | Best For |
|---|---|
| SwiftUI + AppKit | macOS native, menu bar apps, document-based apps |
| XIB/Nib | Legacy Interface Builder, compatibility |
| Mac Catalyst | Porting iPad apps to macOS |

## System Programming

| Language | Strengths |
|---|---|
| Rust | System utilities, CLI tools, cross-compilation, zero-cost abstractions |
| C/C++ | Win32 API, COM, Qt/GTK bindings, hardware interfacing |
| Go | CLI tools, cross-platform builds, embedded FS, system services |
| Zig | Drop-in C replacement, cross-compilation, no hidden control flow |

## Distribution

| Platform | Installer | Auto-Update | Signing |
|---|---|---|---|
| Windows | MSI (WiX), Inno Setup, NSIS, Squirrel | Squirrel | Authenticode |
| macOS | DMG, .app bundle, .pkg | Sparkle | Apple Developer ID + Notarization |
| Linux | AppImage, Flatpak, Snap, deb/rpm | AppImageUpdate | GPG signature |
