# hist_CF_inducedEQ

Investigation of historical cases of earthquakes (EQ) being induced at critical infrastructures, such as geothermal plants. Occurrence of a severe earthquake at the plant (during development or operational phase) can be categorised as a critical infrastructure failure (CF).

## Meta-analysis of induced seismicity at past geothermal fluid stimulation sites
Review of the underground seismic response to past underground stimulation projects aimed at creating, or enhancing, a geothermal reservoir. Induced earthquake hazard is characterised by the overall seismic activity a_fb that is normalised by the injected fluid volume V and the parameter b of the Gutenberg-Richter law.

* `data_geothermal_undergroundfeedback_v1.csv`: Dataset of seismic response parameters at 38 geothermal sites, believed to be a comprehensive review of geothermal fluid stimulations between 1977 and 2018. Corresponds to Table 1 of Mignan et al. (2021). Attributes: `ID`: stimulation identifier, `site`: site name, `V_m3`: total injected fluid volume in m3, `dV_LperSec`: mean injection rate in L/s, `N_above_m0`: number of earthquakes above m0, `m0`: minimum magnitude, `mmax`: maximum observed magnitude, `afb`: a-value of the Gutenberg-Richter law normalised by V (underground feedback), `b`: b-value of the Gutenberg-Richter law, `category`: data quality level for data mining, `comment_N`: if N for stimulation phase only, or including post-injection, `commnet_m0`: minimum observed magnitude or completeness magnitude mc. Details about data sources given in Appendix A of Mignan et al. (2021).

* `data_geothermal_undergroundfeedback_v1_dataminingresult.csv`: Same table as above but with a_fb calculated where missing, following the data mining approach of Mignan et al. (2021). Generated with the jupyter notebook. Additional attributes are `b_nogap`: b imputed by mean, `N_nogap`: N(m0) = 1 for `m0_nogap`: inferred from mmax, `afb_all`: afb estimated when missing (preferred value), `afb_corr`: afb corrected for potential ambiguity in the literature (for completeness but highly uncertain).

* `notebook_geothermal_undergroundfeedback.ipynb`: Data mining from the dataset of seismic response parameters `data_geothermal_undergroundfeedback_v1.csv` to expand the set of a_fb values, following the method of Mignan et al. (2021). Resulting table given in `data_geothermal_undergroundfeedback_v1_dataminingresult.csv`.

### References
Mignan A, Broccardo M, Wang Z (2021), Comprehensive Survey of Seismic Hazard at Geothermal Sites by a Meta-Analysis of the Underground Feedback Activation Parameter afb. Energies, 14, 7998, doi: [10.3390/en14237998](https://www.mdpi.com/1996-1073/14/23/7998)