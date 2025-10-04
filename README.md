# README for Astrophysics Data Analysis Project

## Overview

This repository contains solutions for two astrophysics data analysis questions based on simulated and observational astronomical datasets:

1. **Radial Metallicity Relation in a Simulated Galaxy**  
   Analysis of the radial variation of gas phase metallicity (oxygen abundance) in a Milky Way analogue simulated galaxy. This includes linear fitting of metallicity gradients, residual analysis, and 2D spatial metallicity mapping.

2. **Using ADQL to Search Bright Stars Around the Open Cluster Ruprecht 147**  
   Querying Gaia DR3 and crossmatching with 2MASS catalogs to identify and analyze bright stars (G < 14) within 1 degree of Ruprecht 147. Includes quality filtering, color-magnitude diagrams, and observational feasibility recommendations for a spectroscopic proposal.

***

## Project Structure

- `Q3.ipynb` — Jupyter Notebook for Question 3: Radial metallicity relation analysis  
- `Q2.ipynb` — Jupyter Notebook for Question 2: ADQL querying and CMD analysis for Ruprecht 147  
- `data/` — Folder containing input datasets (e.g., FITS files, CSVs) for local processing  
- `figures/` — Folder where generated plots and figures are saved (e.g., metallicity gradient plots, CMDs)  

***

## Details of Each Task

### Question 3: Radial Metallicity Relation

- Loads simulated gas particle data including 3D positions and oxygen abundance  
- Computes galactocentric radius (cylindrical) and analyses metallicity gradient as a function of radius  
- Fits a linear model to the radial metallicity relation with error estimation  
- Evaluates goodness of fit via residuals and root-mean-square error (RMSE)  
- Visualizes results in multiple panels: density plots, residuals, and spatial median metallicity maps in the xy-plane  
- Discusses physical interpretation of the metallicity gradient and observed residual patterns

### Question 2: ADQL Search and Analysis of Ruprecht 147

- Constructs and runs an ADQL query to Gaia DR3 to extract stars within 1 degree of Ruprecht 147 center (RA=289.074°, Dec=-16.323°) with Gaia G-band magnitude < 14  
- Crossmatches Gaia sources with 2MASS catalog to obtain near-infrared photometry (J, H, Ks bands)  
- Applies quality filters: excludes sources with bad 2MASS photometry (`ph_qual` ≠ 'AAA') and non-positive or missing Gaia parallaxes  
- Counts stars before and after cuts, reporting numbers for transparency  
- Creates two-panel figure showing:  
  - Gaia CMD (BP-RP color vs absolute G magnitude) using parallax distances  
  - 2MASS CMD (J-Ks color vs apparent H magnitude)  
- Saves figures with high quality (200 dpi) in `figures/`  
- Provides recommendation on observation feasibility with 2dF and HERMES based on available fiber allocations and bright star counts  

***

## Usage Instructions

1. Clone the repository:  
   ```
   https://github.com/rizwan-codes-boop/assignment3.git
   cd astrophysics-data-analysis
   ```
2. Install required Python packages if not already installed:  
   ```
   pip install numpy matplotlib astropy scipy astroquery pandas
   ```
3. Run the Jupyter notebooks to reproduce analysis and plots:  
   ```
   jupyter notebook Q2.ipynb
   jupyter notebook Q3.ipynb
   ```
4. Input data files should be placed in the `data/` folder as specified in each notebook.  
5. Output figures will be saved automatically to the `figures/` folder.  

***

## Notes and Improvements

- Quality cuts and their astrophysical motivations could be further documented for clarity.  
- CMD plots currently lack error bars; future updates could incorporate photometric uncertainties.  
- Crossmatching assumptions and handling of potential duplicates could be expanded for robustness.  
- Fiber allocation recommendations are general; deeper observational planning may be required for real proposals.  

***
