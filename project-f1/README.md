# README for F1 Lap Times Analysis Tool

## Overview
This project is a Python-based tool designed to analyze and visualize Formula 1 lap time data from JSON files. It identifies the fastest lap times, calculates average lap times for each driver, and generates comprehensive reports. The results are displayed in tabular form and plotted as bar charts for better visualization. Additionally, the analyzed data is saved to log files for future reference.

## Features
- **Load Driver Details:** Reads driver details such as name and team from a JSON file (`f1_drivers.json`).
- **Parse Lap Times:** Extracts lap time data and Grand Prix location from JSON files.
- **Analyze Lap Times:** Identifies the fastest lap and calculates average lap times for each driver.
- **Display Results:** Outputs results in a tabular format and visualizes them using bar charts.
- **Save Logs:** Saves the processed results into separate JSON log files for each lap time data file.

## Requirements
- Python 3.7+
- Required Python packages:
  - `json`
  - `tabulate`
  - `matplotlib`

Install the required packages using the following command:
```bash
pip install tabulate matplotlib
```

## File Structure
- `f1_drivers.json`: Contains driver details (name and team) mapped by driver codes.
- `lap_times_X.json`: JSON files with lap time data for different Grand Prix events.
- `lap_times_X_log.json`: Generated log files containing the processed results for each lap time data file.
- `main.py`: The main script to execute the program.

## Input File Format
### `f1_drivers.json`
```json
{
    "DR1": {"name": "Driver 1", "team": "Team A"},
    "DR2": {"name": "Driver 2", "team": "Team B"}
}
```

### Lap Times Files (e.g., `lap_times_1.json`)
```json
{
    "grand_prix_location": "Monaco",
    "lap_times": {
        "DR1": [78.3, 77.8, 76.5],
        "DR2": [79.0, 78.5, 77.2]
    }
}
```

## How to Use
1. Ensure the `f1_drivers.json` file and lap times files (`lap_times_1.json`, etc.) are available in the same directory as `main.py`.
2. Run the main script:
   ```bash
   python main.py
   ```
3. The script will process each lap times file, display the results, and save them as JSON log files.

## Output Example
### Console Output
```
Processing file: lap_times_1.json

Grand Prix Location: Monaco

Fastest Driver Overall: DR1 with a time of 76.500 seconds

+------+-----------+---------+---------------+---------------+
| Code | Name      | Team    | Fastest Time  | Average Time  |
+------+-----------+---------+---------------+---------------+
| DR1  | Driver 1  | Team A  | 76.500        | 77.533        |
| DR2  | Driver 2  | Team B  | 77.200        | 78.233        |
+------+-----------+---------+---------------+---------------+
```

### Bar Chart
A bar chart is displayed comparing the fastest and average lap times for each driver.

### JSON Log File (e.g., `lap_times_1_log.json`)
```json
{
    "grand_prix_location": "Monaco",
    "fastest_driver": "DR1",
    "fastest_time": 76.5,
    "driver_details": [
        {
            "code": "DR1",
            "name": "Driver 1",
            "team": "Team A",
            "fastest_time": 76.5,
            "average_time": 77.533
        },
        {
            "code": "DR2",
            "name": "Driver 2",
            "team": "Team B",
            "fastest_time": 77.2,
            "average_time": 78.233
        }
    ]
}
```

## Notes
- If a file is missing or contains invalid JSON, an error message will be displayed, and the file will be skipped.
- Modify the `lap_times_files` list in the `main()` function to include additional lap time files.

## License
This project is open-source and distributed under the MIT License.

## Author
[Your Name]

