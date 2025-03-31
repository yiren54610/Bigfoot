# Bigfoot

## Link to the Page
[Final Report](https://yiren54610.github.io/Bigfoot/)
[BFRO Bigfoot Sighting Incidents Report](https://www.bfro.net/gdb/)

## Update
An analytical report on the Bigfoot sighting incidents documented by the BFRO (Bigfoot Field Researchers Organization) has been developed. The following datasets are included:

- **Bigfoot_overall.csv**: Contains the number of sightings, reporting dates for each state and province in the US and Canada, and general data for other regions worldwide.
- **geot_coord.csv**: Includes latitude and longitude coordinates for each sighting location.
- **us_counties.csv**: Provides county-level data for sightings across the United States.
- **us_classes.csv**: Contains categorization details (Class A/B) for US sighting reports.
- **class_plots.csv**: Includes geospatial data related to sighting classifications.

## Goal
- **Mapping**: Visualize the distribution of Bigfoot sightings across the United States.
- **Analysis**: Examine patterns in sighting activity over time and geography.
- **Evaluation**: Identify potential issues, biases, or gaps in the data and evidence.

## Programming Languages and Tools
- **Python**: Libraries such as Beautiful Soup (for web scraping) and Pandas (for data manipulation).
- **Regex**: For text processing and pattern matching.
- **HTML**: For parsing and extracting data from web pages.
- **APIs**: 
  - Google GeoAPI (for geocoding locations).
  - FCC Area API ([link](https://geo.fcc.gov/api/census/#!/area/get_area)) (for retrieving FIPS codes).
- **GeoJson**: For handling geospatial data.
- **Datawrapper**: For creating visualizations like choropleth maps and charts.

## Process Summary

### Data Processing
1. **Data Collection**:
   - Scrape data from the BFRO website ([link](https://www.bfro.net/gdb/)) using BeautifulSoup.
   - Extract the following details for each county:
     - County name
     - Number of listings
     - Most recent report date
     - Last posted date
     - Link to detailed reports

2. **Detailed Data Extraction**:
   - Loop through each county link to access detailed sighting pages.
   - Scrape additional information such as:
     - Sighting class (Class A/B)
     - Date of sighting
     - Exact location details

3. **Geocoding**:
   - Use Google GeoAPI to obtain latitude and longitude coordinates for each sighting location.
   - Use the FCC Area API to retrieve FIPS codes for each county.

### Mapping
1. **Choropleth Map**:
   - Use Datawrapper to create a choropleth map showing the distribution of sightings across the US.
   - Apply a color gradient to represent the number of sightings per region.

2. **Washington State Locator Map**:
   - Focus on Washington State, which has the highest number of reported sightings.
   - Download forest coverage data from the US Forest Service ([link](https://data-usfs.hub.arcgis.com/datasets/usfs::forest-administrative-boundaries-feature-layer/explore)).
   - Narrow down the GeoJSON file to include only forests in Washington State.
   - Simplify the GeoJSON file using Mapshaper to reduce its size to under 2MB.
   - Add forest coverage data to the locator map.
   - Filter sightings in Washington State using Python and add markers to areas with lower forest coverage.

### Charts
- Use Datawrapper to create:
  - A bar chart showing the number of sightings by state.
  - A line area chart illustrating chronological changes in sighting reports over time.

### Reporting
- Conducted an interview with Matt Moneymaker, the president and founder of the BFRO, to gain insights into the data collection process and the organization's methodology.

## Discussion
- The analysis reveals interesting patterns in Bigfoot sightings, particularly in regions with varying forest coverage.
- Future research could focus on specific case studies, such as sightings in Central America, where forest coverage is lower, to explore potential correlations between habitat and sighting frequency.
- Limitations in the data, such as reporting biases or incomplete evidence, should be addressed in further studies.

 
