# musicrypt

A collection of lightweight utility scripts for managing a local music library on Linux.

## Scripts

### 1. `alacflac`
Recursively searches a directory for audio files encoded in ALAC (Apple Lossless Audio Codec) and converts them to FLAC (Free Lossless Audio Codec) using `ffmpeg`. It replaces the original file upon successful conversion.

**Usage:**
```bash
alacflac [options]
```

**Options:**
- `-v, --verbose`: Enable verbose output (shows files being converted).
- `--dir DIR`: Directory to search (default: `~/Music`).

**Dependencies:**
- Python 3
- `ffmpeg`
- `ffprobe` (usually part of the ffmpeg package)

### 2. `m3u82m3u`
Recursively finds `.m3u8` playlists and converts them to `.m3u` format. It cleans up file paths by removing relative prefix strings (like `../`) to ensure compatibility with players like MPD (Music Player Daemon). It replaces the original `.m3u8` file.

**Usage:**
```bash
m3u82m3u [options]
```

**Options:**
- `-v, --verbose`: Enable verbose output.
- `--dir DIR`: Directory to search (default: `~/Music`).

**Dependencies:**
- Python 3

## Installation

### 1. Clone the repository
Clone this repository to a location of your choice (e.g., `~/.local/scripts`):

```bash
git clone https://github.com/BagpipesRbetter/musicrypt.git ~/.local/scripts
cd ~/.local/scripts
```

### 2. Install Dependencies
Ensure you have Python 3 and FFmpeg installed.

**Debian/Ubuntu:**
```bash
sudo apt update
sudo apt install python3 ffmpeg
```

**Arch Linux:**
```bash
sudo pacman -S python ffmpeg
```

**Fedora:**
```bash
sudo dnf install python3 ffmpeg
```

### 3. Add to PATH
To run these scripts from anywhere, add the script directory to your PATH or create symbolic links to a directory already in your PATH (like `~/.local/bin`).

**Option A: Create Symbolic Links (Recommended)**
```bash
mkdir -p ~/.local/bin
ln -s ~/.local/scripts/alacflac ~/.local/bin/alacflac
ln -s ~/.local/scripts/m3u82m3u ~/.local/bin/m3u82m3u
```
*Ensure `~/.local/bin` is in your `$PATH`.*

**Option B: Add directory to PATH**
Add the following to your shell configuration file (e.g., `~/.bashrc` or `~/.zshrc`):
```bash
export PATH="$HOME/.local/scripts:$PATH"
```

## License
[MIT](LICENSE)
