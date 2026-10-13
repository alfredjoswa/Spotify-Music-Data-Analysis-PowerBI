# 🎵 Spotify Music Analysis – DAX Measures

## Project
Spotify Music Data Analysis and Visualization using Power BI

## Overview
This document contains example DAX measures for analyzing Spotify music data,
including track counts, artist performance, streaming trends, genre distribution,
and danceability.

**Assumed table name:** `Spotify`

**Note:** Replace table and column names with the actual names in your dataset.
These measures assume that each row represents one track record.

---

## 1. Total Track Count

Counts the number of track records in the dataset.

```dax
Total Tracks =
COUNTROWS('Spotify')
```

## 2. Total Artists

Counts the number of distinct artists.

```dax
Total Artists =
DISTINCTCOUNT('Spotify'[Artist])
```

## 3. Total Genres

Counts the number of distinct music genres.

```dax
Total Genres =
DISTINCTCOUNT('Spotify'[Genre])
```

## 4. Average Popularity

Calculates the average popularity score.

```dax
Average Popularity =
AVERAGE('Spotify'[Popularity])
```

## 5. Average Danceability

Calculates the average danceability value.

```dax
Average Danceability =
AVERAGE('Spotify'[Danceability])
```

## 6. Average Energy

Calculates the average energy value of the tracks.

```dax
Average Energy =
AVERAGE('Spotify'[Energy])
```

## 7. Average Tempo

Calculates the average tempo across tracks.

```dax
Average Tempo =
AVERAGE('Spotify'[Tempo])
```

## 8. Total Streams (Millions)

Calculates the total streams when the dataset stores stream values
in millions.

```dax
Total Streams (Millions) =
SUM('Spotify'[Streams_Millions])
```

## 9. Average Stream Value

Calculates the average stream value per track.

```dax
Average Streams (Millions) =
AVERAGE('Spotify'[Streams_Millions])
```

## 10. Highest Stream Value

Returns the highest stream value recorded for an individual track.

```dax
Highest Stream (Millions) =
MAX('Spotify'[Streams_Millions])
```

## 11. Minimum Stream Value

Returns the minimum stream value recorded.

```dax
Minimum Streams (Millions) =
MIN('Spotify'[Streams_Millions])
```

## 12. Explicit Track Count

Counts records marked as explicit.

```dax
Explicit Tracks =
CALCULATE(
    COUNTROWS('Spotify'),
    'Spotify'[Explicit] = TRUE()
)
```

If the Explicit column contains text values such as "Yes" and "No",
replace TRUE() with "Yes".

## 13. Non-Explicit Track Count

Counts records marked as non-explicit.

```dax
Non-Explicit Tracks =
CALCULATE(
    COUNTROWS('Spotify'),
    'Spotify'[Explicit] = FALSE()
)
```

If the Explicit column contains text values such as "Yes" and "No",
replace FALSE() with "No".

## 14. Average Track Duration

Calculates the average track duration in minutes.

```dax
Average Duration (Minutes) =
AVERAGE('Spotify'[Duration_Minutes])
```

## 15. Average Valence

Calculates the average valence value.

```dax
Average Valence =
AVERAGE('Spotify'[Valence])
```

## 16. Average Popularity by Artist

This measure returns the average popularity for the artist or artists
selected in the report.

```dax
Artist Average Popularity =
AVERAGE('Spotify'[Popularity])
```

Use Artist as the category in a chart to compare artists.

## 17. Track Count by Genre

Counts the tracks belonging to each genre in a chart.

```dax
Track Count =
COUNTROWS('Spotify')
```

Place Genre on the chart axis or legend and Track Count in Values.

## 18. Yearly Stream Analysis

Calculates the total stream value for the selected release year.

```dax
Yearly Streams (Millions) =
SUM('Spotify'[Streams_Millions])
```

Place Release_Year on the X-axis and this measure on the Y-axis.

## 19. Average Danceability by Genre

Calculates average danceability for each genre.

```dax
Genre Average Danceability =
AVERAGE('Spotify'[Danceability])
```

Place Genre on the chart axis and this measure in Values.

## 20. Tracks Released in a Selected Year

Counts tracks released in the year selected by the report filters.

```dax
Tracks Released =
COUNTROWS('Spotify')
```

Place Release_Year in a slicer or chart to explore yearly track counts.

---

## How to Use These Measures

1. Open the Power BI Desktop file.
2. Select the Spotify data table.
3. Choose Modeling → New measure.
4. Paste one DAX formula into the formula bar.
5. Press Enter.
6. Add the measure to the appropriate visualization.
7. Verify the results against the source dataset.

## Important Notes

- These measures are examples and may not match the original formulas used
  in the dashboard.
- Replace Spotify with your actual Power BI table name.
- Confirm that each column has the appropriate data type.
- Measures such as Total Streams depend on the units stored in the dataset.
- Use explicit-track formulas that match the actual data type of the Explicit column.
- Filter selections affect the results of these measures.

## Author

Alfred Joswa A

MSc Computer Science Student  
Aspiring Data Analyst | Power BI | Python | SQL
