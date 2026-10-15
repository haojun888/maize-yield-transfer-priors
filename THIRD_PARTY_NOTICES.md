# Third-party notices and exclusions

Prepared 15 October 2026 for the local JAG mainline candidate. This is not a license for the complete archive.

## CY-Bench

Data and benchmark provenance: WUR-AI/AgML-CY-Bench. The locally received Python/Git archive is under EUPL-1.2; its data-source conditions are separate. The original LICENSE is retained in CYBench_LICENSE_as_received.txt. The author's noncommercial terms do not supersede EUPL or restrict rights granted by upstream providers.

The candidate contains no detected direct `cybench` imports and no whole-function matches meeting the limited screen thresholds. These checks support review but do not establish exhaustive independent authorship. Coverage is based on the author's explicit ownership confirmation, with all third-party rights excluded. If adapted upstream code is subsequently identified, apply its actual terms and revise the coverage list before distribution.

Official license: https://github.com/WUR-AI/AgML-CY-Bench/blob/main/LICENSE

## Installed software dependencies

Dependencies are installed separately, not relicensed or bundled as the author's code: NumPy, pandas, Matplotlib, Pillow, PyTorch, SciPy, scikit-learn, joblib, rasterio, pyshp, certifi and affine, including their transitive dependencies. Preserve each installed distribution's own LICENSE/NOTICE. This document does not assign a single license to these packages or certify every possible environment.

## Data, boundaries and weights

See data_rights_inventory.csv. The code license excludes original observations, third-party-derived variables, boundary geometry and model weights. In particular, WISE30sec is CC BY 3.0; NASA's default data policy is not a basis to label all NASA products CC BY 4.0. Do not infer the license of legacy WorldCereal calendar data from a newer code repository.

## Publication status

No upload, public repository or public license grant has been made. The code-only coverage list can be used with an intentional release; the existing all-material candidate ZIP still requires the unresolved data and weights items to be resolved.

## Additional original calendar record verified

Cintas et al. (2022), https://doi.pangaea.de/10.1594/PANGAEA.946550, publishes the phase-I M1 SOS/EOS maps under CC BY-SA 4.0. This establishes the original record terms, not a byte-level match to the received CY-Bench county CSV. Preserve the distinction and applicable share-alike obligations; the author code license does not restrict these data.
