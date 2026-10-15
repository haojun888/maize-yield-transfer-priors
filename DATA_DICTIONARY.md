# Data dictionary

## Processed mainline input

work/maize_fusion_screen/gdd_evi.npz contains 17,303 county–year records. Load with numpy.load(..., allow_pickle=False).

| Key | Shape | Meaning |
|---|---|---|
| x | (17303, 23, 10) | Raw aligned dynamic values; missing values retained |
| static | (17303, 2) | Available water capacity and bulk density |
| lengths | (17303,) | Valid sequence lengths before terminal padding |
| y | (17303,) | Observed yield, t/ha |
| years | (17303,) | Harvest years |
| counties | (17303,) | County identifiers |

Dynamic variable order: tmin, tmax, tavg, precipitation, climatic water balance, radiation, NDVI, surface soil moisture, cumulative GDD, EVI. Group index sets are temperature [0,1,2], water [3,4,7], radiation [5], NDVI [6], GDD [8], EVI [9], and static soil. The fitted model receives source-imputed/normalized values and observation/validity masks according to the supplied preprocessing code and frozen JSON parameters.

Regional work/*/dataset.npz files use corresponding dynamic/static arrays and county–year labels. Additional keys are documented by their scientific preparation modules. These are prepared historical observations, not model-generated target predictions.

## Saved prediction banks

The usual keys are predictions, methods, seeds, y, counties, years, background, weather_only, and weather_calendar. Standard predictions have axes (seed, method, county–year). Some banks also store state identifiers, gate weights, or bins. Access method names through the methods array rather than assuming a fixed axis position. Additional random/budget schemes are retained where they support controls.

The information-intervention refit bank has axes (seed, arm, permutation repetition, method, county–year); arms and methods arrays define their order. Its bins use the earlier weather-plus-calendar definition. Equal sample count does not imply identical membership to a weather-only subset.

The main-transfer predictions.csv has one row per seed, method, protocol, scenario, and county–year. Only gdd_evi input rows are retained. Observed and predicted yields and the source background are in t/ha.

## Metrics and uncertainty

RMSE, MAE, and bias use yield units; R² uses the mean observed yield in the scored subset. NRMSE is 100 × RMSE divided by the same subset's mean observed yield. Background skill is 1 − model SSE/background SSE. Metrics are calculated by seed before averaging; predictions are not ensembled first. Seed SD is not a population confidence interval.

County-paired intervals are conditional on the fitted models. County resampling retains all selected county–year records. Core modules retain the experimental interval procedures; the quick-start verifies descriptive metrics only and does not claim to have recomputed every interval.
