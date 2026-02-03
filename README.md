# Gridfinity Baseplate Layout Calculator

Welcome to the Gridfinity Baseplate Layout Calculator, an optimized tool designed to help you create efficient and aesthetically pleasing layouts for your Gridfinity baseplates.

## 🚀 Key Features:

- **No More Single Unit-Wide Baseplates**: This calculator ensures your layouts avoid any single unit-wide baseplates, leading to more streamlined and efficient prints.
- **Customizable Dimensions**: Input your desired dimensions in both millimeters and inches.
- **Padding Options**: Choose between Corner Justify, Center Justify, or No Padding Calculation to tailor the layout to your specific needs.
- **Detailed Bill of Materials**: The tool provides a detailed Bill of Materials (BoM) with precise padding dimensions.

## 🛠️ Usage Instructions:

1. **Select Your Units**: Choose the unit of measurement for your printer and the area you want to fill.
2. **Input Dimensions**: Enter the maximum build size of your printer and the space dimensions you want to fill with baseplates.
3. **Choose Padding Option**: Select how you want to justify the grid within the space.
4. **Calculate Layout**: Hit the "Calculate Layout" button to generate your optimized layout and BoM.
5. **Save Your SCAD Files**: Hit the individual buttons for downloading a file at the time, or press download all files in zip format to get all in one archive.

## 📦 OpenSCAD Dependencies

The generated OpenSCAD files will try to include `gridfinity-rebuilt-baseplate.scad`, which is a dependency file that needs to be in the same directory (or in OpenSCAD's library path). This file is part of the [Gridfinity Rebuilt OpenSCAD](https://github.com/kennetek/gridfinity-rebuilt-openscad) project - a modular storage system.

### Setting Up the Dependencies

**Option 1: Download the Required Files (Recommended)**

1. Go to the [Gridfinity Rebuilt OpenSCAD repository](https://github.com/kennetek/gridfinity-rebuilt-openscad)
2. Download `gridfinity-rebuilt-baseplate.scad` and any other dependencies it needs
3. Place them in the same directory as your generated SCAD file
4. Reload the file in OpenSCAD

**Option 2: Clone the Entire Repository**

If you plan to work with Gridfinity designs regularly:

1. Clone or download the entire [Gridfinity Rebuilt OpenSCAD repository](https://github.com/kennetek/gridfinity-rebuilt-openscad)
2. Place your generated SCAD file in that directory
3. Open it from there

**Option 3: Set Up OpenSCAD Library Path**

1. Download the Gridfinity files to a permanent location
2. In OpenSCAD, go to **Edit → Preferences → Library Directories**
3. Add the directory containing the Gridfinity files
4. Restart OpenSCAD

The `gridfinity-rebuilt-baseplate.scad` file defines the `gridfinityBaseplate()` module that the generated code uses. Without it, OpenSCAD won't be able to render the baseplate geometry.

## 🐳 Running with Docker:

### Using Docker Compose (Recommended)

The easiest way to run the application is with Docker Compose:

```bash
docker-compose up -d
```

This will pull the pre-built image and start the container. Access the app at `http://localhost:8501`.

To stop the container:
```bash
docker-compose down
```

### Building Locally

If you prefer to build the image yourself:

```bash
# Build the image
docker build -t gridfinity-calculator .

# Run the container
docker run -d -p 8501:8501 --name gridfinity-calculator gridfinity-calculator
```

### Pulling from Container Registry

You can also pull the pre-built image directly:

```bash
docker pull ghcr.io/jplegat/gridfinity-calculator:arm64
docker run -d -p 8501:8501 --name gridfinity-calculator ghcr.io/jplegat/gridfinity-calculator:arm64
```

Once running, open your browser to `http://localhost:8501` to use the calculator.

## 🎨 Visualization:

The tool also provides a visual representation of your layout, showing the placement of each baseplate and any necessary padding.

## 🙏 Acknowledgments:

A huge shoutout to [u/ethan_thompson](https://www.reddit.com/user/ethan_thompson) for creating the original Gridfinity calculator, which inspired this project. His work laid the foundation for this tool, and I highly recommend checking out his calculator as well.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 💡 Contributing

Contributions are welcome! Please feel free to submit a Pull Request or open an issue with any suggestions or improvements.
