![Overview](https://github.com/user-attachments/assets/bba8f34c-9272-45e5-8299-18f055aae722)
UAV-based single-plant data extraction workflow

This repository provides a fully reproducible R-based workflow for extracting single-plant phenotypic traits from UAV imagery using orthomosaic data. The workflow is designed for multi-temporal, high-throughput phenotyping and supports the generation of AI-ready phenomic datasets at the individual plant level.

Overview of the experiment

Crop: Lettuce

Planting date: 29 January 2025

UAV phenotyping window: 26, 34, 41, 48, 51, and 54 days after planting (DAP)

Harvest date: 15 April 2025

Flight altitude: 30 m above ground level

UAV platform: DJI Mavic 3M Multispectral

UAV data were collected repeatedly across all flight dates within the high-throughput phenotyping window. Each flight represents a temporal snapshot of plant development, enabling longitudinal tracking of single plants throughout the growing season.

Sensor configuration

The DJI Mavic 3M Multispectral is equipped with:

One RGB camera for high-resolution true-color imagery

Four multispectral sensors (Green, Red, Red Edge, and Near-Infrared)

This configuration enables the extraction of both structural (RGB-based) and spectral (multispectral-based) phenotypic traits at the single-plant level.

Workflow description
1. Orthomosaic generation

RGB and multispectral images acquired at each flight date were processed into georeferenced orthomosaics. This step was applied consistently across all time points, ensuring temporal comparability of extracted traits.

2. Single-plant plot definition

Individual lettuce plants were delineated using polygon shapefiles, where each polygon corresponds to a single plant. The same plant-level geometries were used across all orthomosaics to enable multi-temporal tracking of individual plants.

3. Spatial alignment and masking

Shapefiles were aligned to the coordinate reference system (CRS) of each orthomosaic. Orthomosaics were cropped and masked to the experimental area to improve processing efficiency and spatial accuracy.

4. Soil removal and canopy isolation

Soil background was removed using color- and index-based masking approaches (e.g., HUE, RGB indices, and multispectral indices), resulting in isolated plant canopies suitable for quantitative analysis.

5. Trait extraction

Single-plant traits were extracted independently for each flight date, including:

Canopy pixel count and projected canopy area

RGB-derived color indices

Multispectral vegetation indices (e.g., NDVI, NDRE)

All traits were compiled into tabular datasets while preserving the temporal structure of the data.

6. Downstream analyses

The resulting multi-temporal and multi-band datasets were used for:

Statistical analysis of genotype-specific growth dynamics

Machine-learning and regression-based prediction models

Integration of RGB and multispectral features for AI-driven phenomic analyses

This design enables the generation of AI-ready, single-plant phenomic datasets suitable for advanced modeling approaches.

Reproducibility and openness

All image processing, masking, and trait extraction steps are implemented in open-source R scripts, primarily using the packages FIELDimageR, terra, and sf.
The complete, reproducible code used in this study—including multi-temporal and multispectral processing workflows—is provided in this GitHub repository.
