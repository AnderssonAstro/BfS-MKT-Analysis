# BfS:MKT Analysis
 Analysis of citizen science data from BfS:MKT, as found in [Andersson et al. 2023](https://ui.adsabs.harvard.edu/abs/2023MNRAS.523.2219A/abstract), freely accessible in pre-print and from MNRAS.

If you use any of this data or code, please cite the paper and/or the following DOI:

[![DOI](https://zenodo.org/badge/529282129.svg)](https://zenodo.org/doi/10.5281/zenodo.10462687)


In this notebook you will find the main aggregation Jupyter notebook, which reduces some of the classification data and produces our main figures. Note that some information in the paper comes from other repos, namely [RISS19](https://github.com/PaulHancock/RISS19) and [Radio-Optical](https://github.com/4pisky/radio-optical-transients-plot) for Figures 5 and 7 respectively, and [MKT Source Matching](https://github.com/AstroLaura/MeerKAT_Source_Matching) for some counterpart searching.

**Data**

The _TraPData_ folder contains everything related to individual subjects (sources) as found by the [TraP](https://tkp.readthedocs.io/en/latest/). Namely:
- **Light curves of each of our 168 transient/variable sources** - you may want to test if any of these fit your expected model (e.g. power law decay)!
- Folders containing _all_ 8874 light curves used in this work, split up by field.
- All 381x2 figures analysed that passed a 0.4 vote fraction from volunteers, which produced our final sample of 168 variables/transients.
- Two folders ('Known' and 'Unknown') of these final 168 sources, split into the transients we knew about (XRBs, flare stars etc) and the newly detailed ones.
- TraP statistics on each of the 11 fields used in this work.
- Two .csv files with the RA,Dec of our 168 (used for crossmatching) and their file names (used when ssh-ing).

The _ProjectData_ folder contains information on the [BfS:MKT Zooniverse project](https://www.zooniverse.org/projects/alex-andersson/bursts-from-space-meerkat):
- In the _ReductionFiles_ folder there are details on the panoptes aggregation code in .yaml files (which workflow id, version and question labels)
- The original info on each subject
- Details of each iteration of the workflow (note that most of these were changed in building the final project. Only ID 19109 v16 was actually used in the first public launch.
- The reduced results for each subject (i.e. radio source) in terms of vote fractions. This is used in our main aggregation notebook to find our final sample of transients/variables. **Note that this file may be of use for researching into e.g. rates of extended AGN, how many artefacts we get, total source counts etc.** Do let me know if these data are of use to you!

The _MaserPlot_ folder contains a small notebook for producing Figure 8, using the GLIMPSE survey from Spitzer which is available on the [NASA/IPAC archive](https://irsa.ipac.caltech.edu/data/SPITZER/GLIMPSE/index_cutouts.html).

The _Figures_ folder contains all other Figures used in the paper.

Table2.csv is the table from the paper's appendix with key info on each of our 168 final candidates. Please use this to find more out about your favourite candidate transients/variables! This table is essentially a slimmed-down version of  the AggregatedCitizenTransients.csv and .xlsx, which have this info again, plus assorted TraP info, MeerLICHT data, subject metadata, notes from my classifications etc. The MeerLICHT data alone can be found in the ML_Magnitudes.csv file, and my 'expert labelling' of our 381 initial candidates is in 0.4TExpertLabels.csv

**Software**

Everything was run using Python3.8, but most other versions should be fine. If you have versioning issues, feel free to get in touch. Within Python we used the following packages:
- Pandas v1.2.4
- Numpy v1.19.5
- Astropy v4.2.1
- Matplotlib v3.3.4

Volunteer classifications were extracted and reduced using the standard [panoptes](https://aggregation-caesar.zooniverse.org/README.html) scripts; v1.1.3
