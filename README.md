# Source-domain sensitivity priors for maize yield transfer

Research code supporting the manuscript **Source domain sensitivity priors for multisource maize yield prediction across regions and years** by Bai Haojun, Department of Geography, Faculty of Social Sciences, The University of Hong Kong.

The full mainline source tree is distributed as github_source_v1.0.0.zip in this repository. Download and unpack it before using the reproducibility commands below; the archive preserves all scientific module paths, entry points and configurations. Root-level files provide the license, citation metadata and data dictionary. Model weights, processed inputs and saved prediction banks are distributed separately. This code-only repository by itself does not contain the assets needed to reproduce numerical results. The full code/model and processed-data archive is published on Zenodo: [Version 1.0.0, DOI 10.5281/zenodo.23383068](https://doi.org/10.5281/zenodo.23383068). Download all seven data ZIPs and restore_large_file.py as described on the record page; one prediction bank is restored by byte concatenation with SHA-256 verification.

## License

The author's 64 code files listed in COVERED_FILES.csv are subject to LICENSE.txt: free noncommercial academic research, reproduction, modification and same-terms redistribution, with attribution and change notices. Commercial use requires prior written permission from u3685143@connect.hku.hk. Third-party material retains its own terms. This is source-available code under custom academic-use terms, not an OSI open-source license. Documentation and metadata are not automatically covered by the code license.

## Reproduction from archived assets

Install requirements-analysis.txt for the saved-result route. Place the matching data/model assets at their original relative paths so that outputs/, source_data/ and work/ align with this repository. Preserve each archive's own manifests separately. Then run from the repository root:

```sh
python scripts/reproduce_metrics.py
python scripts/draw_figures.py
```

The first command recalculates descriptive metrics from saved predictions; the second redraws Figs. 1–5 from saved tables and geometry. Neither fits a model or runs target inference. See DATA_DICTIONARY.md for array axes, units and file meanings. The matching full local candidate previously passed 1,173 metric-row checks and five pixel-identical figure checks in its preparation environment.

## Optional retraining

requirements-models.txt lists additional dependencies. scripts/train_mainline.py prints the expected processed input path and exits by default. Passing --execute starts a new experiment in runs/mainline/ and requires the separately supplied processed inputs. Training was not rerun during release preparation. The wrapper was syntax-checked and core imports were resolved; an end-to-end retraining claim is not made. Dependency lists and observed environment metadata are not a complete training lockfile.

## Interpretation and provenance

All manuscript target evaluations use frozen source models. Sensitivity indices and fusion weights describe model behavior and do not quantify physical or causal contributions. The inputs are retrospective with timestamp cutoffs and a fixed WorldCereal 2021 mask. CY-Bench observations and geometry were received as version 1.10, identified by archive checksums matching https://zenodo.org/records/17279151. Provider data conditions remain separate from this code license. See THIRD_PARTY_NOTICES.md.

## Citation and contact

Use CITATION.cff for software authorship metadata. The versioned mixed reproducibility archive is DOI 10.5281/zenodo.23383068 (dataset record); it is not a journal-article DOI. Contact: Bai Haojun, u3685143@connect.hku.hk.
