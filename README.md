# Spotify Song Clustering Analysis

This notebook performs an analysis of Spotify song data, focusing on clustering and visualization of key attributes. The purpose is to gain insights into song popularity, album performance, and genre trends.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Data Preprocessing](#data-preprocessing)
3. [Key Analyses](#key-analyses)
4. [Visualizations](#visualizations)
5. [Usage Instructions](#usage-instructions)

---

### Project Overview
This project uses a dataset containing Spotify song attributes, such as track popularity, album names, artist names, and genres. The primary objectives include:
- Identifying popular songs by applying a threshold.
- Grouping and analyzing albums and artists with the most popular tracks.
- Filtering data by genre to focus on specific trends.
- Visualizing results to understand patterns in song popularity.

### Data Preprocessing
1. **Loading the Dataset**:
   - The Spotify data is read into a pandas DataFrame for analysis.
2. **Cleaning Data**:
   - Dropped unnecessary columns (e.g., `Unnamed: 0`) for simplicity.
   - Converted `track_album_release_date` to a datetime format for easier manipulation.
3. **Handling Missing or Inconsistent Data**:
   - Used error handling (`errors='coerce'`) and conditional logic to address inconsistent date formats.
4. **Feature Engineering**:
   - Added a binary column `is_popular` to mark songs with popularity above a defined threshold.

### Key Analyses
#### 1. Popular Song Identification
- Songs are marked as popular if their popularity score exceeds a threshold (e.g., 50).
- Popularity is then analyzed at different levels:
  - By album.
  - By artist.
  - By album-artist combinations.

#### 2. Filtering by Genre
- The dataset is filtered by specific genres to focus on targeted analyses.
- Results are narrowed to albums and artists within the selected genre.

#### 3. Grouping and Aggregation
- Grouped data by album and artist, then summed the count of popular songs.
- Sorted results to identify the top-performing albums and artists.

### Visualizations
- **Bar Charts**:
  - Visualized the top 10 album-artist pairs by the number of popular songs.
- **Dynamic Titles**:
  - Adapted visualization titles to reflect the selected genre for better context.

### Usage Instructions
1. **Requirements**:
   - Python 3.8+
   - Required libraries: pandas, matplotlib, seaborn.
   - Install dependencies:
     ```bash
     pip install pandas matplotlib seaborn
     ```

2. **Steps to Run**:
   - Open the notebook: `spotify song clustering.ipynb`.
   - Run all cells sequentially.
   - Modify parameters (e.g., genre filter, popularity threshold) as needed.

3. **Customizing the Analysis**:
   - **Change Popularity Threshold**:
     Modify `popularity_threshold` to redefine what counts as a popular song.
   - **Filter by Genre**:
     Update `genre_filter` to focus on a specific genre.
   - **Adjust Visualization Settings**:
     Customize figure sizes, bar chart types, and other visualization options.

---

### Example Results
#### Sample Outputs:
- **Top Albums and Artists**:
  - Albums with the highest number of popular songs.
  - Artists dominating the popularity metrics.
- **Genre-Specific Insights**:
  - Patterns and trends within genres (e.g., Pop, Rock).

#### Sample Code for Custom Filtering:
```python
# Filter for the "Rock" genre
filtered_data = spotify_data[spotify_data['track_genre'] == 'Rock']
```

---

### Contribution
If you wish to contribute:
- Fork this repository.
- Make your changes and test them thoroughly.
- Submit a pull request with detailed explanations.

### License
This project is distributed under the MIT License. See `LICENSE` file for more details.

