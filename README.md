# PatchFlow 
## Short description
PatchFlow is a set of precalculated networks for simulating the metapopulation SEIR model at a global level. For the current version, using openly available datasets on population sizes [1] at the resolution of administrative regions (admin2 and admin3) [2], we construct country specific mobility networks based on a radiational model [3,4]. These networks are constructed to be compatible with open source metapopulation simulation engine, PatchSim [5].  

## Versions
|         |             |
| ------- | ----------- |
| 1.0  |  Initial release of the synthetic mobility networks calculated using radiation model based on GPW-GADM admin 1 and admin 2 level regions |

## Documentation
1. [Files description](docs/files_description.md)
2. [Methodology](docs/methodology.md)

## Relevant resources / literature
1. GPW, https://sedac.ciesin.columbia.edu/data/set/gpw-v4-admin-unit-center-points-population-estimates-rev11, used under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) license.
2. GADM, https://gadm.org/
3. Simini, F, et al. "A universal model for mobility and migration patterns." Nature 484.7392 (2012): 96-100
4. scikit-mobility, https://github.com/scikit-mobility/scikit-mobility, Pappalardo, L, et al. "scikit-mobility: a Python library for the analysis, generation and risk assessment of mobility data", 2019, https://arxiv.org/abs/1907.07062
5. PatchSim, https://github.com/NSSAC/patchsim, Venkatramanan S, et al. "Optimizing spatial allocation of seasonal influenza vaccine under temporal constraints"  PLoS Computational Biology, 2019 Sep 16;15(9):e1007111.
