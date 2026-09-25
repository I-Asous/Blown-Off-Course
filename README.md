# Wind Load Capacity: NYC Wind Exposure Mapping for Street Asset Siting
 
**NYC DOT Internship Project**
 
## Overview
 
NYC DOT installs street assets such as bus shelters, kiosks, and other street furniture across all five boroughs. Each one has to withstand the wind load at its location, and that load changes a lot depending on how close the site is to open water.
 
This project digitizes the wind exposure categories in the **NYC Building Code (§1609.4.3)** and maps them citywide. The result is a GIS layer that shows, for any location, which exposure category applies and how far it is from the shoreline. DOT can overlay it with asset data to decide where something can be safely placed.
 
**Core question:** Where is wind load greatest, and can a given asset be safely placed there?
 
## Background
 
### Basic Design Wind Speed (NYC Building Code §1609.3)
 
**Table 1609.3: Basic Design Wind Speed**
 
| Risk Category | Basic Design Wind Speed, mph (3-sec gust, 33 ft, Exposure C) | Mean Recurrence Interval, years | Probability of Exceedance in 50 years, % |
|---|---|---|---|
| I | 110 | 300 | 15 |
| II | 117 | 700 | 7 |
| III | 127 | 1,700 | 3 |
| IV | 132 | 3,000 | 1.6 |

 
**Why it matters for this project:**
- The wind speed sets the baseline load for a structure.
- The exposure category, mapped in this project, then adjusts that load up or down depending on location.
 
### Wind Exposure Categories (NYC Building Code §1609.4.3)
 
| Category | Description | Code Criteria |
|---|---|---|
| **B** | Sheltered, dense urban surface | Structures 30 ft tall or less: 1,500 ft of built-up surface roughness upwind. Taller structures: 2,600 ft or 20× building height, whichever is greater. |
| **C** | Default / near-shore | Applies where shown in Figure 1609.4.3, or wherever B or D doesn't apply. On the figures, this covers buildings within 2,600 ft (or 20× height) of the shoreline. |
| **D** | Coastal, highest wind | Open-water roughness for 5,000 ft (or 20× height) upwind, plus sites within 600 ft (or 20× height) of a D condition. |
 
Figures 1609.4.3(1)–(5) map these exposures along each borough's shoreline:
 
1. Manhattan
2. Bronx
3. Brooklyn
4. Queens
5. Staten Island

Code reference: <https://codelibrary.amlegal.com/codes/newyorkcity/latest/NYCadmin/0-0-0-177667>
 
## Objectives
 
1. Digitize the NYC shoreline and assign exposure categories to each segment using the code figures.
2. Build exposure zones based on distance from the shoreline, measured in feet.
3. Classify every building footprint into Exposure B, C, or D.
4. Overlay existing and proposed street assets to flag high-exposure placements.
5. Produce decision-ready maps that DOT staff can layer with other datasets.
