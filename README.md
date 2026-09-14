# aart — Image to ASCII Art (Windows CLI)

Turn any image into ASCII art right from your terminal.

```
aart photo.jpg
```

---

## Installation

**Requirements:** [Python 3](https://www.python.org/downloads/) installed, with "Add Python to PATH" checked during setup.
**Bundled for free!** All items bundled for free: [PATH Checker](https://aart.freedev.app/info/path-checker.htm), [Python Finder](https://aart.freedev.app/info/find-python.htm) [Fix python path](https://aart.freedev.app/info/fix-py.htm)

1. Unzip the `aart` folder anywhere on your computer.
2. Double-click **`install.bat`** (or run it from a terminal).

The installer will:
- Check that Python is available
- Install the `Pillow` image library if it's missing
- Copy `aart.py` and `aart.bat` to `%LOCALAPPDATA%\aart`
- Add that folder to your **User PATH**

3. **Close and reopen your terminal** so the PATH change takes effect.

Test it worked:
```
aart --help
```

---

## Usage

```
aart <image_path> [options]
```

| Option | Description |
|---|---|
| `-w`, `--width N` | Output width in characters (default: `100`) |
| `-o`, `--output FILE` | Save result to a text file instead of printing to the terminal |
| `-c`, `--color` | Print in ANSI color (matches the image's colors — best in Windows Terminal) |
| `-i`, `--invert` | Invert the brightness mapping (useful for images with dark backgrounds) |
| `-r`, `--ramp RAMP` | Use a custom character ramp, ordered light → dark |
| `-h`, `--help` | Show help |

---

## Examples

**Basic conversion, printed to the terminal:**
```
aart photo.jpg
```

**Wider, more detailed output:**
```
aart photo.jpg -w 150
```

**Full color ASCII art (looks best in Windows Terminal):**
```
aart photo.png -w 150 -c
```

**Save the result to a text file instead of printing it:**
```
aart logo.jpg -o ascii_logo.txt
```

**Invert brightness (good for dark-background images):**
```
aart night_sky.jpg -w 80 -i
```

**Use a simpler custom character ramp:**
```
aart photo.jpg -r " .:-=+*#%@"
```

---

## Tips

- **Narrower widths (40–80)** look better for quick previews or pasting into chat.
- **Wider widths (120–200)** capture more detail but need a big terminal window or a text file to view properly.
- Color mode (`-c`) only affects terminal output — it's automatically disabled when saving to a file with `-o`, since ANSI codes don't belong in plain text.
- Works with common formats: JPG, PNG, BMP, GIF, WEBP, etc. (anything Pillow supports).
- For transparent PNGs, transparent areas are composited onto a white background before conversion.

---

## Uninstall

1. Delete the folder: `%LOCALAPPDATA%\aart`
2. Remove it from your PATH:
   - **Windows Settings → System → About → Advanced system settings → Environment Variables → Path (User variables) → Edit** → remove the `aart` entry

---

## Troubleshooting

**`'aart' is not recognized as an internal or external command`**
→ Reopen your terminal after installing (PATH changes don't apply to already-open windows). If it still fails, confirm `%LOCALAPPDATA%\aart` was added to your PATH.

**`Python was not found`**
→ Install Python from python.org and make sure "Add Python to PATH" is checked during setup.

**`ModuleNotFoundError: No module named 'PIL'`**
→ Run `pip install Pillow` manually.
