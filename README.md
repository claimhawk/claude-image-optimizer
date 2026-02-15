# imgopt - Image Optimizer for Claude Code

A fast terminal-based image optimizer that helps you prepare images for pasting into Claude Code without killing your context window.

## What it does

- **Clamps images between 480-720px** - automatically resizes images to an optimal size for Claude Code
- **Drag and drop** - just drag an image into the terminal and it processes automatically
- **Instant clipboard** - optimized image goes straight to your clipboard, ready to paste
- **Visual feedback** - shows original → optimized dimensions and confirmation

## Why?

Large images in Claude Code can quickly consume your context window. This tool automatically resizes images to a sensible size (480-720px) before you paste them, keeping your conversations efficient.

## Installation

### From source

```bash
git clone https://github.com/claimhawk/imgopt-rs.git
cd imgopt-rs
cargo build --release
cp target/release/imgopt /usr/local/bin/imgopt
```

### Using cargo

```bash
cargo install --git https://github.com/claimhawk/imgopt-rs
```

## Usage

1. Run the tool:
   ```bash
   imgopt
   ```

2. Drag and drop an image file into the terminal

3. The optimized image is automatically copied to your clipboard

4. Paste into Claude Code!

Press `ESC` or `Ctrl+C` to quit.

## Features

- **Smart clamping**: Images larger than 720px are scaled down, images smaller than 480px are scaled up
- **Maintains aspect ratio**: Your images stay proportional
- **High quality**: Uses Lanczos3 filtering for clean resizing
- **macOS optimized**: Native clipboard integration using osascript
- **Fast**: Processes images instantly

## Requirements

- macOS (uses osascript for clipboard operations)
- Rust 1.70+ (for building from source)

## How it works

When you drag an image into the terminal, imgopt:
1. Detects the file path automatically
2. Loads and analyzes the image dimensions
3. Calculates optimal new dimensions (clamped 480-720px)
4. Resizes using high-quality Lanczos3 filtering
5. Copies the result directly to your clipboard
6. Shows confirmation and waits for the next image

## Technical details

- Built with Rust for performance and reliability
- Uses `crossterm` for terminal UI
- Uses `image` crate for high-quality resizing
- Uses `arboard` for clipboard operations

## License

MIT

## Contributing

Issues and pull requests welcome!

---

Built with ❤️ for efficient Claude Code conversations
