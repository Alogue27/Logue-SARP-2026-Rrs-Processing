# Investigating hyperspectral features of Pseudo-nitzschia blooms using NASA PACE observations
 SARP West Oceans 2026 group
<img align = "left" src="https://science.nasa.gov/wp-content/uploads/2023/11/sarp-patch.jpeg?w=1280&format=webp" alt="drawing" width="200"/>

(https://science.nasa.gov/earth-science/early-career-opportunities/student-airborne-research-program/).

Code Author: Alex Logue, Purdue University 
Contact information: aloguemiya@gmail.com

Graduate Student Mentor: Dorthy Sue Grimmer, Texas A&M University 

Faculty Mentor: Henry Houskeeper, Woods Hole Oceanagraphic Instution

## Abstract
Harmful Algal Blooms (HABS) occur due to excessive phytoplankton biomass or the presence of toxin-producing taxa and are a growing threat to coastal ecosystems. The diatom genus Pseudo-nitzschia (PN) can accumulate at high biomass and also produce a neurotoxin, Domoic Acid (DA), which has caused large animal mortality events along the California coast. PN detection presently relies on in situ sampling which is costly, labor-intensive, and offers limited spatial coverage. Remote sensing of HABS is a promising alternative, but has historically been limited by spectral resolution insufficient to distinguish phytoplankton at the taxonomic level required for HAB detection. NASA's recently launched Plankton, Aerosol, Cloud, ocean Ecosystem satellite (PACE) hosts the Ocean Color Instrument (OCI), providing hyperspectral resolution that may enable this distinction. This study uses reflectance and backscatter to identify optical signatures of PN. Cell count data from CalHABMAP at Scripps Pier identified PN bloom periods, and contemporaneous PACE OCI observations of apparent and inherent optical properties were evaluated to determine detection thresholds for PN. Remote sensing reflectance (Rrs) anomalies and backscatter spectra were obtained using the PACE data record. Backscatter is influenced by phytoplankton cell size, shape, and index of refraction, and the Quasi-Analytical Algorithm (QAA) was applied to derive spectral backscatter from Rrs rather than using the polynomial spectral shape invoked by PACE's standard backscatter retrieval. Spectral regions of focus were based on prior literature. Reflectance anomalies revealed a potentially useful feature near 550–600 nm, while backscatter spectra showed slight divergence near 630 nm between high and low abundance days. The results suggest backscatter may confer useful information for detecting PN, in agreement with prior work. Without in situ measurements to separate PN's spectral features from those of co-varying constituents like sediment and chlorophyll, differences in PACE-derived Rrs cannot be fully attributed to PN alone. Future work should investigate in situ backscatter spectra to test the robustness of inverting hyperspectral backscatter to improve PN detection compared to reflectance-or absorption-based remote sensing detection.

## About Code and Project
This code consists of 3 main notebooks. The first is a data loading one that downloads clipped granules for a series of dates and extracts PACE L2 Rrs, bb and L3 Chlorphyll variables. This note book also plots a transect line and selects 4 Lat/Lon coordinates and saves it to a CSV. All downstream notebooks rely on the outputs of this first notebook

The Second noebook generates an anomalous Rrs (aRrs) using a physat approach. A median Rrs value is generated from a no PN baseline for each selected chlorphyll bin. This value is then subtracted from the rest of the data to generate aRrs to view and intresting spectral shape fetures. 

The third notebook utilizes a Quasi analytical algorithm(QAA) approach to generate a backscatter spectrum from Rrs. This project uses code from @profxj repositories linked below. Specifically the ocpy and XQAA repositories 

https://github.com/ocean-colour
