# 🐄 Cattle Movement Tracker

A real-time web application for monitoring and tracking cattle movements across different stops on a farm. The application provides interactive maps, live data visualization, and journey progress tracking.

## 🌟 Features

- **Interactive Farm Map**: Visual representation of cattle locations with custom markers
- **Real-time Data Updates**: Live tracking of cattle status, position, and movement
- **Journey Progress Visualization**: Network graph showing cattle's path through farm stops
- **Data Analytics**: Bar chart displaying cattle distribution across different stops
- **Responsive Design**: Works seamlessly across different screen sizes

## 📋 Table of Contents

- [Features](#-features)
- [Installation](#-installation)
- [Usage](#-usage)
- [File Structure](#-file-structure)
- [Data Format](#-data-format)
- [Technology Stack](#-technology-stack)
- [API Reference](#-api-reference)
- [Contributing](#-contributing)
- [License](#-license)

## 🚀 Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/cattle-movement-tracker.git
   cd cattle-movement-tracker
   ```

2. **Set up the project structure**:
   ```
   cattle-movement-tracker/
   ├── index.html
   ├── script.js
   ├── style.css
   └── data/
       └── cattles.json
   ```

3. **Start a local server**:
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js (if you have http-server installed)
   npx http-server
   
   # Using PHP
   php -S localhost:8000
   ```

4. **Open in browser**:
   Navigate to `http://localhost:8000` in your web browser.

## 📖 Usage

### Main Interface

1. **Map View**: The main map displays cattle locations with numbered markers (🐄 1, 🐄 2, etc.)
2. **Click on Markers**: Click any cattle marker to view its journey progress
3. **Hover for Details**: Hover over markers to see detailed information popup
4. **Live Updates**: Data refreshes automatically every 5 seconds

### Data Visualization

- **Bar Chart**: Shows distribution of cattle across different farm stops
- **Data Table**: Displays detailed information about each cattle including:
  - Cattle ID
  - Current Stop
  - Status (Moving, Grazing, Reached)
  - Distance Travelled
  - Remaining Distance
  - Grazing Time
  - Walking Time
  
<img width="1919" height="866" alt="Screenshot 2025-07-13 201216" src="https://github.com/user-attachments/assets/d6ff9cdb-7898-46fc-afb6-9cf965aea520" />


### Journey Progress

- **Network Graph**: Click on any cattle marker to see its journey visualization
- **Color Coding**:
  - **Green**: Completed stops
  - **Yellow**: Current stop
  - **Gray**: Upcoming stops

## 📁 File Structure

```
cattle-movement-tracker/
├── index.html          # Main HTML file
├── script.js           # JavaScript functionality
├── style.css           # Styling and layout
└── data/
    └── cattles.json    # Cattle data (100 entries)
```

## 📊 Data Format

The `cattles.json` file contains an array of cattle objects with the following structure:

```json
{
  "id": 1,
  "currentStop": 1,
  "status": "Moving",
  "travelled": 4,
  "remaining": 7,
  "grazingTime": 30,
  "walkingTime": 120
}
```

### Data Fields

- `id`: Unique cattle identifier
- `currentStop`: Current stop index (0-8)
- `status`: Current activity ("Moving", "Grazing", "Reached")
- `travelled`: Distance covered in kilometers
- `remaining`: Distance remaining to next stop
- `grazingTime`: Time spent grazing in seconds
- `walkingTime`: Time spent walking in seconds

### Farm Stops

The application tracks cattle movement through 9 predefined stops:

1. **Central Barn** (Stop 0)
2. **Water Trough** (Stop 1)
3. **Mango Orchard** (Stop 2)
4. **Open Grazing Field** (Stop 3)
5. **Mud Pond** (Stop 4)
6. **Wheat Zone** (Stop 5)
7. **Milking Station** (Stop 6)
8. **Shed Crossing** (Stop 7)
9. **Main Shelter** (Stop 8)

## 🛠️ Technology Stack

- **HTML5**: Structure and layout
- **CSS3**: Styling and responsive design
- **JavaScript (ES6+)**: Application logic and interactivity
- **Leaflet.js**: Interactive mapping
- **Chart.js**: Data visualization charts
- **Vis.js**: Network graph visualization
- **OpenStreetMap**: Map tiles

## 🔧 API Reference

### Main Functions

#### `initMap()`
Initializes the interactive map with cattle markers.

#### `initTable()`
Populates the data table with cattle information.

#### `initChart()`
Creates the bar chart for cattle distribution.

#### `updateAll()`
Updates all data and visualizations (called every 5 seconds).

#### `drawGraph(cattle)`
Generates the journey progress graph for a specific cattle.

### Data Updates

The application simulates real-time updates by:
- Randomly changing cattle status between "Moving" and "Grazing"
- Incrementing travel distances for moving cattle
- Updating time counters for grazing and walking
- Moving cattle to next stops when distance targets are reached

## 🎨 Customization

### Styling

Modify `style.css` to change:
- Color schemes
- Layout arrangements
- Font styles
- Responsive breakpoints

### Map Configuration

In `script.js`, update:
- `stopLocations[]`: GPS coordinates for farm stops
- `stops[]`: Names of farm locations
- Map center and zoom level

### Data Source

Replace `data/cattles.json` with your own cattle data or integrate with a real-time API.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is **free for all** - use, modify, and distribute without any restrictions. No license required!

## 🐛 Known Issues

- Map markers may overlap when multiple cattle are at the same stop
- Network graph layout may vary between renders
- Large datasets (>200 cattle) may impact performance

## 🔮 Future Enhancements

- [ ] Real-time GPS integration
- [ ] Historical movement analytics
- [ ] Mobile app version
- [ ] Push notifications for alerts
- [ ] Export functionality for reports
- [ ] Multi-farm support
