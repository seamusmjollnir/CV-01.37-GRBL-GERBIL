# The CV-01.37 GRBL GERBIL
<img width="400" height="400" alt="gerbil" src="https://github.com/user-attachments/assets/93d09caf-0d3a-42a4-b209-d982713bff9c" />

### The free, no-bullshit laser engraving control application built specifically for the Creality CV-01 Pro

---

## What Is This

The CV-01.37 GRBL GERBIL is a complete laser engraving and cutting control application that runs entirely inside your web browser. There is no installation. There is no account. There is no subscription. There is no cloud. You open one HTML file in Chrome or Edge and you have a fully functional laser control studio ready to connect to your Creality CV-01 Pro over USB and start burning.

This was built because the software that ships with the CV-01 Pro is garbage, and LightBurn costs $60 for a machine that costs $200. That ratio is stupid. This application does everything you actually need — drawing, importing, image processing, vector tracing, QR code generation, G-code generation, direct USB control, and SD card export — in a single self-contained file smaller than most cell phone photos.

## Who Is This For

This is for anyone who owns a Creality CV-01 Pro laser engraver and is tired of fighting with Creality's bundled software or doesn't want to pay $60 for LightBurn. Every setting in this application — the bed dimensions, the power range, the S-value mapping, and the material presets — is purpose-built and pre-tuned for the CV-01 Pro. You plug in your laser, open this file, and go.

## Machine Specifications (Creality CV-01 Pro)

| Spec | Value |
|------|-------|
| Bed Size | 170mm × 200mm |
| Laser | 1.6W diode at 450nm wavelength |
| Firmware | GRBL 1.1f |
| Connection | USB-C (serial at 115200 baud) |
| SD Card | Standard SD slot, accepts `.nc` and `.gcode` files on root |
| S-Value Max | 255 ($30=255) |
| Power Range | 0–100% mapped to S0–S255 |

## How To Use It

### Step 1: Download

Download the file `THE_CV-01.37_GRBL_GERBIL.html` from this repository. Save it anywhere on your computer. Your desktop is fine.

### Step 2: Open It

Double-click the HTML file. It will open in your default browser. If your default browser is not Chrome or Edge, right-click the file, choose "Open with," and select Google Chrome or Microsoft Edge. These are the only two browsers that support the USB serial connection this application uses. Firefox and Safari will not work for machine control, though the design tools will still function.

### Step 3: Start Working

After a quick splash screen, you are looking at the full application. There is nothing else to install, configure, download, update, or register. The entire application — all the code, all the icons, all the interface, even the logo — is inside that one file.

### Step 4: Connect Your Laser

Plug your CV-01 Pro into your computer via USB-C. Click the green **Connect USB** button in the top banner. Your browser will show a popup listing available serial ports. Select the one that corresponds to your CV-01 Pro. On Windows this is typically labeled as a COM port (COM3, COM4, etc.). The status indicator will turn green and show "USB" when connected.

### Step 5: Create or Import Your Design

Use the drawing tools on the left sidebar to create shapes and text directly on the canvas, or import existing designs using the **Import** button. The application accepts SVG, DXF, PNG, JPG, BMP, GIF, and WEBP files. Drag and drop also works — just drag a file onto the canvas area.

### Step 6: Configure Your Cut/Engrave Settings

Each layer in the right panel has its own speed, power, number of passes, and mode (cut or engrave). You can also open the **Materials Library** to apply one of 12 pre-tuned presets that are calibrated specifically for the CV-01 Pro's 1.6W laser.

### Step 7: Send To Machine

You have three options for getting your design to the laser:

- **Run directly over USB** — Click the Play button in the Control tab to stream G-code to the machine in real time
- **Export .gcode file** — Click the `.gcode` button in the top banner to download a G-code file, then copy it to your SD card manually
- **Write directly to SD card** — Click the **SD Card** button and your browser will prompt you to select your SD card. The application writes the `.nc` file directly to the card. There is also a **Batch SD** option that writes one file per layer

## Complete Feature List

### Drawing Tools
- **Rectangle** — Click and drag to create rectangles of any size on the work area
- **Circle** — Click and drag to create circles from center point outward
- **Line** — Click to set the start point, drag to the end point
- **Text** — Click anywhere on the canvas to place text with full font controls
- **Select** — Click any object to select it, then drag to move it

### Text System
- **13 built-in fonts** — Monospace, Arial, Helvetica, Times New Roman, Georgia, Courier New, Verdana, Impact, Comic Sans MS, Trebuchet MS, Lucida Console, Tahoma, and Palatino Linotype
- **Custom font upload** — Upload any .ttf, .otf, .woff, or .woff2 font file from your computer. Custom fonts appear in the dropdown with a ★ prefix
- **Adjustable font size** — Set the size in millimeters
- **Live preview** — A preview of your text in the selected font appears in the toolbar as you type
- **Text on path** — Wrap text along a circular arc for curved engraving on signs, awards, and labels

### File Import
- **SVG** — Scalable Vector Graphics with paths, rectangles, circles, lines, and polygons
- **DXF** — AutoCAD Drawing Exchange Format with LINE, CIRCLE, ARC, and LWPOLYLINE entities
- **PNG, JPG, BMP, GIF, WEBP** — Raster images for engraving with full image editing suite
- **Drag and drop** — Drag any supported file directly onto the canvas

### Image Editing
When a raster image is selected, the Image tab provides a complete processing pipeline:
- **Brightness, Contrast, Gamma** — Adjust tonal range
- **Threshold** — Convert to pure black and white at a configurable cutoff
- **Invert** — Swap black and white
- **DPI Selection** — Set dots-per-inch for raster output
- **Four dithering algorithms** — Floyd-Steinberg, Atkinson, Ordered Bayer, and Threshold

### Image Trace (Auto-Vectorize)
Select a processed raster image and click **Trace** in the top toolbar. The application extracts vector contour lines from the image using a marching squares algorithm. This converts photographs and raster art into cuttable vector paths — one of the most-requested features in any laser software.

### QR Code Generator
Click **QR** in the top toolbar. Type any URL, text, or data into the input field, set the size in millimeters, and click Generate. The application creates a vector QR code made of individual rectangles on the active layer, ready to engrave. No external service, no internet connection required.

### Array / Tile Tool
Select any object and click **Array** in the top toolbar. Set the number of rows, columns, and gap spacing in millimeters. The tool duplicates the selected object in a grid pattern — essential for batch production of keychains, tags, coasters, labels, and any repeated item.

### Alignment
When an object is selected, the right panel shows alignment buttons:
- **Align Left / Center / Right** — Horizontal alignment to the bed
- **Align Top / Middle / Bottom** — Vertical alignment to the bed

Instantly center your design on the work area or snap it to any edge.

### Boolean Operations
Combine or subtract shapes with three operations:
- **Union** — Merge two overlapping rectangles into one bounding shape
- **Subtract** — Cut one rectangle out of another
- **Intersect** — Keep only the overlapping area between two rectangles

### Layer System
Every object belongs to a layer. Each layer has independent settings:
- **Name** — Editable label for organization
- **Color** — Visual identifier on the canvas (8 colors available)
- **Speed** — Feed rate in mm/min
- **Power** — Laser power percentage (0–100%, mapped to S0–S255)
- **Passes** — Number of times the laser traces each path
- **Mode** — Cut (M4 dynamic power) or Engrave
- **Visibility** — Toggle layer visibility without deleting
- **Lock** — Prevent accidental edits

### G-Code Generation
- Full GRBL 1.1f compatible G-code output
- Path optimization to minimize travel moves
- Per-layer speed, power, and pass settings
- M3 (constant power) and M4 (dynamic power) modes
- Automatic homing return at end of job
- Preview generated G-code in the built-in console

### Rotary Axis Support
Enable rotary mode in the Control panel for engraving cylindrical objects like tumblers, bottles, and mugs. Set the cylinder diameter in millimeters and the application adjusts the Y-axis mapping in the G-code output. Works with the CV-01 Pro rotary accessory (sold separately by Creality).

### Material Library
12 pre-tuned presets calibrated for the CV-01 Pro's 1.6W 450nm diode:

| Material | Speed (mm/min) | Power (%) | Passes | Mode |
|----------|---------------|-----------|--------|------|
| Basswood 3mm Cut | 800 | 100 | 1 | Cut |
| Basswood Engrave | 3000 | 60 | 1 | Engrave |
| Cardboard | 600 | 80 | 1 | Cut |
| Leather (thin) | 500 | 90 | 2 | Cut |
| Leather Engrave | 2000 | 40 | 1 | Engrave |
| Acrylic 2mm | 200 | 100 | 3 | Cut |
| Bamboo Engrave | 2500 | 50 | 1 | Engrave |
| Rubber Stamp | 1500 | 70 | 1 | Engrave |
| Paper Cut | 1200 | 40 | 1 | Cut |
| Fabric (cotton) | 1000 | 50 | 1 | Cut |
| Cork Engrave | 2000 | 45 | 1 | Engrave |
| Anodized Alum | 500 | 100 | 3 | Engrave |

### Machine Control (USB Connected)
- **Jog Controls** — Move the laser head in X and Y with configurable step sizes (0.1mm, 1mm, 10mm)
- **Home** — Send the machine to its home position
- **Frame Preview** — Trace the bounding box of your design at low power to verify placement
- **Run / Pause / Resume / Stop** — Full job control
- **GRBL Console** — Direct terminal for raw GRBL commands with simulated offline mode

### SD Card Operations
- **Single file write** — Write the entire job as one `.nc` file to your SD card root
- **Batch write** — Write one `.nc` file per layer for selective burning from the machine's SD card menu

### Power / Speed Test Grid
Built-in 5×5 test pattern generator. Each square uses a different speed/power combination. Burn on scrap material to find your ideal settings before committing to a real job.

### Burn Simulation Preview
Click **Burn Sim** in the top toolbar to overlay a wood grain texture on the canvas. See approximately what your engraving will look like on material before you run the job. Toggle off to return to the normal view.

### Canvas Features
- **Snap to Grid** — Toggle the magnet icon in the left toolbar. Objects snap to a 5mm grid
- **Rulers** — Millimeter measurement rulers along the top and left edges. Toggle with the ruler icon
- **Zoom** — Mouse scroll wheel or toolbar buttons
- **Pan** — Middle-click and drag
- **Object manipulation** — Select, move, duplicate, delete, rotate 90°, flip horizontal, flip vertical

### Sound Effects
The application includes audio feedback for key actions — button clicks, laser start, job completion chimes, and error alerts. All sounds are generated using the Web Audio API with no external files. Toggle sound on or off with the speaker icon in the left toolbar.

### Project Save / Load
- **Save** — Export your workspace as a `.grbl` JSON file
- **Load** — Import a previously saved `.grbl` project to pick up where you left off
- Projects preserve all object positions, layer configurations, and settings

### Undo / Redo
Full undo/redo history for every canvas and layer modification.
- **Ctrl+Z** — Undo
- **Ctrl+Y** — Redo

### Keyboard Shortcuts

| Key | Action |
|-----|--------|
| V | Select tool |
| R | Rectangle tool |
| C | Circle tool |
| L | Line tool |
| T | Text tool |
| Delete | Delete selected object |
| Ctrl+Z | Undo |
| Ctrl+Y | Redo |

## ADHD Pill Blaster (Mini-Game)

Click the gamepad icon in the left toolbar to launch the built-in mini-game. Control a laser engraver that fires upward at falling capsule pills labeled "ADHD." Hit pills to score points. Miss three and it's game over. Speed and spawn rate increase as your score climbs. High scores are saved locally and displayed on the game over screen.

**Controls:** A/D or Arrow Keys to move. Space or Up Arrow to fire. ESC to close.

## Animated Splash Screen

On launch, the application displays an animated splash screen with the GRBL GERBIL logo and a loading bar. It auto-dismisses after 2.8 seconds. This is purely cosmetic — the application is ready to use the moment the splash clears.

## Browser Requirements

**Google Chrome** (version 89+) or **Microsoft Edge** (version 89+). No other browsers are supported for full functionality.

The application uses two browser APIs exclusive to Chrome and Edge:
- **Web Serial API** — For USB communication with the laser
- **File System Access API** — For writing G-code files directly to SD cards

Firefox, Safari, Opera, and Brave can run the design tools but cannot connect to the laser or write to SD cards.

## Linux Setup

On Linux, serial port access requires membership in the `dialout` group:

```
sudo usermod -a -G dialout $USER
```

Log out and back in after running this command. Chrome serial then works identically to Windows.

## What This Is Not

- This is not a general-purpose laser application. It is built for one machine: the **Creality CV-01 Pro**. Bed size, power range, S-value mapping, and presets are all hardcoded for this laser
- This is not LightBurn. LightBurn has a decade of development, camera integration, variable power ramping, and support for hundreds of machines. This is a focused, single-machine tool that does the core job without the price tag
- This does not require an internet connection. Once saved to your computer, it runs entirely offline. No telemetry, no cloud, no updates

## File Size

The entire application compiles into a single HTML file at approximately 446 kilobytes. That includes all source code, all icons, the full logo image, the QR code library, and the mini-game. Smaller than most cell phone photos.

## Pricing

This application is available for **$10 CAD**. Payment accepted via DONATION of crypto to   . Upon confirmation of payment, the HTML file will be sent to you directly via email. The source code is also freely available in this repository if you want to compile it yourself for free.

**No refunds. No returns. No complaints.**

You can see exactly what the application does before you buy it. The source code is right here. There are no surprises.

## Contact

For purchases, questions, or support, email with "GRBL GERBIL" in the subject line.

## Built By

The CV-01.37 GRBL GERBIL was built by Seamus Mjollnir in Parksville, British Columbia, Canada. Born out of frustration with overpriced and underdelivering laser software.

## License

MIT License. Do what you want with it. See [LICENSE](LICENSE) for the full text.
