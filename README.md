# powercurvePlot

> **This function now lives in the [`modelviz`](https://github.com/pablobernabeu/modelviz) package.**

Plotting power curves from the `simr` package. This standalone function has been
generalised, renamed and folded into **modelviz**, a unified, CRAN-grade package
for visualising statistical models and data.

The successor is **`power_curve_plot()`**, which:

* accepts either a `simr::powerCurve()` object **or** a plain data frame, so a
  (often slow) power simulation does not have to be re-run just to redraw,
* drops the `Cairo` dependency, and
* shares a consistent theme and palette with the rest of the package.

## Use it via modelviz

```r
# install.packages("remotes")
remotes::install_github("pablobernabeu/modelviz")

library(modelviz)

pc <- data.frame(
  nlevels = seq(10, 60, by = 10),
  mean  = c(0.18, 0.34, 0.52, 0.66, 0.79, 0.88),
  lower = c(0.10, 0.25, 0.42, 0.56, 0.70, 0.81),
  upper = c(0.28, 0.44, 0.62, 0.75, 0.86, 0.93)
)
power_curve_plot(pc, x_lab = "Number of participants")
```

See the [modelviz repository](https://github.com/pablobernabeu/modelviz) and
`vignette("model-estimates", package = "modelviz")` for details.

---

The original standalone script is preserved in this repository
(`powercurvePlot.R`) and in the git history for reference.
