# Movers Data Processing Project

## Overview

This project processes movers data from CSV files, cleans it, and enriches it with racial probabilities using the `surgeo` library. The final output is a consolidated dataset suitable for further analysis and mapping.

## Project Structure

- **Data Source**: The raw data consists of multiple CSV files . These files contain information about movers from 2020 to 2022.
- **Processing Script**: The main processing script reads, merges, cleans, and enriches the data.
- **Output**: The final processed data is saved as a CSV file.

## Steps Performed

1. **Setting Up the Environment**:
   - Set the working directory to where the CSV files are located.
   - Define the path to the project geodatabase.
   - Configure ArcPy environment settings.

2. **Merging CSV Files**:
   - Read all CSV files from the specified directory.
   - Concatenate them into a single DataFrame.
   - Remove duplicate records.

3. **Data Cleaning**:
   - Convert all string columns to uppercase for consistency.
   - Ensure ZIP codes are treated as strings.
   - Create a unique identifier (ID) for each record by concatenating the first name, last name, and ZIP code.

4. **Racial Probability Estimation**:
   - Initialize BIGS models using the `surgeo` library.
   - Calculate racial probabilities based on first name, last name, and ZIP code.
   - Assign the most probable race to each individual.

5. **Merging and Finalizing Data**:
   - Merge the original data with the racial probability data.
   - Remove any duplicate records in the merged dataset.
   - Save the final dataset as a CSV file.

## Dependencies

- `pandas`: For data manipulation and analysis.
- `numpy`: For numerical operations.
- `glob`: For file operations.
- `os`: For interacting with the operating system.
- `arcpy`: For spatial data management.
- `surgeo`: For estimating racial probabilities.

## Usage

1. **Clone the Repository**:
   ```sh
   git clone <repository_url>
   cd <repository_directory>
   ```

2. **Install Dependencies**:
   Ensure you have all the necessary Python libraries installed. You can use pip to install them:
   ```sh
   pip install pandas numpy surgeo
   ```

3. **Run the Script**:
   Execute the main script to process the data:
   ```sh
   python process_movers_data.py
   ```

4. **Output**:
   The final cleaned and enriched data will be saved as `Movers2022.csv` in the specified output directory.

## Notes

- Ensure you have the necessary permissions to access the directories and files.
- The script assumes that the raw data CSV files follow a consistent structure.
- Modify the paths in the script as needed to match your local setup.

## Contact

For any questions or issues, please create an issue in the repository.
