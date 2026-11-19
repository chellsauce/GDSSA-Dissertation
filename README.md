# The Geography of Crime in South West England
### Investigating Built-Environment and Socioeconomic Associations Using Spatial Regression

A spatial data science project examining the geographical distribution of recorded crime across South West England and its associations with built-environment and socioeconomic characteristics.

**Research area:** South West England, UK  
**Spatial unit:** Lower Layer Super Output Areas (LSOAs)  
**Study period:** 2025  
**Primary tools:** Python, GeoPandas, PySAL, Pandas, Matplotlib

---

## 1. Project Overview

Crime is not distributed evenly across geographical areas. Differences in the built environment, land use, accessibility and socioeconomic conditions may be associated with variations in crime patterns.

This project investigates the geography of recorded crime across South West England, exploring how built-environment characteristics and socioeconomic conditions are associated with crime density.

Using spatial data integration, exploratory spatial analysis and spatial regression techniques, the research examines geographical patterns and accounts for spatial dependence between neighbouring areas.

The analysis focuses on understanding these spatial relationships rather than establishing causal effects.

## 2. Research Objectives

The main objectives were to:

- Examine the geographical distribution and spatial patterns of recorded crime across South West England.
- Investigate associations between crime density and built-environment characteristics.
- Explore the relationship between socioeconomic conditions and crime density.
- Assess spatial autocorrelation and the implications of spatial dependence for regression modelling.
- Compare conventional regression with spatial regression approaches.

## 3. Study Area

The study covers South West England, using Lower Layer Super Output Areas (LSOAs) as the unit of spatial analysis.

The initial study area contained 3,407 LSOAs. One area (the Isles of Scilly) was excluded from the modelling dataset because of its incompatibility with the Queen contiguity spatial weights specification, resulting in 3,406 modelling units.

[Insert study area map here]

![Study area map](figures/study_area.png)

## 4. Data Sources and Variables

The analysis integrates crime, built-environment and socioeconomic datasets.

| Data category | Variables / indicators | Purpose |
|---|---|---|
| Recorded crime | Police-recorded crime data (2025) | Dependent variable |
| Built environment | Points of Interest (POI) categories | Represent local facilities and activities |
| Transport infrastructure | Intersection Density derived from OS MRN data | Represent road network characteristics |
| Land-use characteristics | ONS Spatial Signatures | Represent broader urban morphology characteristics |
| Socioeconomic conditions | IMD 2025 Income Rank | Represent income-related deprivation |
| Population characteristics | Population density | Control variable |

The crime dataset contained approximately 1.46 million records before aggregation and processing.

The dependent variable was constructed as crime density per square kilometre.

The Points of Interest dataset was organised into nine categories to represent different types of facilities and activities across the study area.

**Note:** The original datasets are not included in this repository unless their redistribution permissions explicitly allow it. Please refer to the original data providers for access.

## 5. Analytical Workflow

The project followed a series of data processing, spatial analysis and modelling stages.

### 5.1 Data Preparation and Integration

- Processed and cleaned recorded crime data.
- Prepared geographical datasets and harmonised spatial reference systems.
- Aggregated crime records to LSOA boundaries.
- Processed Points of Interest data into nine built-environment categories.
- Constructed road network intersection density indicators.
- Integrated socioeconomic and population characteristics.
- Prepared the final modelling dataset.

### 5.2 Exploratory Spatial Analysis

Exploratory analysis was conducted to understand the distribution of crime and explanatory variables across the study area.

This included:

- Mapping geographical variations in crime density.
- Examining the distribution of built-environment characteristics.
- Exploring socioeconomic patterns.
- Assessing global spatial autocorrelation using Moran's I.

[Insert crime density map here]

![Crime density map](figures/crime_density_map.png)

[Insert selected exploratory visualisation here]

![Exploratory analysis](figures/exploratory_analysis.png)

### 5.3 Spatial Regression Modelling

The modelling stage examined associations between crime density and the selected explanatory variables.

The analysis included:

- Ordinary Least Squares (OLS) regression as a baseline model.
- Spatial Error Model (SEM) to account for spatial dependence in the error structure.
- Queen contiguity spatial weights to represent neighbourhood relationships between LSOAs.
- Model comparison using goodness-of-fit and information criteria.
- Residual spatial autocorrelation assessment.

The modelling process also considered multicollinearity when selecting explanatory variables. For example, the Employment Deprivation Rank was excluded because of its strong correlation with the Income Deprivation Rank.

### 5.4 Model Diagnostics

Model diagnostics were used to assess the extent to which spatial dependence remained after regression modelling.

Global Moran's I was used to examine spatial autocorrelation in the model residuals, alongside comparisons of model performance.

[Insert model diagnostics figure here]

![Model diagnostics](figures/model_diagnostics.png)

## 6. Key Findings

The analysis identified substantial geographical variation in recorded crime density across South West England.

The built-environment analysis showed that different types of facilities and infrastructure were distributed unevenly across the study area. Commercial Services had the highest average density among the selected POI categories.

The spatial regression analysis highlighted the importance of accounting for spatial dependence when examining the relationships between crime density and its potential correlates.

**Selected model results:**

| Evaluation metric | Result |
|---|---:|
| OLS residual Moran's I | [Insert final value] |
| SEM residual Moran's I | [Insert final value] |
| SEM lambda | [Insert final value] |
| SEM AIC | [Insert final value] |

[Insert regression results visualisation here]

![Regression results](figures/regression_results.png)

*Note: Results describe statistical associations within the study area and should not be interpreted as evidence of causation.*

## 7. Tools and Technologies

| Category | Tools |
|---|---|
| Programming | Python |
| Data manipulation | Pandas, NumPy |
| Geospatial processing | GeoPandas |
| Spatial statistics | PySAL |
| Data visualisation | Matplotlib |
| Spatial analysis | Spatial weights, Moran's I, spatial regression |

## 8. Limitations


