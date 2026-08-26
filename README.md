# Image to Data Converter

**Convert any image into structured data formats — SVG, XML, JSON, YAML, and CSV — with intelligent color quantization and region detection.**

![Demo](https://via.placeholder.com/1200x630/f4ede6/2d2a24?text=Image+to+Data+Converter)

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Live Demo](#live-demo)
- [How It Works](#how-it-works)
- [Usage](#usage)
- [Formats Explained](#formats-explained)
- [Technologies](#technologies)
- [Installation](#installation)
- [Contributing](#contributing)
- [License](#license)

---

## Overview

The **Image to Data Converter** is a web‑based tool that transforms raster images into structured, machine‑readable data. It reduces the image to a quantized palette, extracts connected regions (blobs), and exports the results in five popular formats. Whether you need vector graphics (SVG), hierarchical XML, portable JSON, human‑readable YAML, or tabular CSV, this tool has you covered.

The interface is designed for simplicity and efficiency: a unified drag‑and‑drop area, auto‑configured settings based on image dimensions, and instant visual feedback with a quantized SVG preview and color swatches.

---

## Features

- **One‑click upload** – Drag an image anywhere or click to browse. The preview appears in the same space.
- **Smart auto‑configuration** – When you load an image, the tool automatically adjusts color count, minimum region size, and downsampling based on the image resolution – giving you a great starting point.
- **Live controls** – Fine‑tune quantization with three sliders:
  - **Color count** (2–48)
  - **Minimum region size** (2–160 px²)
  - **Downsample factor** (1–12)
- **Toggle options** – Include pixel data (downsampled), region outlines in SVG, histogram, and pretty‑print.
- **Real‑time visual preview** – A clean SVG render of the quantized image with region outlines (toggleable), plus a color swatch panel showing hex codes and coverage percentages.
- **Export in 5 formats** – Switch between SVG, XML, JSON, YAML, and CSV with a single click. Each format reflects your current settings.
- **Copy & save** – Copy the generated output to your clipboard or download it as a file.
- **Image analysis** – The *Analyze* button reveals average RGB, brightness, and color range statistics.
- **Paste support** – Paste an image from your clipboard directly into the tool.
- **Fully responsive** – Works on desktop, tablet, and mobile devices.

---

## Live Demo

Try it now: **[https://imagetodata.app/](https://imagetodata.app/)**  
*(Replace with your actual domain if deployed.)*

---

## How It Works

1. **Image loading** – The image is drawn onto a canvas to extract pixel data.
2. **Color quantization** – A k‑means clustering algorithm reduces the image to a limited palette (2–48 colors).
3. **Region detection** – Connected‑component analysis groups adjacent pixels of the same color into regions (blobs). Regions smaller than the minimum size are discarded.
4. **Data structure** – The palette, regions, and (optionally) downsampled pixel rows are assembled into an internal model.
5. **Export** – The model is serialized into your chosen format using dedicated formatters.

All processing happens client‑side – no data is sent to any server, ensuring privacy and speed.

---

## Usage

### Quick Start

1. **Load an image** – Drag & drop an image onto the large central area, or click it to browse. Supported formats: PNG, JPG, WebP, BMP, GIF, SVG, ICO, TIFF.
2. **Adjust settings** – Use the sliders to control color count, minimum region size, and downsampling. Check/uncheck options like region outlines or pixel data.
3. **Convert** – Click the **Convert** button. The right panel will display a vector preview and the output in the currently selected format.
4. **Switch formats** – Click any of the format tabs (SVG, XML, JSON, YAML, CSV) to see the output in that format.
5. **Copy or Save** – Use the **Copy** button inside the output box, or click **Save** to download the file.

### Controls

| Control | Description |
|---------|-------------|
| **Color count** | Number of clusters for k‑means quantization. Higher values preserve more detail. |
| **Minimum region** | The smallest region (in pixels) that will be included in the output. Larger values filter out noise. |
| **Downsample** | Factor by which the pixel data is reduced when "include pixel data" is enabled. Higher values produce smaller output. |
| **Include pixel data** | Adds downsampled rows of color IDs to the output. |
| **Pretty print** | Formats XML, JSON, and YAML with indentation for readability. |
| **Region outlines** | Draws white borders around each region in the SVG preview. |
| **Histogram** | Adds a histogram of grayscale values to the output (if supported by the format). |

---

## Formats Explained

| Format | Best for | Description |
|--------|----------|-------------|
| **SVG** | Vector graphics, design tools | A clean SVG vector representation with one `<rect>` per region. Suitable for further editing or embedding. |
| **XML** | Data exchange, hierarchical storage | A structured XML document with metadata, palette, regions, histogram, and pixel rows. |
| **JSON** | Web APIs, JavaScript applications | Lightweight, machine‑readable JSON with the same structure as XML. |
| **YAML** | Configuration files, human‑readable data | A friendly, indentation‑based format ideal for manual inspection or configuration. |
| **CSV** | Spreadsheets, data analysis | Tabular output with separate sections for metadata, palette, regions, and histogram. Easy to import into Excel or Google Sheets. |

---

## Technologies

- **HTML5** – Semantic structure
- **CSS3** – Responsive, minimal design with a warm beige palette
- **Vanilla JavaScript** – All logic runs client‑side
- **Canvas API** – Image pixel extraction and rendering
- **k‑means clustering** – Color quantization (implemented from scratch)
- **Connected‑component labeling** – Region detection (4‑connectivity)
- **XMLSerializer / JSON / custom formatters** – Data serialization

No external libraries or frameworks – the entire tool is contained in a single HTML file.

---

## Installation

### Option 1: Run locally

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/image-to-data-converter.git
   cd image-to-data-converter
   ```
2. Open `index.html` in your browser – that’s it!

### Option 2: Host on a web server

Upload the `index.html` file to any static hosting service (Netlify, Vercel, GitHub Pages, etc.) and serve it.

---

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/amazing-feature`).
3. Commit your changes (`git commit -m 'Add some amazing feature'`).
4. Push to the branch (`git push origin feature/amazing-feature`).
5. Open a Pull Request.

---

## License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## Acknowledgements

- Built with ❤️ by the Image to Data team.
- Inspired by the need for simple, open‑source image data extraction tools.

---

**Made for designers, developers, and data enthusiasts.**
