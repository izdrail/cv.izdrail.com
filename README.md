# cv.izdrail.com

This repository contains the source code and JSON data for Stefan Izdrail's personal CV website and PDF generation, based on [jsoncv](https://github.com/reorx/jsoncv).

## Architecture & Tech Stack

- **Vite:** Used as the build tool and development server.
- **EJS:** Used for templating the CV structure.
- **SCSS:** For styling the CV and ensuring print-friendly PDF generation.
- **JSON Schema:** The CV content is maintained in a structured JSON format (`izdrail.cv.json`), conforming to a customized version of the JSON Resume Schema.

## Getting Started

### Prerequisites

- Node.js (version 18 or higher recommended)
- npm or yarn

### Installation

1. Clone the repository:
   ```bash
   git clone git@github.com:izdrail/cv.izdrail.com.git
   cd cv.izdrail.com
   ```
2. Install dependencies:
   ```bash
   npm install
   ```

## Usage

### Development

To start a local development server with hot-reloading:

```bash
npm run dev
```

This will run Vite and build the CV using `izdrail.cv.json` as the data source and the default theme (`izdrail`). You can view it in your browser, typically at `http://localhost:5173`.

### Updating the CV Content

All CV data is stored in `izdrail.cv.json`. To update your experience, skills, or any other details, simply edit this file. The development server will automatically reload with the changes.

### Building the HTML/PDF CV

To build the optimized, single-file HTML version of the CV:

```bash
npm run build
```

The output will be placed in the `dist` directory by default. 

**Environment Variables:**
You can customize the build using environment variables:
- `DATA_FILENAME`: The JSON file to use for data (default: `./izdrail.cv.json`).
- `OUT_DIR`: The output directory for the built files (default: `dist`).
- `THEME`: The theme folder to use from `src/themes/` (default: `izdrail`).

Example:
```bash
DATA_FILENAME="./izdrail.cv.json" OUT_DIR="build" THEME="izdrail" npm run build
```

### Converting to PDF

The generated HTML file is optimized for printing. To create a PDF:
1. Open the generated `dist/index.html` file in Google Chrome.
2. Press `Cmd + P` (or `Ctrl + P` on Windows).
3. Select **"Save as PDF"** as the destination.
4. Ensure headers and footers are unchecked, and background graphics are checked.
5. Click **Save**.

### Static Site Features

If you want to build the broader static site layout (e.g., with an editor, preview features, etc.), you can use the site-specific scripts:

```bash
# Run site dev server
npm run dev-site

# Build static site
npm run build-site
```

## Theme Customization

Themes are located in the `src/themes/` directory. The primary theme used here is `izdrail`. To make styling changes (colors, typography, layout), edit `src/themes/izdrail/index.scss` and the corresponding `index.ejs` template.

## Credits

This project is built upon the excellent [jsoncv](https://github.com/reorx/jsoncv) toolkit by [reorx](https://github.com/reorx).
