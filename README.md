# Bird Biodiversity by HOLC Grades in LA County

Analysis of biodiversity in bird observations in historically redlined areas in Los Angeles

![](figs/birds-on-power-line.png)

## Background

This data analysis project seeks to investigate how present-day environmental justice may reflect legacies of injustice in the past. The United States has a long history of racial segregation which is still visible. During the 1930's the Home Owners' Loan Corporation (HOLC), as part of the New Deal, rated neighborhoods based on their perceived safety for real estate investment. Their problematic (read: racist, discriminatory) ranking system went from A ("most safe") to D ("hazardous"). These rankings were also color-coded:

-   (A (green)
-   B (blue)
-   C (yellow)
-   D (red))

These rankings were then used to block access to loans for home ownership. Colloquially known as "redlining", this practice has had widely-documented consequences not only for community wealth, but also health.[^readme-1] Redlined neighborhoods have less greenery[^readme-2] and are hotter than other neighborhoods .[^readme-3]

[^readme-1]: Gee, G. C. (2008). A multilevel analysis of the relationship between institutional and individual racial discrimination and health status. American journal of public health, 98(Supplement_1), S48-S56.

[^readme-2]: Nardone, A., Rudolph, K. E., Morello-Frosch, R., & Casey, J. A. (2021). Redlines and greenspace: the relationship between historical redlining and 2010 greenspace across the United States. Environmental health perspectives, 129(1), 017006.

[^readme-3]: Hoffman, J. S., Shandas, V., & Pendleton, N. (2020). The effects of historical housing policies on resident exposure to intra-urban heat: a study of 108 US urban areas. Climate, 8(1), 12.

A recent study -- co-authored by [Dr. Millie Chapman](https://scholar.google.com/citations?user=xJHRncgAAAAJ&hl=en), who was my graduate student instructor in an Environmental Data Science class taught by [Carl Boettiger](https://github.com/cboettig) that I took at UC Berkeley in 2020 -- found that redlining has not only affected the environments communities are exposed to, it has also shaped our observations of biodiversity.[^readme-4]

[^readme-4]: Ellis-Soto, D., Chapman, M., & Locke, D. H. (2023). Historical redlining is associated with increasing geographical disparities in bird biodiversity sampling in the United States. Nature Human Behaviour, 1-9.

Community or citizen science, whereby individuals share observations of species, is generating an enormous volume of data. Ellis-Soto and co-authors found that redlined neighborhoods remain the most undersampled areas across 195 US cities. This gap is highly concerning, because conservation decisions are made based on these data.

## Data

### EJ Screen US EPA data:

To understand the current environmental, demographic, and public health conditions at a census block group level in LA County, I work with data from the United States Environmental Protection Agency's EJScreen: Environmental Justice Screening and Mapping Tool.

In my analysis, I work with block group data that has been downloaded from the [EPA site](https://www.epa.gov/ejscreen/download-ejscreen-data). To understand the associated data columns, I explored the Technical Documentation and column description spreadsheet available via that same link. There are also [limitations and caveats](https://www.epa.gov/ejscreen/limitations-and-caveats-using-ejscreen) of the data, which you can read up on.

**Citation:**

United States Environmental Protection Agency (2023), EJScreen: Environmental Justice Screening and Mapping Tool [Data file] Available from: <https://www.epa.gov/ejscreen/download-ejscreen-data> Accessed December 15, 2023.

### HOLC grade data:

In my analysis, I use maps of HOLC grade designations for Los Angeles. These are from digitized maps and information from the HOLC that a team of researchers, led by the [Digital Scholarship Lab](https://dsl.richmond.edu/) at the University of Richmond, synthesized and made accessible as part of the [Mapping Inequality](https://dsl.richmond.edu/panorama/redlining/#loc=5/39.1/-94.58) project. - More information on this data can be found [here](https://dsl.richmond.edu/panorama/redlining/#loc=5/39.1/-94.58&text=downloads).

**Citation:**

Digital Scholarship Lab, Mapping Inequality. [Data File] Available from: <https://dsl.richmond.edu/> Accessed December 15, 2023.

### Bird observations/biodiversity data:

Another key part of my analysis is the bird biodiversity data. In my analysis, I work with Global Biodiversity Information Facility (GBIF) bird observation data from 2022. The [Global Biodiversity Information Facility](gbif.org) is the largest aggregator of biodiversity observations in the world. Observations typically include a location and date that a species was observed. - GBIF data available from <https://www.gbif.org/>

**Citation:**

Global Biodiversity Information Facility [Data File] Available from <https://www.gbif.org/> Accessed December 15, 2023.

## Repository Structure

``` bash
├── LICENSE
├── README.md
├── bird-biodiversity-holc.Rproj
├── data # too large for github, view Data or Sources for download info
│   ├── EJSCREEN_2023_BG_Columns.xlsx
│   ├── EJSCREEN_2023_BG_StatePct_with_AS_CNMI_GU_VI.gdb #GeoDataBase
│   ├── ejscreen-tech-doc-version-2-2.pdf
│   └── gbif-birds-LA
│       ├── gbif-birds-LA.dbf
│       ├── gbif-birds-LA.prj
│       ├── gbif-birds-LA.shp
│       └── gbif-birds-LA.shx
├── docs # analysis notebooks, html
│   ├── bird-biodiversity-holc-analysis.html
│   ├── bird-biodiversity-holc-analysis.qmd # primary analysis notebook
│   └── bird-biodiversity-holc-analysis_files
│       ├── figure-html
│       │   ├── bird_plot-1.png
│       │   ├── holc_plot-1.png
│       │   ├── la-crop-1.png
│       │   └── wastewater-plot-1.png
│       └── libs # css files etc. for Quarto (.qmd)
│           ├── bootstrap
│           ├── clipboard
│           └── quarto-html
└── figs # plots, figures used in notebook
    ├── bird_obs_plot.png
    └── spatial-relations-geocompxr.png
```

## Sources

Digital Scholarship Lab, Mapping Inequality. [Data File] Available from: <https://dsl.richmond.edu/> Access date: December 15, 2023.

Ellis-Soto, D., Chapman, M., & Locke, D. H. (2023). Historical redlining is associated with increasing geographical disparities in bird biodiversity sampling in the United States. Nature human behaviour, 7(11), 1869--1877. <https://doi.org/10.1038/s41562-023-01688-5> Accessed December 14, 2023.

Gee, G. C. (2008). A multilevel analysis of the relationship between institutional and individual racial discrimination and health status. American journal of public health, 98(Supplement_1), S48-S56.

Global Biodiversity Information Facility. [Data File] Available from <https://www.gbif.org/> Access date: December 15, 2023.

Hoffman, J. S., Shandas, V., & Pendleton, N. (2020). The effects of historical housing policies on resident exposure to intra-urban heat: a study of 108 US urban areas. Climate, 8(1), 12.

Nardone, A., Rudolph, K. E., Morello-Frosch, R., & Casey, J. A. (2021). Redlines and greenspace: the relationship between historical redlining and 2010 greenspace across the United States. Environmental health perspectives, 129(1), 017006.

United States Environmental Protection Agency (2023), EJScreen: Environmental Justice Screening and Mapping Tool [Data file] Available from: <https://www.epa.gov/ejscreen/download-ejscreen-data> Access date: December 15, 2023.
