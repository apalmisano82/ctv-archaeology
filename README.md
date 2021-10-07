CRAN Task View: Archaeological Science
---------------------------------

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><strong>Maintainer:</strong>
Ben Marwick</td>
<td align="left"><strong>Contact:</strong>
benmarwick at gmail.com</td>
<td align="left"><strong>Version:</strong>
2020-12-26</td>
</tr>
</tbody>
</table>

This CRAN Task View contains a list of packages useful for scientific work in Archaeology, grouped by topic. Note that this is not an official CRAN Task View, just one I have prepared for my own convenience, so it includes some packages only on GitHub and other non-CRAN resources I find useful. Many of the most highly recommended packages listed here can be installed in a single step by installing the [tidyverse](https://cran.r-project.org/package=tidyverse) package.

Besides these packages, a very wide variety of functions suitable for scientific work in Archaeology is provided by both the basic R system (and its set of recommended core packages), and a number of other packages on the Comprehensive R Archive Network (CRAN) and [GitHub](http://www.rdocumentation.org/packages?type=github). Consequently, several of the other CRAN Task Views may contain suitable packages, in particular the [Social Sciences](http://cran.rstudio.com/web/views/SocialSciences.html), [Spatial](http://cran.rstudio.com/web/views/Spatial.html),  [Spatio-temporal](http://cran.rstudio.com/web/views/SpatioTemporal.html), [Cluster analysis](http://cran.r-project.org/web/views/Cluster.html), [Multivariate Statistics](http://cran.r-project.org/web/views/Multivariate.html), [Bayesian inference](http://cran.r-project.org/web/views/Bayesian.html), [Visualization](http://cran.r-project.org/web/views/Graphics.html), and [Reproducible research](http://cran.r-project.org/web/views/ReproducibleResearch.html) Task Views. 

Contributions to this Task View are always welcome, and encouraged. The source file for this particular task view file resides in a GitHub repository (see below), and pull requests are the preferred method for contributions. 

**Data acquisition**

-  The ideal method is to export your spreadsheets from Excel (or whatever program you made them) as CSVs (comma-separated-values, a simple, non-proprietary plain-text-based format that is very transparent, being human-readable, easily machine-processable and suitable for archival storage) and read them into R using the base function `read.csv()`. Data in other types of plain text files can be read in with `read.table()`.
-  To read Microsoft Excel files into R there are a number of packages: [readxl]( https://github.com/hadley/readxl) (requires Rcpp, which in turn requires Rtools for Windows or XCode for OSX), [gdata](http://cran.rstudio.com/web/packages/gdata/index.html) (requires Perl), [openxlsx](http://cran.rstudio.com/web/packages/openxlsx/index.html) (requires Rcpp, which in turn requires Rtools for Windows or XCode for OSX), [XLConnect](http://cran.rstudio.com/web/packages/XLConnect/index.html) (requires [rJava](http://cran.rstudio.com/web/packages/rJava/index.html) and Java), [xlsx](http://cran.rstudio.com/web/packages/xlsx/index.html) (also requires rJava and Java). OpenDocument Spreadsheet files can be read into R using [readODS](http://cran.rstudio.com/web/packages/readODS/index.html). 
-  For working with untidy and/or complex Excel spreadsheets (i.e. many tables in one sheet, coloured cells, cells with formulas, etc.), use [jailbreakr](https://github.com/rsheets/jailbreakr), [xlsxtractr](https://github.com/hrbrmstr/xlsxtractr), [tidyxl](https://github.com/nacnudus/tidyxl) and [unpivotr](https://github.com/nacnudus/unpivotr)
-  Text data (as in sentences and paragraphs) can be read in and analysed with the [tm](http://cran.rstudio.com/web/packages/tm/index.html) package or [tidytext](https://cran.r-project.org/package=tidytext). If the text is in a Microsoft Word file, use [textreadr](https://CRAN.R-project.org/package=textreadr), or if it's a PDF file, use [pdftools](https://CRAN.R-project.org/package=pdftools). Text in image files can be extracted with [tesseract](https://cran.r-project.org/package=tesseract)
-   For quickly reading in a very large number of CSV files, or very large CSV files, use `fread()` from the [data.table](http://cran.rstudio.com/web/packages/data.table/index.html) package or functions in the [readr](https://github.com/hadley/readr) package. For plain text (CSV, TSV, etc) files that are too big to fit in memory, use [chunked](https://CRAN.R-project.org/package=chunked) to read and operate on them in small chunks.
-   [RODBC](http://cran.rstudio.com/web/packages/RODBC/index.html), [RMySQL](http://cran.rstudio.com/web/packages/RMySQL/index.html), [RPostgreSQL](http://cran.rstudio.com/web/packages/RPostgreSQL/index.html), [RSQLite](http://cran.rstudio.com/web/packages/RSQLite/index.html) for connecting R to SQL databases. [RODBC](http://cran.rstudio.com/web/packages/RODBC/index.html) can connect to Microsoft Access databases. 
-   The [haven](https://github.com/hadley/haven) and [foreign](http://cran.rstudio.com/web/packages/foreign/index.html) packages can be used for reading and writing files from certain versions of Minitab, S, SAS, SPSS, Stata, Systat and Weka. 
-   ESRI shapefiles can be read using [rgdal](http://cran.rstudio.com/web/packages/rgdal/index.html) or [maptools](http://cran.rstudio.com/web/packages/maptools/index.html)
- R can receive data directly from the web using [rvest](http://cran.rstudio.com/web/packages/rvest/index.html), [httr](http://cran.rstudio.com/web/packages/httr/index.html), [XML](http://cran.rstudio.com/web/packages/XML/index.html), [jsonlite](http://cran.rstudio.com/web/packages/jsonlite/index.html), [RSelenium](http://cran.r-project.org/web/packages/RSelenium/index.html) (requires Selenium 2.0 Remote WebDriver). R can be programmed to be a web-scraper using rvest and/or Rselenium. The [Web Technologies](http://cran.r-project.org/web/views/WebTechnologies.html) task view gives more details.
- Google spreadsheets can be read into R using the [googlesheets](https://github.com/jennybc/googlesheets) package
- Tables can be read directly from Microsoft Word documents with [docxtractr](https://cran.r-project.org/web/packages/docxtractr), and from PDF documents with [tabulizer](https://github.com/leeper/tabulizer)
- Datasets from the Open Context repository can be browsed and read into R using the [opencontext](https://github.com/ropensci/opencontext) package

**Data manipulation**

-   [dplyr](http://cran.rstudio.com/web/packages/dplyr/index.html) and [data.table](http://cran.rstudio.com/web/packages/data.table/index.html) for splitting the data up by groups, applying some common or custom functions, and combining the output back into a convenient form (ie. typical aggregation, splitting and summarising operations). Both packages are fast on very large datasets. 
- For cleaning, examining, and making quick summaries of data, [janitor](https://github.com/sfirke/janitor), [skimr](https://github.com/ropenscilabs/skimr), [statar](https://github.com/matthieugomez/statar), and [xda](https://github.com/ujjwalkarn/xda) maybe useful. [tabplot](https://github.com/mtennekes/tabplot/) has functions for exploratory data visualisation of tables
- [tidyr](http://cran.rstudio.com/web/packages/tidyr/index.html) for rearranging the data from long to wide forms, and more complex reshaping. 
- [purrr](http://cran.rstudio.com/web/packages/purrr/index.html) simplifies working with lists, applying functions to list elements and collecting the results
- [broom](http://cran.rstudio.com/web/packages/broom/index.html) takes the output of many built-in functions in R, such as `lm` or `t.test`, and turns them into tidy data frames.
- [measurements](https://cran.r-project.org/web/packages/measurements/), [convertr](https://github.com/ropenscilabs/convertr), and  [units](https://cran.r-project.org/web/packages/units) converts between metric and imperial units, or calculate a dimension's unknown value from other dimensions' measurements.

**Visualising data**

- [ggplot2](http://cran.rstudio.com/web/packages/ggplot2/index.html) produces a very wide variety of attractive plots with a highly flexible and logical syntax. 
-    Extensions include [ggbiplot](https://github.com/vqv/ggbiplot) (PCA biplots with ellipses),  [GGally](http://cran.r-project.org/web/packages/GGally/index.html) (plot matrices), [ggtern](http://www.ggtern.com/) (ternary plots), [ggfortify](https://github.com/sinhrks/ggfortify) (many methods for plotting PCA, clustering, linear model output, etc., using ggplot2),[ggalt](https://github.com/hrbrmstr/ggalt) (more geoms, coords, stats, scales and fonts, including splines, 1d and 2d densities), [waffle](https://github.com/hrbrmstr/waffle) (for square pie charts), [ggraph](https://github.com/thomasp85/ggraph) for treemaps, [ggfan](https://CRAN.R-project.org/package=ggfan) for fanplots, [tidybayes](https://github.com/mjskay/tidybayes) for plotting output of Bayesian analysis, [ggridges](https://CRAN.R-project.org/package=ggridges) for ridge plots, [ggalt](https://CRAN.R-project.org/package=ggalt) for many additional geoms, [ggrepel](https://github.com/slowkow/ggrepel) for moving overlapping text labels away from each other, and [shadowtext](https://cran.r-project.org/web/packages/shadowtext/) for a halo around text to make it more readable on busy plots.
-    For showing distributions across several categories: [ggforce](https://CRAN.R-project.org/package=ggforce), [ggbeeswarm](https://github.com/eclarke/ggbeeswarm), [vipor](https://github.com/sherrillmix/vipor), [sinaplot](https://cran.r-project.org/web/packages/sinaplot)
-    For isolines and isobands use [ggisoband](https://github.com/clauswilke/ggisoband)
-    [plotly](https://github.com/ropensci/plotly) and [ggiraph](https://github.com/davidgohel/ggiraph) make ggplots interactive with mouse-over pop-ups, zooming, click-actions, etc. [scatterD3](https://github.com/juba/scatterD3) makes highly interactive scatter plots
-    [circlize](https://cran.r-project.org/web/packages/circlize/index.html) implements Circos in R for circular and chord plots. Rose plots can be made with [ggplot2](http://cran.rstudio.com/web/packages/ggplot2/index.html), Schmidt diagrams can be made with the `net` function in [RFOC](https://cran.r-project.org/web/packages/RFOC) or the `Stereo*` functions in [RockFab](https://cran.r-project.org/web/packages/RockFab/)
-   [plotrix](http://cran.rstudio.com/web/packages/plotrix/index.html) has the function `battleship.plot()` to make Ford's battleship diagrams. 
-   [ggmap](http://cran.rstudio.com/web/packages/ggmap/index.html) combines the spatial information of static maps from Google Maps, OpenStreetMap, Stamen Maps or CloudMade Maps with the layered grammar of graphics implementation of ggplot2
-    Stratigraphic data plots can be drawn using [tidypaleo](https://github.com/paleolimbot/tidypaleo), the `Stratiplot()` function in [analogue](http://cran.rstudio.com/web/packages/analogue/index.html) and functions `strat.plot()` and strat.plot.simple in the [rioja](http://cran.rstudio.com/web/packages/rioja/index.html) package. The rioja package also includes `chclust()` for stratigraphically constrained clustering, and related dendrogram plotting methods.
-    [rgl](http://cran.rstudio.com/web/packages/rgl/index.html) and [plotly](https://github.com/ropensci/plotly) for interactive 3D plots, and [scatterplot3d](http://cran.rstudio.com/web/packages/scatterplot3d/index.html) also draws 3D point clouds.
-   [tabplot](https://github.com/mtennekes/tabplot/) for exploratory data visualisation of tables
-   For schematic diagrams, such as Harris matrices, [DiagrammeR](https://github.com/rich-iannone/DiagrammeR) is useful.
-   For colour schemes in plots: [viridis](https://github.com/sjmgarnier/viridis) for perfectly perceptually-uniform colours, [RColorBrewer](http://cran.r-project.org/web/packages/RColorBrewer/index.html), [wesanderson](http://cran.r-project.org/web/packages/wesanderson/index.html), and [munsell](http://cran.r-project.org/web/packages/munsell/index.html) for exploring and using the Munsell colour system, and for some extra themes for ggplot2, including some Tufte-inspired themes, see [ggthemes](http://cran.r-project.org/web/packages/ggthemes/index.html). 

**Multi-panel plot layouts**

- To combine and align multiple ggplot2 plots (and other image types) in one panel:
- use [cowplot](https://cran.r-project.org/web/packages/cowplot/index.html) for a publication-ready theming and labelling
- [patchwork](https://github.com/thomasp85/patchwork) for a simple grammar using `+`, `/`, etc
- [gridExtra](http://cran.rstudio.com/web/packages/gridExtra/index.html) for configuring layouts with a matrix
- [egg](https://CRAN.R-project.org/package=egg)
- [multipanelfigure](https://CRAN.R-project.org/package=multipanelfigure), perhaps the most versatile for combining different elements

**Analysis in general**

-    Base R, especially the stats package, has a lot of functionality useful for analysing archaeological data. For example, `chisq.test()`, `prop.test()`, `binom.test()`, `t.test()`, `wilcox.test()`, `kruskal.test()`, `mcnemar.test()`, `cor.test()`, `power.t.test()`, `power.prop.test()`, `power.anova.test()` among many others. [Hmisc](http://cran.r-project.org/web/packages/Hmisc/index.html) includes bootstrapping, setting confidence intervals, and power analysis functions, see also [psych](http://cran.r-project.org/web/packages/psych/index.html) for useful descriptive statistics and visualizations.
-    [corrr](https://cran.rstudio.com/web/packages/corrr/) contains many convenient functions for exploring correlations.
-    Bayesian and resampling variants of these also exist, for example in the [MCMCpack](http://cran.r-project.org/web/packages/MCMCpack/index.html), [BEST](http://cran.r-project.org/web/packages/BEST/index.html) (requires JAGS), [Bayesian First Aid](https://github.com/rasmusab/bayesian_first_aid) (also requires JAGS) packages (see the [Bayesian](http://cran.r-project.org/web/views/Bayesian.html) task view for more) and the [coin](http://cran.rstudio.com/web/packages/coin/index.html), [boot](http://cran.r-project.org/web/packages/boot/index.html), and [bootstrap](http://cran.r-project.org/web/packages/bootstrap/index.html) packages (see also [msm](http://cran.r-project.org/web/packages/msm/index.html)).
-    For analysing change over time, [bcp](http://cran.r-project.org/web/packages/bcp/index.html), [changepoint](http://cran.r-project.org/web/packages/changepoint/index.html), [ecp](http://cran.r-project.org/web/packages/ecp/index.html), [AnomalyDetection](https://github.com/twitter/AnomalyDetection) and [BreakoutDetection](https://github.com/twitter/BreakoutDetection) provide functions for detecting distributional changes within time-ordered observations.
-    [abc](http://cran.r-project.org/web/packages/abc/index.html) provides functions for parameter estimation, model selection, and goodness-of-fit.

**Analysis of categorical and count data**

- The `table()` function in the base package and the `xtabs()` and `ftable()` functions in the stats package construct contingency tables.
- The `chisq.test()` and `fisher.test()` functions in the stats package may be used to test for independence in two-way contingency tables
- The `assocstats()` function in the vcd package computes the Pearson chi-Squared test, the Likelihood Ratio chi-Squared test, the phi coefficient, the contingency coefficient and Cramer's V for plain or stratified contingency tables.

**Linear, generalized linear models, and non-linear models**

-  Linear models can be fitted (via OLS) with `lm()` (from stats). The [modelr](https://github.com/hadley/modelr) package has helper functions for pipeable modelling (e.g. cross-validation, bootstrapping). For data from a non-normal population, or when there are apparent outliers, [lmPerm](https://cran.r-project.org/web/packages/lmPerm) computes linear models using permutation tests.
-  Bayesian fitting of linear and non-linear models is possible with [rstanarm](https://cran.r-project.org/web/packages/rstanarm),  [brms](https://github.com/paul-buerkner/brms), and [rethinking](https://github.com/rmcelreath/rethinking).
-  The `nls()` function (from stats) as well as the package [minpack.lm](http://cran.rstudio.com/web/packages/minpack.lm/index.html) allow the solution of nonlinear least squares problems.
- Correlated and/or unequal variances can be modeled using the `gnls()` function of the [nlme](http://cran.rstudio.com/web/packages/nlme/index.html) package and by [nlreg](http://cran.rstudio.com/web/packages/nlreg/index.html). The nlme package is supported by Pinheiro & Bates (2000) Mixed-effects Models in S and S-PLUS, Springer, New York. 
-  The generic `anova()` function in the [stats](http://cran.rstudio.com/web/packages/stats/index.html) package constructs sequential analysis of variance and analysis of deviance tables, and can compute F and likelihood-ratio tests for nested models. (It is typical for other classes of statistical models in R to have anova methods as well.) The generic anova function in the [car](http://cran.rstudio.com/web/packages/car/index.html) package (associated with Fox, An R and S-PLUS Companion to Applied Regression, Sage, 2002) constructs so-called "Type-II" and "Type-III" tests for linear and generalized linear models.
- [cerUB](https://github.com/Andros-Spica/cerUB) for multivariate statistic protocols for integrating archaeometric data (geochemical, mineralogical, petrographic)

**Multivariate statistics**

-   The [Cluster task view](http://cran.r-project.org/web/views/Cluster.html) provides a more detailed discussion of available cluster analysis methods and appropriate R functions and packages.
-  [caret](http://cran.rstudio.com/web/packages/caret/index.html) and [FactoMiner](http://cran.rstudio.com/web/packages/FactoMiner/index.html) are popular packages with a suite of multivariate methods
- [aplpack](http://cran.rstudio.com/web/packages/aplpack/index.html) provides `bagplots()`
- `lda()` and `qda()` within [MASS](http://cran.rstudio.com/web/packages/MASS/index.html) provide linear and quadratic discrimination respectively.

Model Testing and Validation

- [caret](http://cran.rstudio.com/web/packages/caret/index.html) provides many functions for model training, testing, and validation. There is also Max Kuhn's excellent companion book called "Applied Predictive Modeling" (Springer, also available as an ebook). The [mlr](http://cran.r-project.org/web/packages/mlr/index.html) package also provides classification, regression, and machine learning methods. 
-  Other packages that enable tuning and evaluation of models include bootstrap and [Hmisc](http://cran.rstudio.com/web/packages/Hmisc/index.html)
- The [CVtools](http://cran.rstudio.com/web/packages/CVtools/index.html) and [DAAG](http://cran.rstudio.com/web/packages/DAAD/index.html) packages include cross-validation functions for evaluating the optimality of tuning parameters such as sample sizes or number of predictors etc., in statistical models 
- [rsample](https://CRAN.R-project.org/package=rsample) creates different types of resamples and corresponding classes for their analysis

Hierarchical cluster analysis

-    The package [cluster](http://cran.rstudio.com/web/packages/cluster/index.html) provides functions for cluster analysis following the methods described in Kaufman and Rousseeuw (1990) Finding Groups in data: an introduction to cluster analysis, Wiley, New York
-    There are also `hclust()` in the stats package and `hcluster()` in [amap](http://cran.rstudio.com/web/packages/amap/index.html)
-    [pvclust](http://cran.rstudio.com/web/packages/pvclust/index.html) is a package for assessing the uncertainty in hierarchical cluster analysis. It provides approximately unbiased p-values as well as bootstrap p-values. Enhanced plotting is also available through the [dendextend](http://cran.rstudio.com/web/packages/dendextend/index.html) package.
-    [dendextend](http://cran.rstudio.com/web/packages/dendextend/index.html) Offers a set of functions for extending dendrogram objects in R. It allows to both adjust a tree's graphical parameters - the color, size, type, etc of its branches, nodes and labels - as well as visually (and statistically) compare different dendrograms to one another.

Other partitioning methods

-   `kmeans()` in stats provides k-means clustering and cmeans() in [e1071](http://cran.rstudio.com/web/packages/e1071/index.html) implements a fuzzy version of the k-means algorithm. The recommended package [cluster](http://cran.rstudio.com/web/packages/cluster/index.html) also provides functions for various partitioning methodologies.
-    To compute the optimum number of clusters there is the `pamk()` function in the [fpc](http://cran.rstudio.com/web/packages/fpc/index.html) package, `cascadeKM()` in [vegan](http://cran.rstudio.com/web/packages/vegan/index.html), `Mclust()` in [mclust](http://cran.rstudio.com/web/packages/mclust/index.html), `apcluster()` in [apcluster](http://cran.rstudio.com/web/packages/apcluster/index.html)
- Self-organising maps can be produced with the [kohonen](https://CRAN.R-project.org/package=kohonen)

Mixture models and model-based cluster analysis

-    [mclust](http://cran.rstudio.com/web/packages/mclust/index.html) and [flexmix](http://cran.rstudio.com/web/packages/flexmix/index.html) provide implementations of model-based cluster analysis.

Principle components and other projection, scaling, and ordination methods

-  Principal Components (PCA) is available via the `prcomp()` function (based on svd),  `rda()` (in package [vegan](http://cran.rstudio.com/web/packages/vegan/index.html)), `pca()` (in package [labdsv](http://cran.rstudio.com/web/packages/labdsc/index.html)) and `dudi.pca()` (in package [ade4](http://cran.rstudio.com/web/packages/ade4/index.html)), provide more ecologically-orientated implementations. Plotting of PCA output is available in [ggbiplot](https://github.com/vqv/ggbiplot) and [ggfortify](https://github.com/sinhrks/ggfortify). 
-   Redundancy Analysis (RDA) is available via `rda()` in vegan and `pcaiv()` in ade4. 
-   Canonical Correspondence Analysis (CCA) is implemented in `cca()` in both vegan and ade4. 
-   Detrended Correspondence Analysis (DCA) is implemented in `decorana()` in vegan. 
-   Principal coordinates analysis (PCO) is implemented in `dudi.pco()` in ade4, `pco()` in labdsv, `pco()` in [ecodist](http://cran.rstudio.com/web/packages/ecodist/index.html), and `cmdscale()` in package [MASS](http://cran.rstudio.com/web/packages/MASS/index.html).
-    Non-Metric multi-Dimensional Scaling (NMDS) is provided by `isoMDS()` in package MASS and `nmds()` in [ecodist](http://cran.rstudio.com/web/packages/ecodist/index.html). `nmds()`, a wrapper function for `isoMDS()`, is also provided by package [labdsv](http://cran.rstudio.com/web/packages/labdsv/index.html). vegan provides helper function `metaMDS()` for `isoMDS()`, implementing random starts of the algorithm and standardised scaling of the NMDS results. The approach adopted by vegan with `metaMDS()` is the recommended approach for ecological data.
- `corresp()` and `mca()` in MASS provide simple and multiple correspondence analysis respectively. [ca](http://cran.rstudio.com/web/packages/ca/index.html) also provides single, multiple and joint correspondence analysis. `ca()` and `mca()` in ade4 provide correspondence and multiple correspondence analysis respectively, as well as adding homogeneous table analysis with `hta()`. Further functionality is also available within vegan co-correspondence is available from cocorresp. [FactoMineR](http://cran.rstudio.com/web/packages/FactoMineR/index.html) provides `CA()` and `MCA()` which also enable simple and multiple correspondence analysis as well as associated graphical routines. [CAinterprTools](https://github.com/gianmarcoalberti/CAinterprTools) has functions for correspondence analysis and diagnostics. 
-    Seriation methods are available in [seriation](http://cran.rstudio.com/web/packages/seriation/index.html), which includes `bertinplot()` for producing battleship plots, and [CAseriation](https://github.com/gianmarcoalberti/CAseriation) which also has a battleship plotting function. 
-    [tabula](https://github.com/nfrerebeau/tabula) provides methods to analyse and visualise archaeological count data (artifacts, faunal remains, etc.) using diversity measures and Ford (1962) and Bertin (1977) diagrams.

Dissimilarity coefficients

- `dist()` in standard package stats, `daisy()` in recommended package [cluster](http://cran.rstudio.com/web/packages/cluster/index.html), `vegdist()` in [vegan](http://cran.rstudio.com/web/packages/vegan/index.html), `dsvdis()` in [labdsv](http://cran.rstudio.com/web/packages/labdsv/index.html), `Dist()` in [amap](http://cran.rstudio.com/web/packages/amap/index.html), `distance()` in [ecodist](http://cran.rstudio.com/web/packages/ecodist/index.html), a suite of functions in [ade4](http://cran.rstudio.com/web/packages/ade4/index.html), and [rdist](http://cran.rstudio.com/web/packages/rdist/index.html) for very fast distance computations. 
- [simba](http://cran.rstudio.com/web/packages/simba/index.html) provides functions for the calculation of similarity and multiple plot similarity measures with binary data (for instance presence/absence data)
- `distance()` in the [analogue](http://cran.rstudio.com/web/packages/analogue/index.html) package can be used to calculate dissimilarity between samples of one matrix and those of a second matrix. The same function can be used to produce pair-wise dissimilarity matrices, though the other functions listed above are faster. `distance()` can also be used to generate matrices based on Gower's coefficient for mixed data (mixtures of binary, ordinal/nominal and continuous variables). Function `daisy()` in package [cluster](http://cran.rstudio.com/web/packages/cluster/index.html) provides a faster implementation of Gower's coefficient for mixed-mode data than `distance()` if a standard dissimilarity matrix is required. Function `gowdis()` in package [FD](http://cran.rstudio.com/web/packages/FD/index.html) also computes Gower's coefficient and implements extensions to ordinal variables.
- [DistatisR](http://cran.rstudio.com/web/packages/DistatisR/index.html) provides functions for three-way multidimensional scaling for the analysis of multiple distance/covariance matrices collected on the same set of observations.
- Simple and partial Mantel tests to compute the Mantel statistic as a matrix correlation between two dissimilarity matrices are available in [vegan](http://cran.rstudio.com/web/packages/vegan/index.html) and [ecodist](http://cran.rstudio.com/web/packages/ecodist/index.html)


**Making maps and using R as a Geographical Information System**

- Making maps: [ggspatial](http://cran.rstudio.com/web/packages/ggspatial/index.html) for easy plotting of most kinds of spatial data, see also: [maps](http://cran.rstudio.com/web/packages/maps/index.html), [rworldmap](http://cran.rstudio.com/web/packages/rworldmap/index.html), [mapdata](http://cran.rstudio.com/web/packages/mapdata/index.html), [maptools](http://cran.rstudio.com/web/packages/maptools/index.html), [mapproj](http://cran.rstudio.com/web/packages/mapproj/index.html),[mapsf](http://cran.r-project.org/web/packages/mapsf/index.html), [ggplot2](http://cran.rstudio.com/web/packages/ggplot2/index.html), [ggmap](http://cran.rstudio.com/web/packages/ggmap/index.html), [RgoogleMaps](http://cran.rstudio.com/web/packages/RgoogleMaps/index.html), [cartography](http://cran.rstudio.com/web/packages/cartography/index.html) [RColorBrewer](http://cran.rstudio.com/web/packages/RColorBrewer/index.html) 
- Scale bars and North arrows can be added to maps made with ggplot and ggmap using [GISTools](https://cran.r-project.org/web/packages/GISTools), [ggsn](https://github.com/oswaldosantos/ggsn) or [legendMap](https://github.com/3wen/legendMap). 
- Interactive mapping of spatial objects with zooming and panning is possible with [leaflet](https://cran.rstudio.com/web/packages/leaflet/index.html) and geo[mapview](http://cran.rstudio.com/web/packages/mapview/index.html)
- To interactively create and edit spatial objects (points, lines, polygons), use [mapedit](https://cran.r-project.org/package=mapedit), and to smooth drawn polygons, use [smoothr](https://cran.r-project.org/package=smoothr)
-   R has many packages that enable it to be used as a GIS for spatial analysis: [sf](http://cran.rstudio.com/web/packages/sf/index.html), [sp](http://cran.rstudio.com/web/packages/sp/index.html), [raster](http://cran.rstudio.com/web/packages/raster/index.html), [rasterVis](http://cran.rstudio.com/web/packages/rasterVis/index.html), [shapefiles](http://cran.rstudio.com/web/packages/shapefiles/index.html), [spatial](http://cran.rstudio.com/web/packages/spatial/index.html), [spatstat](http://cran.rstudio.com/web/packages/spatstat/index.html), [splancs](http://cran.rstudio.com/web/packages/splancs/index.html), [ipdw](http://cran.rstudio.com/web/packages/ipdw/index.html), [geoR](http://cran.rstudio.com/web/packages/geoR/index.html),  [argosfilter](http://cran.rstudio.com/web/packages/argosfilter/index.html), [ads](http://cran.rstudio.com/web/packages/ads/index.html), [spdep](http://cran.rstudio.com/web/packages/spdep/index.html), [gstat](http://cran.rstudio.com/web/packages/gstat/index.html), [GISTools](http://cran.rstudio.com/web/packages/GISTools/index.html)
-   [spgrass6](http://cran.rstudio.com/web/packages/spgrass6/index.html) and [rgrass7](http://cran.rstudio.com/web/packages/rgrass7/index.html) provides facilities for using all [GRASS](http://grass.osgeo.org/) geographical information system commands from the R command line. [RQGIS](https://github.com/jannes-m/RQGIS) establishes an interface between R and QGIS, i.e. it allows the user to access QGIS functionalities from within R.
-   [spdply](https://cran.r-project.org/web/packages/spdplyr) provides methods for dplyr verbs for 'sp' and 'Spatial' class objects.
-   [rgdal](http://cran.rstudio.com/web/packages/rgdal/index.html) uses the GDAL (Geospatial Data Abstraction Library) (raster) and OGR (vector) data I/O library, as well as PROJ.4 for CRS (coordinate reference systems) (re)projections
-   [rgeos](http://cran.rstudio.com/web/packages/rgeos/index.html) uses the GEOS (Geometry Open Source) library, which powers PostGIS: does the 'usual' geometry operations for features
-   The [Spatial](http://cran.r-project.org/web/views/Spatial.html) and [Spatio Temporal](http://cran.r-project.org/web/views/SpatioTemporal.html) task views have more details. 
-  [recexcavAAR](https://cran.r-project.org/web/packages/recexcavAAR/index.html) 3D Reconstruction of Archaeological Excavations
- [SiteExploitationTerritories](https://github.com/eScienceCenter/SiteExploitationTerritories) implements the Tobler Hiking Function for spatial time-cost analysis of rasters 
- [klrfome](https://github.com/mrecos/klrfome) provides functions to model a single scalar outcome (e.g. presence/absence of an archaeological site) to a distribution of features (such as landscape and environmental variables).

**Environmental & geological analysis**

-    Transfer function models including weighted averaging (WA), modern analogue technique (MAT), Locally-weighted WA, & maximum likelihood (aka Gaussian logistic) regression (GLR) are provided by [analogue](http://cran.rstudio.com/web/packages/analogue/index.html), [vegan](http://cran.rstudio.com/web/packages/vegan/index.html), and [rioja](http://cran.rstudio.com/web/packages/rioja/index.html) for stratigraphic analyses
-   [G2Sd](http://cran.rstudio.com/web/packages/G2Sd/index.html) gives full descriptive statistics and a physical description of sediments based on grain-size distributions, [soiltexture](http://cran.rstudio.com/web/packages/soiltexture/index.html) and [ggtern](http://cran.rstudio.com/web/packages/ggtern/index.html) for ternary plots of soil texture
-    Constrained clustering of stratigraphic data is provided by function `chclust()` in the form of constrained hierarchical clustering in [rioja](http://cran.rstudio.com/web/packages/rioja/index.html).
-    Stratigraphic columns can be plotted and analysed with the the [SDAR](http://run.unl.pt/bitstream/10362/14554/1/TGEO0128.pdf) package. 
-    Benn diagrams can be drawn with [plotrix](http://cran.rstudio.com/web/packages/plotrix/index.html) and Woodcock diagrams with [RFOC](http://cran.rstudio.com/web/packages/RFOC/index.html).
- Function for circular statistics such as the Rayleigh test and many others, can be found in [CircStats](https://cran.r-project.org/web/packages/CircStats/index.html), [RFOC](https://cran.rstudio.com/web/packages/RFOC/index.html), [circular](https://cran.rstudio.com/web/packages/circular/index.html), [Directional](https://cran.r-project.org/web/packages/Directional/), and [heR.Misc](http://exposurescience.org/hosted-projects/inhalation-exposure-simulation-modeling-project/the-her-software-project)
- The [siar](http://cran.rstudio.com/web/packages/siar/index.html) package takes data on organism isotopes and fits a Bayesian model to their dietary habits based upon a Gaussian likelihood with a mixture dirichlet-distributed prior on the mean
-    The [zooaRch](http://cran.r-project.org/web/packages/zooaRch/) package has functions for survival analysis of zooarchaeological datasets
-    Functions for tree ring analysis can be found in [dplR](http://cran.rstudio.com/web/packages/dplR/index.html)
- [Orientations](https://github.com/surf3s/Orientations)for doing fabric analysis. Initially intended for use with total station coordinate data (two XYZ points on the long axis of an object) but bearing and plunge data can be transformed into the appropriate format for use here (see McPherron 2018).
- See the [Environmetrics](http://cran.r-project.org/web/views/Environmetrics.html) task view for more.

**Dating**
-    Radiocarbon dates can be calibrated using [Bchron](http://cran.rstudio.com/web/packages/Bchron/index.html) with various calibration curves (including user generated ones); also does Age-depth modelling, relative sea level rate estimation incorporating time uncertainty in polynomial regression models; and non-parametric phase modelling via Gaussian mixtures as a means to determine the activity of a site (and as an alternative to the Oxcal function SUM). 
-    [rcarbon](https://github.com/ahb108/rcarbon) for basic calibration, modelling, hypothesis testing
-    Bayesian age-depth modelling of radiocarbon dates is also available in [Bacon](http://chrono.qub.ac.uk/blaauw/bacon.html), and [clam](http://chrono.qub.ac.uk/blaauw/) contains functions for "classical", non-Bayesian age-depth modelling. These are not R packages, but [clam](https://github.com/SimonGoring/clam) has been packaged for easy use.
-    [c14bazAAR](https://cran.r-project.org/web/packages/c14bazAAR/index.html) for the retrieval and preparation of large radiocarbon datasets.
-    The [oxcAAR](https://github.com/ISAAKiel/oxcAAR) package allows you to use R to connect to a local installation of the OxCal software to calibrate radiocarbon dates and a variety of other OxCal operations. 
- [ArchaeoPhases](https://cran.r-project.org/package=ArchaeoPhases) provides statistical tools to analyze and to estimate archaeological phases from the posterior distribution (i.e. MCMC samples) of a sequence of dates. Includes testing procedures to check the presence of a gap between two successive phases or periods.
-    Various R functions for Luminescence Dating data analysis are in the [Luminescence](http://cran.rstudio.com/web/packages/Luminescence/index.html) package (including radial plotting) and in the [numOSL](https://cran.r-project.org/web/packages/numOSL/index.html) package, including equivalent dose calculation, annual dose rate determination, growth curve fitting, decay curve decomposition, statistical age model optimization, and statistical plot visualization.
-    The [archSeries](https://github.com/davidcorton/archSeries) makes chronologies from information from multiple entities with varying chronological resolution and overlapping date ranges
-    The [ADMUR](https://github.com/UCL/ADMUR) package provides tools to directly model underlying population dynamics using chronological datasets (radiocarbon and other) with a variety of models, including Continuous Piecewise Linear (CPL) model framework, and model comparison framework using BIC.
- For time series analysis using calendar dates, [zoo](https://cran.r-project.org/package=zoo) and [padr](https://cran.r-project.org/package=padr) are useful.
- [SPARTAAS](https://CRAN.R-project.org/package=SPARTAAS) Statistical pattern recognition and dating using archaeological artefacts assemblages. 
 

**Evolution, phylogenetics, morphometrics, and shape analysis**

-  The [Phylogenetics task view](http://cran.r-project.org/web/views/Phylogenetics.html) provides more detailed coverage of the subject area and related functions within R. 
-  Packages specifically tailored for the analysis of phylogenetic and evolutionary data include: [ape](http://cran.rstudio.com/web/packages/ape/index.html), [phytools](http://cran.rstudio.com/web/packages/phytools/index.html), [phangorn](http://cran.rstudio.com/web/packages/phangorn/index.html), [Rphylip](http://cran.rstudio.com/web/packages/Rphylip/index.html) (requires PHYLIP), [ouch](http://cran.rstudio.com/web/packages/ouch/index.html), and [pegas](http://cran.rstudio.com/web/packages/pegas/index.html). 
-  For plotting trees most of these packages include their own modifications of the base `plot()` function, and there are also [ggtree](http://cran.rstudio.com/web/packages/ggtree/index.html), [ggdendro](http://cran.rstudio.com/web/packages/ggdendro/index.html), [dendextend](http://cran.rstudio.com/web/packages/dendextend/index.html), and [ggphylo](http://cran.rstudio.com/web/packages/ggphylo/index.html)
-  Morphometric and shape analysis methods are provided by [shapes](http://cran.rstudio.com/web/packages/shapes/index.html), [geomorph](http://cran.rstudio.com/web/packages/geomorph/index.html), [paleomorph](https://cran.r-project.org/web/packages/paleomorph) and [Momocs](http://cran.rstudio.com/web/packages/Momocs/index.html). Related packages include [shapeR](https://github.com/lisalibungan/shapeR) [Anthropometry](http://cran.rstudio.com/web/packages/Anthropometry/index.html) and [Morpho](http://cran.rstudio.com/web/packages/Morpho/index.html).
- [StereoMorph](http://cran.rstudio.com/web/packages/StereoMorph/index.html) allows users to collect 3D landmarks and curves from objects using two standard digital cameras. 
- [cTransmission](https://github.com/ercrema/cTransmission) provides an Approximate Bayesian Computation Framework for inferring patterns of cultural transmission from frequency data

**Image analysis**

-   [pixmap](http://cran.rstudio.com/web/packages/pixmap/index.html) provides methods for creating, plotting and converting bitmapped images in three different formats: RGB, grey and indexed pixmaps. Similarly, [jpeg](http://cran.rstudio.com/web/packages/jpeg/index.html) provides an easy and simple way to read, write and display bitmap images stored in the JPEG format.
-   [EBImage](http://www.bioconductor.org/packages/release/bioc/html/EBImage.html) (requires ImageMagick) provides general purpose functionality for the reading, writing, processing and analysis of images (and is very well documented). Various functions for image processing and analysis can also be found in [ripa](http://cran.rstudio.com/web/packages/ripa/index.html) and [imager](https://github.com/dahtah/imager)
-   [magick](https://github.com/jeroenooms/magick) provides bindings to the [ImageMagick image-processing library](http://www.imagemagick.org/), the most comprehensive open-source image processing package available.
-   [iconr](https://cran.r-project.org/web/packages/iconr) analysis of Prehistoric Iconography, considers any iconographic composition (‘decoration’) as a geometric graph of graphical units (GUs)

**Simulations**

- [NetLogoR](https://cran.r-project.org/package=NetLogoR) provides fucntions to easily create agent-based models in R following the NetLogo framework 
- [RNetLogo](http://cran.rstudio.com/web/packages/RNetLogo/index.html) links R and NetLogo
-  [simecol](http://cran.rstudio.com/web/packages/simecol/index.html) for simulating ecological (and other) dynamic systems. It can be used for differential equations, individual-based (or agent-based) and other models as well.
-  One-dimensional cellular automata are also possible to model with the package [CellularAutomaton](http://cran.rstudio.com/web/packages/CellularAutomaton/index.html).

**Network analysis**

-    The two major packages are [igraph](http://cran.rstudio.com/web/packages/igraph/index.html), which is a generic network analysis and visualisation package, and [sna](http://cran.rstudio.com/web/packages/sna/index.html), which performs social analysis of networks.
-    Other packages include [statnet](http://cran.rstudio.com/web/packages/statnet/index.html), [intergraph](http://cran.rstudio.com/web/packages/intergraph/index.html), [network](http://cran.rstudio.com/web/packages/network/index.html) (manipulates and displays network objects), [ergm](http://cran.rstudio.com/web/packages/ergm/index.html) (a set of tools to analyze and simulate networks based on exponential random graph models exponential random graph models), [hergm](http://cran.rstudio.com/web/packages/hergm/index.html) (implements hierarchical exponential random graph models), and [RSiena](http://cran.rstudio.com/web/packages/RSiena/index.html) (allows the analyses of the evolution of social networks using dynamic actor-oriented models)

**Mortality Analysis**

- [mortAAR](https://cran.r-project.org/web/packages/mortAAR/index.html) Analysis of Archaeological Mortality Data

**Skyscape Archaeology**
- [skyscapeR](https://github.com/f-silva-archaeo/skyscapeR) Data reduction, visualization and analysis in skyscape archaeology, archaeoastronomy and cultural astronomy

**Writing Reproducible manuscripts**

-  [rrtools](https://github.com/benmarwick/rrtools), is a package that provides instructions, templates, and functions for making a basic compendium suitable for writing reproducible research reports and articles with R.
-   The [rticles](https://github.com/rstudio/rticles) package includes templates for converting markdown documents into PDF files formatted ready for submission for publication, such as in the PLOS journals, the Frontiers In journals, and Elsevier journals. Similarly, the [papaja](https://github.com/crsh/papaja) packge contains a template for converting a markdown file into an APA-formatted PDF. These packages depend on [pandoc](http://johnmacfarlane.net/pandoc/), a universal document format converter (not an R package). In this context it is used to convert rmarkdown or LaTeX to PDF, MS Word or HTML files. It is included with RStudio but can also be used stand-alone from the command line.
-   [RStudio](http://www.rstudio.com/) is an integrated development environment that simplfies developing R code with numerous built-in conveniences, including vim keyboard shortcuts. There are also packages that make scholarly writing in RStudio easy: [wordcountaddin](https://github.com/benmarwick/wordcountaddin), [citr](https://github.com/crsh/citr). And several for making nice tables: [kableExtra](https://cran.r-project.org/web/packages/kableExtra), [carpenter)](https://github.com/lwjohnst86/carpenter), [htmlTable)](https://cran.r-project.org/web/packages/htmlTable), [pixiedust](https://cran.r-project.org/web/packages/pixiedust/index.html), [pander](https://github.com/Rapporter/pander), [simpletable](https://github.com/jalapic/simpletable) [stargazer](https://cran.r-project.org/web/packages/stargazer/)
-   The [rmarkdown](http://cran.rstudio.com/web/packages/rmarkdown/index.html) package implements the simple markdown document formatting language with some minor customizations to recognize R code blocks and inline code. The [bookdown](http://cran.rstudio.com/web/packages/bookdown/index.html) package provides tools for single file and multi-chapter rmarkdown documents with all the usual scholarly accessories: citations, figures, tables, captions and cross-referencing. 
- [redoc](https://github.com/noamross/redoc) is an experimental package to enable a two-way R-Markdown ⟷ Microsoft Word workflow.
-   [Emacs](http://www.gnu.org/software/emacs/) is a highly flexible text editor (easiest to use as the [spacemacs](http://spacemacs.org/) distribution), which when used with the [Emacs Speaks Statistics](http://ess.r-project.org/) package, is a comprehensive writing and R development environment. [Org-mode](http://orgmode.org/) provides a literate programming environment in Emacs similar to knitr. 

**Reproducible research**

-   [knitr](http://cran.rstudio.com/web/packages/knitr/index.html) enables R code and text with formatting instructions (eg. markdown or LaTeX) to be combined in a single document and executed to produce a document that contains rendered plots, analysed data and formatted text. The [remake](https://github.com/richfitz/remake) package has functions that enable declarative workflows so that each time an analysis is run, it updates only the parts of the workflow that have changed. 
-   The [rrrpkg](https://github.com/ropensci/rrrpkg) essay explains why the R package is a suitable file-and-folder structure for almost any research project, with real-world examples, [manuscriptPackage](https://github.com/jhollist/manuscriptPackage), [template](https://github.com/cboettig/template), [template](https://github.com/Pakillo/template) (yes, that's two slightly different packages with the same name), and [prodigenr](https://github.com/lwjohnst86/prodigenr), [makeProject](https://cran.r-project.org/web/packages/makeProject), and [ProjectTemplate](https://cran.r-project.org/web/packages/ProjectTemplate/index.html) are packages that give templates for organising an analysis as an R package (eg. where the manuscript is the package vignette, or similarly bundled with the package). [rlp](https://github.com/yihui/rlp) is a package that lets you write an analysis as a Rmd file and then converts it into a package  
-   [packrat](http://cran.rstudio.com/web/packages/packrat/index.html) supports the development of isolated, stand-alone projects that include all the packages used and their dependencies. [miniCRAN](http://cran.rstudio.com/web/packages/miniCRAN/index.html) has functions to create a local repository to install packages (and their dependancies) from without internet access. Related packages include [rbundler](http://cran.rstudio.com/web/packages/rbundler/index.html) for package development which manages dependencies listed in a package's DESCRIPTION file by storing them in a local project-specific library for installation, and [pkgsnap](https://github.com/MangoTheCat/pkgsnap) for creating a snapshot of your installed CRAN packages with 'snap', and then using 'restore' on another system to recreate exactly the same environment.
-   [checkpoint](http://cran.rstudio.com/web/packages/checkpoint/index.html) allows you to install R packages from a specific snapshot date in the past, ensuring that you use the same package version that you started with, not a more recent one (related: [gRAN](https://github.com/rgmbecker/gRAN) can retrieve and build sources for any version of any non-base package that has ever been released on CRAN or BioConductor).
-   [rocker](https://github.com/rocker-org/rocker) is a project that provides Docker containers to run R in a lightweight virtual environment, the hadleyverse container includes dplyr, ggplot2, etc., as well as RStudio server and LaTeX. The package [harbor](https://github.com/wch/harbor) provides functions for controlling docker containers on local and remote hosts. The [analogsea](https://github.com/sckott/analogsea) package has functions for deploying R and RStudio quickly & easily on DigitalOcean clusters using Docker images for cloud computing. The [dockertest](https://github.com/richfitz/dockertest) package contains functions for generating Dockerfiles from R packages and other R projects, and building Docker containers that contains all the package dependencies. [liftr](https://CRAN.R-project.org/package=liftr) helps with persistent reproducible reporting by containerization of R Markdown documents.

**Developing R code and packages**

-   [devtools](http://cran.rstudio.com/web/packages/devtools/index.html) (requires Rtools for Windows or Xcode for OSX) for easily creating R packages. [usethis](https://CRAN.R-project.org/package=usethis) automates many tasks surrouding package-making, including `use_travis()` and related functions for easily adding continuous integration for automated building and testing during package development. [Mason](https://github.com/metacran/mason) helps you to quickly build R packages using an interactive Q&A to generate metadata files, READMEs with badges, git repositories, etc.
-   [Goodpractice](https://github.com/MangoTheCat/goodpractice) gives advice about good practices when building R packages. Advice includes functions and syntax to avoid, package structure, code complexity, code formatting, etc.
-   [badgecreatr](https://github.com/RMHogervorst/badgecreatr) generates badges for your readme file to signal the quality and current status of your package. 
-   [roxygen2](http://cran.rstudio.com/web/packages/roxygen2/index.html) for simplifying the creation of documentation for packages,
-   [testthat](http://cran.rstudio.com/web/packages/testthat/index.html) for developing tests of functions in packages
-   [Rcpp](http://cran.rstudio.com/web/packages/Rcpp/index.html) enables the use of C++ code in R packages for high performance computing, requires Rtools for Windows or Xcode for OSX
-   [editR](https://github.com/swarm-lab/editR) is a basic Rmarkdown editor with instant previewing of your document. It allows you to create and edit Rmarkdown documents while instantly previewing the result of your writing and coding.
-   [Style guide for writing R code](http://adv-r.had.co.nz/Style.html) by Hadley Wickham, and the packages [formatR](http://cran.rstudio.com/web/packages/formatR/index.html) and [rfmt](https://github.com/google/rfmt) which are designed to reformat R code to improve readability. The [lintr](http://cran.r-project.org/web/packages/lintr/) package analyses code to check that it conforms to Hadley Wickham's style guide (this package is built into RStudio)
-   Idioms of R are discussed in the [vignette](http://cran.r-project.org/web/packages/rockchalk/vignettes/Rchaeology.pdf) of the [rockchalk](http://cran.rstudio.com/web/packages/rockchalk/index.html) package, and Pat Burn's essay [the R Inferno](http://www.burns-stat.com/documents/books/the-r-inferno/).

**Datasets**

-   [archdata](http://cran.rstudio.com/web/packages/archdata/index.html) contains eleven archaeological datasets from around the world reported in published studies. These represent typical forms of archaeological data (and so are useful for teaching)
-   [binford](https://github.com/benmarwick/binford) contains more than 200 variables coding aspects of hunter-gatherer subsistence, mobility, and social organization for 339 ethnographically documented groups of hunter-gatherers, as used in Binford (2001) _Constructing Frames of Reference: An Analytical Method for Archaeological Theory Building Using Ethnographic and Environmental Data Sets_
-  [BSDA](http://cran.rstudio.com/web/packages/BSDA/index.html) contains a dataset of 60 radiocarbon ages of observations taken from an archaeological site with four phases of occupation.
-  [cawd](https://github.com/sfsheath/cawd) contains 15 datasets of ancient Greek, Roman and Persian maps and digital atlas data 
-  [chemometrics](http://cran.rstudio.com/web/packages/chemometrics/index.html) contains a dataset of elemental concentrations for 180 archaeological glass vessels excavated from 15th - 17th century contexts in Antwerp.
-  [zooaRch](http://cran.r-project.org/web/packages/zooaRch/) contains two zooarchaeological datasets.
-  [gsloid](https://CRAN.R-project.org/package=gsloid) Contains published data sets for global benthic d18O data for 0-5.3 Myr and global sea levels based on marine sediment core data for 0-800 ka
- [evoarchdata](https://github.com/benmarwick/evoarchdata) contains four published datasets widely used in archaeological studies of cultural evolution


**Places to go for help**

- `?` function, eg. `?mean` to get built-in help on the mean function
- `sos::findFn("rose diagram")` searches all installed packages for the search term, using the [sos](http://cran.rstudio.com/web/packages/sos/index.html) package
-   Most major packages come with vignettes that narrate typical uses of the package's core functions. Vignettes can be accessed with the command `vignette(packagename)`.
- Google searches in the form: [r help [search terms]](https://www.google.com/?gws_rd=ssl#q=r+help+)
-   A custom search engine of R resources: http://www.rseek.org/
-   [Graphical output from the examples in the documentation for all CRAN packages](http://rgm3.lab.nig.ac.jp/RGM)
-   All R package documentation (including CRAN, GitHub and Bioconductor packages) is online in an easy-to-ready format at http://www.rdocumentation.org/
-   Cheatsheets to print for handy reference: [short one on base](http://cran.r-project.org/doc/contrib/Short-refcard.pdf), [longer one on base](http://cran.r-project.org/doc/contrib/Baggott-refcard-v2.pdf), [ggplot2, dplyr, tidyr, rmarkdown, making packages](http://www.rstudio.com/resources/cheatsheets/), [data.table](https://s3.amazonaws.com/assets.datacamp.com/img/blog/data+table+cheat+sheet.pdf), [using colours](https://www.nceas.ucsb.edu/~frazier/RSpatialGuides/colorPaletteCheatsheet.pdf), [colours](http://research.stowers-institute.org/efg/R/Color/Chart/ColorChart.pdf), [numerous others](http://devcheatsheet.com/tag/r/)
-  [stackoverflow](http://stackoverflow.com/questions/tagged/r) is an online Q&A point-scoring website where questions and answers can be voted on to indicate their quality. Many highly skilled R programmers are active participants. [Cross Validated](http://stats.stackexchange.com/) is a similar Q&A site for questions about statistics
-   You could send a message to the official [r-help email list](https://stat.ethz.ch/mailman/listinfo/r-help), but do be sure to read, follow and cite the [posting guide](http://www.r-project.org/posting-guide.html). The list is also [searchable](https://www.google.com/?gws_rd=ssl#q=site:stat.ethz.ch+pipermail+archaeology).


### Related links:

-   CRAN Task View: [SocialSciences](http://cran.rstudio.com/web/views/SocialSciences.html)
-   CRAN Task View: [Spatial](http://cran.rstudio.com/web/views/Spatial.html)
-   CRAN Task View: [Spatio-temporal](http://cran.rstudio.com/web/views/spatioTemporal.html)
-   CRAN Task View: [Cluster analysis](http://cran.r-project.org/web/views/Cluster.html)
-   CRAN Task View: [Multivariate Statistics](http://cran.r-project.org/web/views/Multivariate.html) 
-   CRAN Task View: [Bayesian inference](http://cran.r-project.org/web/views/Bayesian.html)
-   CRAN Task View: [Phylogenetics](http://cran.r-project.org/web/views/Phylogenetics.html)
-   CRAN Task View: [Robust](http://cran.r-project.org/web/views/Robust.html)
-   CRAN Task View: [Visualization](http://cran.r-project.org/web/views/Graphics.html)
-   CRAN Task View: [Reproducible research](http://cran.r-project.org/web/views/ReproducibleResearch.html) 
-   [David L. Carlson's guides on using R for 'Quantifying Archaeology' by Stephen Shennan 'Statistics for Archaeologists' by Robert Drennan]( http://people.tamu.edu/~dcarlson/quant/index.html)
-   [Matt Peeples' scripts for archaeological statistics]( http://www.mattpeeples.net/resources.html)
-   [Gianmarco Alberti's pages on Correspondence Analysis in Archaeology](http://cainarchaeology.weebly.com/)
-   [Quantitative Archaeology Wiki](http://wiki.iosa.it/doku.php), including [some code for battleship plots](http://wiki.iosa.it/dokuwiki/doku.php?id=contingency_tables)
-  [Michael Baxter's 'Notes on Quantitative Archaeology using R'](http://www.mikemetrics.com/r-chaeology/4568129078)
-   [GitHub repository for this Task View](https://github.com/benmarwick/ctv-archaeology)

#### Publications that include R code

Allison, James R. (2019). Ceramic Production and Exchange among the Virgin Anasazi, 30 Years Later, _KIVA_, 85:4, 289-312, <http://doi.org/10.1080/00231940.2019.1689660>

d'Alpoim Guedes J, Jin G, Bocinsky RK (2015). The Impact of Climate on the Spread of Rice to North-Eastern China: A New Look at the Data from Shandong Province. PLOS ONE 10(6): e0130430. doi: <http://dx.doi.org/10.1371/journal.pone.0130430>

d’Alpoim Guedes, Jade and R. Kyle Bocinsky. (2018). Climate change stimulated agricultural innovation and exchange across Asia, 2018. _Science Advances_ 4:eaar4491. <http://doi.org/10.1126/sciadv.aar4491>

d’Alpoim Guedes, J., Hanson, S., Higham, C., Higham, T., & Lertcharnrit, T. (2019). The wet and the dry, the wild and the cultivated: Subsistence and risk management in ancient Central Thailand. Archaeological and Anthropological Sciences, 11(12), 6473–6484. https://doi.org/10.1007/s12520-019-00794-8

Angourakis, Andreas, Verònica Martínez Ferreras, Alexis Torrano, and Josep M. Gurt Esparraguera. (2018). “Presenting Multivariate Statistical Protocols in R Using Roman Wine Amphorae Productions in Catalonia, Spain.” _Journal of Archaeological Science_ 93 (May): 150–65. https://doi.org/10.1016/j.jas.2018.03.007. Describes the cerUB pkg

Arroyo-Kalin, Manuel and Riris Philip (2021). Did pre-Columbian populations of the Amazonian biome reach carrying capacity during the Late Holocene? _Philosophical Transactions of the Royal Society B: Biological Sciences_ B37620190715 <http://doi.org/10.1098/rstb.2019.0715>

Barton, C. M., Tortosa, J. E. A., Garcia-Puchol, O., Riel-Salvatore, J. G., Gauthier, N., Conesa, M. V., & Bouchard, G. P. (2017). Risk and resilience in the late glacial: A case study from the western Mediterranean. _Quaternary Science Reviews_. <https://doi.org/10.1016/j.quascirev.2017.09.015>

Beck, J., & Smith, B. H. (2019). Don't throw the baby teeth out with the bathwater: Estimating subadult age using tooth wear in commingled archaeological assemblages. _International Journal of Osteoarchaeology_, 29(5), 831-842. <https://doi.org/10.1002/oa.2802>

Beheim, Bret A., and Adrian V. Bell. (2011). Inheritance, Ecology and the Evolution of the Canoes of East Oceania. _Proceedings of the Royal Society B: Biological Sciences_, February. <https://doi.org/10.1098/rspb.2011.0060> <https://github.com/babeheim/polynesian-canoe-analysis>

Belmiro, J., Bicho, N., Haws, J., & Cascalheira, J. (2020). The Gravettian-Solutrean transition in westernmost Iberia: New data from the sites of Vale Boi and Lapa do Picareiro. _Quaternary International_ <https://doi.org/10.1016/j.quaint.2020.08.027> <https://www.doi.org/10.17605/OSF.IO/456EG>

Benjamin J, O’Leary M, McDonald J, Wiseman C, McCarthy J, Beckett E, et al. (2020). Aboriginal artefacts on the continental shelf reveal ancient drowned cultural landscapes in northwest Australia. PLoS ONE 15(7): e0233912. <https://doi.org/10.1371/journal.pone.0233912> <https://github.com/patrick-morrison/benjamin_et_al_2020_submerged_cb>

Bevan A. and Crema E. R. (2021). Modifiable reporting unit problems and time series of long-term human activity. _Philosophical Transactions of the Royal Society B: Biological Sciences_ B37620190726 <http://doi.org/10.1098/rstb.2019.0726>

Biagetti, S., Alcaina-Mateos, J., Crema, E.R., (2016). A matter of ephemerality: the study of Kel Tadrart Tuareg (southwest Libya) campsites via quantitative spatial analysis. Ecology and Society 21. https://doi.org/10.5751/ES-08202-210142 [GitHub repo](https://github.com/ercrema/a_matter_of_ephemerality).

Bicho, N. and Cascalheira, J. (2018). The use of lithic assemblages for the definition of short-term occupations in hunter-gatherer prehistory. In Picin, A. and Cascalheira, J. (eds.) _Short-term occupations in Paleolithic Archaeology._ Interdisciplinary Contributions to Archaeology. Springer. <https://doi.org/10.17605/OSF.IO/3WGSA>

Bird, MI, SA Condie, S O’Connor, D O’Grady, C Reepmeyer, S Ulm, M Zega, F Saltré, CJA Bradshaw. (2019). Early human settlement of Sahul was not an accident. Scientific Reports doi:10.1038/s41598-019-42946-9 https://github.com/cjabradshaw/SahulHuman

Birch, T. and M. Martinón-Torres (2019). Shape as a measure of weapon standardisation: From metric to geometric morphometric analysis of the Iron Age ‘Havor’ lance from Southern Scandinavia. _Journal of Archaeological Science_ 101: 34-51 <https://doi.org/10.1016/j.jas.2018.11.002>

Borck, L., Athenstädt, J.C., Cheromiah, L.A., Aragon, L.D., Brandes, U. and Hofman, C.L., (2020). Plainware and Polychrome: Quantifying Perceptual Differences in Ceramic Classification Between Diverse Groups to Further a Strong Objectivity. Journal of Computer Applications in Archaeology, 3(1), pp.135–150. DOI: <http://doi.org/10.5334/jcaa.37>

Bradshaw, CJA, S Ulm, AN Williams, MI Bird, RG Roberts, Z Jacobs, F Laviano, LS Weyrich, T Friedrich, K Norman, F Saltré. (2019). Minimum founding populations for the first peopling of Sahul. Nature Ecology and Evolution doi:10.1038/s41559-019-0902-6 https://github.com/cjabradshaw/SahulHuman 

Breslawski RP, Etter BL, Jorgeson I, Boulanger MT (2018). The Atlatl to Bow Transition: What Can We Learn from Modern Recreational Competitions? _Lithic Technology_ <http://doi.org/10.1080/01977261.2017.1416918> <https://github.com/taphocoenose/The-atlatl-to-bow-transition>

Breslawski RP, Playford T (2017). Probabilistic Models of Seasonal Bison Exploitation Based on Fetal Prey Osteometry and Reproductive Phenology. _Archaeological and Anthropological Sciences_ <http://doi.org/10.1007/s12520-017-0500-y> <https://github.com/taphocoenose/Probabilistic-Models-of-Seasonal-Bison-Exploitation>

Brown, A., & Crema, E. (2019). Maori Population Growth in Pre-contact New Zealand: regional population dynamics inferred from summed probability distributions of radiocarbon dates. _The Journal of Island and Coastal Archaeology_ <https://doi-org/10.1080/15564894.2019.1605429> <https://zenodo.org/record/2250314>

Broughton, J. M., & Weitzel, E. M. (2018). Population reconstructions for humans and megafauna suggest mixed causes for North American Pleistocene extinctions. Nature communications, 9(1), 5441. https://doi.org/10.1038/s41467-018-07897-1

Brunner M, von Felten J, Hinz M, Hafner A (2020). Central European Early Bronze Age chronology revisited: A Bayesian examination of large-scale radiocarbon dating. PLOS ONE 15(12): e0243719. https://doi.org/10.1371/journal.pone.0243719

Bustos-Pérez, G., Baena, J., (2021). Predicting Flake Mass: A View from Machine Learning. _Lithic Technology_ 14. https://doi.org/10.1080/01977261.2021.1881267

Calandra, I., Schunk, L., Bob, K., Gneisinger, W., Pedergnana, A., Paixao, E., ... & Marreiros, J. (2019). The effect of numerical aperture on quantitative use-wear studies and its implication on reproducibility. _Scientific reports_, 9(1), 1-10. <https://doi.org/10.1038/s41598-019-42713-w>

Calandra I., Schunk, L., Rodriguez, A., Gneisinger, W., Pedergnana, A., Paixao, E., Marreiros, J. (2019). Back to the edge: relative coordinate system for use-wear analysis. _Archaeological and Anthropological Sciences_. <https://doi.org/10.1007/s12520-019-00801-y> 

Cardillo, Marcelo, Scartascini Federico Luis and Zangrando Atilio Francisco (2015). Combining morphological and metric variations in the study of design and functionality in stone weights. A comparative approach from continental and insular Patagonia, Argentina. _Journal of Archaeological Science: Reports_ 4:578-587. <https://doi.org/10.1016/j.jasrep.2015.10.030>

Carleton, W. C. (2020). Evaluating Bayesian Radiocarbon‐dated Event Count (REC) models for the study of long‐term human and environmental processes. _Journal of Quaternary Science_ https://doi.org/10.1002/jqs.3256

Carleton W. C., Groucutt HS. (2020). Sum things are not what they seem: Problems with point-wise interpretations and quantitative analyses of proxies based on aggregated radiocarbon dates. _The Holocene_  https://doi.org/10.1177/0959683620981700

Carleton, W. C. , J. Conolly, and G. Iannone (2012). A locally-adaptive model of archaeological potential (LAMAP) _Journal of Archaeological Science_ 39(11), 3371-3385, 2012 <https://doi.org/10.1016/j.jas.2012.05.022>, <https://github.com/wccarleton/lamap>

Carleton, W., McCauley, B., Costopoulos, A., & Collard, M. (2018). An evolutionary agent-based model contradicts Dunnell’s version of the waste hypothesis for cultural elaboration. <https://doi.org/10.31235/osf.io/2h36u> <https://github.com/wccarleton/abm_waste>

Carney, M. and Davies, B., (2020). Agent-Based Modeling, Scientific Reproducibility, and Taphonomy: A Successful Model Implementation Case Study. _Journal of Computer Applications in Archaeology_ 3(1), pp.182–196. DOI: <http://doi.org/10.5334/jcaa.52> <https://zenodo.org/record/3761900>

Carrero-Pazos, M., Bevan, A., & Lake, M. W. (2019). The spatial structure of Galician megalithic landscapes (NW iberia): A case study from the Monte Penide region. _Journal of Archaeological Science_, 108, 104968. https://doi.org/10.1016/j.jas.2019.05.004

Cascalheira, J., Gonçalves, C. and Maio D. (2020). The spatial patterning of Middle Paleolithic human settlement in westernmost Iberia. _Journal of Quaternary Science_ https://doi.org/10.1002/jqs.3286

Cascalheira, João. (2019). Territoriality and the organization of technology during the Last Glacial Maximum in southwestern Europe. _PloS one_, 14(12). https://doi.org/10.1371/journal.pone.0225828

Clarkson, C., Mike Smith, Ben Marwick, Richard Fullagar, Lynley A. Wallis, Patrick Faulkner, Tiina Manne, Elspeth Hayes, Richard G. Roberts, Zenobia Jacobs, Xavier Carah, Kelsey M. Lowe, Jacqueline Matthews, S. Anna Florin (2015). The archaeology, chronology and stratigraphy of Madjedbebe (Malakunanja II): A site in northern Australia with early occupation. _Journal of Human Evolution_  8, 46–64 [http://dx.doi.org/10.1016/j.jhevol.2015.03.014](http://dx.doi.org/10.1016/j.jhevol.2015.03.014)

Cochrane, E. E., Tautunu, A. A. M. M., & DiNapoli, R. J. (2019). Hypotheses to explain the few early coastal archaeological deposits in Sāmoa: Preliminary evaluations. _Journal of Archaeological Science: Reports_, 26, 101931. <https://doi.org/10.17608/k6.auckland.7647218>

Coco, E., & Iovita, R. (2020). Time-dependent taphonomic site loss leads to spatial averaging: implications for archaeological cultures. _Humanities and Social Sciences Communications_, 7(1), 1-9. <https://www.nature.com/articles/s41599-020-00635-3>

Coco, E., Holdaway, S. & Iovita, R. (2020). The Effects of Secondary Recycling on the Technological Character of Lithic Assemblages. _Journal of Paleolithic Archaeology_  <https://doi.org/10.1007/s41982-020-00055-4>

Conrad, C., Higham, C., Eda, M. and Marwick, B. (2016). Paleoecology and Forager Subsistence Strategies During the Pleistocene-Holocene Transition: A Reinvestigation of the Zooarchaeological Assemblage from Spirit Cave, Mae Hong Son Province, Thailand. _Asian Perspectives_ 55(1). https://github.com/cylerc/AP_SC

Contreras, Daniel A., Joël Guiot, Romain Suarez, and Alan Kirman. (2018). "Reaching The Human Scale: A Spatial and Temporal Downscaling Approach To The Archaeological Implications Of Paleoclimate Data." _Journal of Archaeological Science_ 93:54-67.[doi:10.1016/j.jas.2018.02.013](https://doi.org/10.1016/j.jas.2018.02.013)

Contreras, Daniel A. and John Meadows. (2014). “Summed radiocarbon calibrations as a population proxy: a critical evaluation using a realistic simulation approach.” _Journal of Archaeological Science_ 52:591-608. [doi:10.1016/j.jas.2014.05.030](http://www.sciencedirect.com/science/article/pii/S0305440314002088)

Coto-Sarmiento, M., Rubio-Campillo, X., Remesal, J., (2018). Identifying social learning between Roman amphorae workshops through morphometric similarity. _Journal of Archaeological Science_ 96, 117–123. <https://doi.org/10.1016/j.jas.2018.06.002>,   <https://github.com/Mcotsar/LearningBaetica>

Crema, E. R., and A. Bevan (2020). INFERENCE FROM LARGE SETS OF RADIOCARBON DATES: SOFTWARE AND METHODS. _Radiocarbon_ :1–17. https://doi.org/10.1017/RDC.2020.95

Crema, E.R., Kandler, A., Shennan, S., (2016). Revealing patterns of cultural transmission from frequency data: equilibrium and non-equilibrium assumptions, _Scientific Reports_ 6, 39122.

Crema, E. R., J. Habu, K. Kobayashi and M. Madella (2016). "Summed Probability Distribution of <sup>14</sup>C Dates Suggests Regional Divergences in the Population Dynamics of the Jomon Period in Eastern Japan." [_PLoS ONE_ 11(4): e0154809.](http://journals.plos.org/plosone/article?id=10.1371%2Fjournal.pone.0154809), [GitHub repo](https://github.com/ercrema/Jomon_SPD_Comparison), [Zenodo repo](http://dx.doi.org/10.5281/zenodo.47339).

Crema, E.R., K. Edinborough, T. Kerig, S.J. Shennan (2014). An Approximate Bayesian Computation approach for inferring patterns of cultural evolutionary change, _Journal of Archaeological Science_, Volume 50 Pages 160-170 [http://dx.doi.org/10.1016/j.jas.2014.07.014](http://www.sciencedirect.com/science/article/pii/S0305440314002593)

Crema, E.R., Kobayashi, K., (2020). A multi-proxy inference of Jōmon population dynamics using bayesian phase models, residential data, and summed probability distribution of 14C dates. Journal of Archaeological Science 117, 105136. https://doi.org/10.1016/j.jas.2020.105136 [GitHub repo](https://github.com/ercrema/jomonPhasesAndPopulation), [Zenodo repo](https://doi.org/10.5281/zenodo.3719507). 

Danielisová, A., Pajdla, P., Bursák, D., Strnad, L., Trubač, J. and Kmošek, J., (2021). Claiming the land or protecting the goods? The Duchcov hoard in Bohemia as a proxy for ‘Celtic migrations’ in Europe in the 4th century BCE. Journal of Archaeological Science 127, 105314. [https://doi.org/10.1016/j.jas.2020.105314](https://doi.org/10.1016/j.jas.2020.105314); [GitHub repo](https://github.com/petrpajdla/duchcov_si).

Davis, D.S.; DiNapoli, R.J.; Douglass, K. (2020). Integrating Point Process Models, Evolutionary Ecology and Traditional Knowledge Improves Landscape Archaeology—A Case from Southwest Madagascar. _Geosciences_ , 10, 287.

DiNapoli, R. J., Rieth, T. M., Lipo, C. P., & Hunt, T. L. (2020). A model-based approach to the tempo of “collapse”: The case of Rapa Nui (Easter Island). _Journal of Archaeological Science_, 105094.

DiNapoli, R. J., Lipo, C. P., Brosnan, T., Hunt, T. L., Hixon, S., Morrison, A. E., & Becker, M. (2019). Rapa Nui (Easter Island) monument (ahu) locations explained by freshwater sources. PLOS ONE, 14(1), e0210409. https://doi.org/10.1371/journal.pone.0210409

Dombrosky, J. (2020). A ~1000-year 13C Suess correction model for the study of past ecosystems. _The Holocene_, 30(3), 474–478. https://doi.org/10.1177/0959683619887416

Drake BL, Wills WH, Hamilton MI, Dorshow W (2014). Strontium Isotopes and the Reconstruction of the Chaco Regional System: Evaluating Uncertainty with Bayesian Mixing Models. PLoS ONE 9(5): e95580. [doi:10.1371/journal.pone.0095580](http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0095580)

Drake, Brandon L., David T. Hanson, James L. Boone (2012). The use of radiocarbon-derived Δ13C as a paleoclimate indicator: applications in the Lower Alentejo of Portugal, _Journal of Archaeological Science_, Volume 39, Issue 9, September 2012, Pages 2888-2896, [http://dx.doi.org/10.1016/j.jas.2012.04.027](http://www.sciencedirect.com/science/article/pii/S0305440312001471)

Drake, Brandon L., (2012). The influence of climatic change on the Late Bronze Age Collapse and the Greek Dark Ages, _Journal of Archaeological Science_, Volume 39, Issue 6, June 2012, Pages 1862-1870 [http://dx.doi.org/10.1016/j.jas.2012.01.029](http://www.sciencedirect.com/science/article/pii/S0305440312000416)

Drake, Brandon L., WH Wills, and Erik B Erhardt (2012). The 5.1 ka aridization event, expansion of piñon-juniper woodlands, and the introduction of maize (Zea mays) in the American Southwest The Holocene December 2012 22: 1353-1360, first published on July 9, 2012 [doi:10.1177/0959683612449758](http://hol.sagepub.com/content/22/12/1353.short)

Dye, Thomas S. (2011). “A Model-based Age Estimate for Polynesian Colonization of Hawai‘i”. _Archaeology in Oceania_ 46, pp. 130–138 [https://github.com/tsdye/hawaii-colonization](https://github.com/tsdye/hawaii-colonization)

Dye, T. S. (2016). "Long-term rhythms in the development of Hawaiian social stratification." _Journal of Archaeological Science_ <http://www.sciencedirect.com/science/article/pii/S030544031630053X> 71: 1-9.

Edinborough, K., Porčić, M., Martindale, A., Brown, T. J., Supernant, K., & Ames, K. M. (2017). Radiocarbon test for demographic events in written and oral history. _Proceedings of the National Academy of Sciences_, 114(47), 12436-12441. <https://doi.org/10.1073/pnas.1713012114>

Farahani, A. (2018). A 2500-year historical ecology of agricultural production under empire in Dhiban, Jordan. _Journal of Anthropological Archaeology_, 52, 137-155. <http://dx.doi.org/10.17632/dygn8vp6pz.1>

Florin, S.A., Roberts, P., Marwick, B. et al. (2021). Pandanus nutshell generates a palaeoprecipitation record for human occupation at Madjedbebe, northern Australia. _Nature Ecology and Evolution_ <https://doi.org/10.1038/s41559-020-01379-8> 

Freeman, J., Robinson, E., Beckman, N. G., Bird, D., Baggio, J. A., & Anderies, J. M. (2020). The global ecology of human population density and interpreting changes in paleo-population density. _Journal of Archaeological Science_, 120, 105168. <https://github.com/people3k/JAS2020Ethnographic-Population-Density>

Gantley, M., Whitehouse, H., & Bogaard, A. (2018). Material Correlates Analysis (MCA): An Innovative way of Examining Questions in Archaeology Using Ethnographic Data. _Advances in Archaeological Practice_, 6(4), 328-341. http://doi.org/10.1017/aap.2018.9

Garvey, Raven. (2018). Current and potential roles of archaeology in the development of cultural evolutionary theory. Philosophical Transactions of the Royal Society B: Biological Sciences, 373(1743), 20170057. https://doi.org/10.1098/rstb.2017.0057 <https://dx.doi.org/10.6084/m9.figshare.c.3965853>

Gauthier, Nicolas (2021). Hydroclimate variability influenced social interaction in the prehistoric american southwest. _Frontiers in Earth Science_ 8:713. DOI:10.3389/feart.2020.620856.

Giusti, D., Konidaris, G. E., Tourloukis, V., Marini, M., Maron, M., Zerboni, A., … Harvati, K. (2019). Recursive anisotropy: a spatial taphonomic study of the Early Pleistocene vertebrate assemblage of Tsiotra Vryssi, Mygdonia Basin, Greece. _Boreas_, 0(0). https://doi.org/10.1111/bor.12368

Giusti, D., Tourloukis, V., Konidaris, G., Thompson, N., Karkanas, P., Panagopoulou, E., & Harvati, K. (2018). Beyond maps: patterns of formation processes at the Middle Pleistocene open-air site of Marathousa 1, Megalopolis Basin, Greece. _Quaternary International._ <https://doi.org/10.1016/j.quaint.2018.01.041>

Giusti, D. and M. Arzarello, (2016). The need for a taphonomic perspective in spatial analysis: Formation processes at the Early Pleistocene site of Pirro Nord (P13), Apricena, Italy, _Journal of Archaeological Science: Reports_ 8, 235--249 code and data: <https://github.com/dncgst/pirronord_jas-reports> 

González-Molina I, Jiménez-García B, Maíllo-Fernández JM, Baquedano E, Domínguez-Rodrigo M (2020). Distinguishing Discoid and Centripetal Levallois methods through machine learning. _PLOS ONE_ 15(12): e0244288. <https://doi.org/10.1371/journal.pone.0244288> <https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/T8SEC2>

Graham, S., Gupta, N., Smith, J., Angourakis, A., Reinhard, A., Ellenberger, K., Batist, Z., Rivard, J., Marwick, B., Carter, M., Compton, B., Blades, R., Wood, C., Nobles, G. (2019). _The Open Digital Archaeology Textbook_ <https://o-date.github.io/> Code notebooks and repositories, and text source at <https://github.com/o-date>

Hageneuer, S. & Schmidt, S. C. (2019). Monumentality by numbers. In: Buccellati, F., Hageneuer, S., van der Heyden, S. & Levenson, F. (Eds.), _Size Matters - Understanding Monumentality Across Ancient Civilizations_. Bielefeld: transcript Verlag: 291-308. https://doi.org/10.14361/9783839445389-017

Hegmon M, Peeples MA, on behalf of the LTVTP-NABO collaboration (2018). The human experience of social transformation: Insights from comparative archaeology. _PLOS ONE_ 13(11): e0208060. https://doi.org/10.1371/journal.pone.0208060

Hinz, M., (2020). Sensitivity of Radiocarbon Sum Calibration. _Journal of Computer Applications in Archaeology_, 3(1), pp.238–252. DOI: http://doi.org/10.5334/jcaa.53

Hoggard, C. S., & Stade, C. M. (2019). The efficiency of Middle Palaeolithic technological blade strategies: an experimental investigation. Lithics–The Journal of the Lithic Studies Society, (39), 52. <http://journal.lithics.org/index.php/lithics/article/view/737> <https://osf.io/5v8xh/>

Hoggard, C. S., McNabb, J., & Cole, J. N. (2019). The Application of Elliptic Fourier Analysis in Understanding Biface Shape and Symmetry Through the British Acheulean. _Journal of Paleolithic Archaeology_. <https://doi.org/10.1007/s41982-019-00024-6> <https://osf.io/td92j/>

Horta, P., Cascalheira, J., & Bicho, N. (2019). The Role of Lithic Bipolar Technology in Western Iberia’s Upper Paleolithic: the Case of Vale Boi (Southern Portugal). _Journal of Paleolithic Archaeology_ <https://doi.org/10.1007/s41982-019-0022-5> <https://osf.io/wpxgh/>

Hu, Y., Marwick, B., Zhang, J.-F., Rui, X., Hou, Y.-M., Yue, J.-P., ... Li, B. (2018). Late Middle Pleistocene Levallois stone-tool technology in southwest China. _Nature_ <https://doi.org/10.1038/s41586-018-0710-1> <https://doi.org/10.17605/OSF.IO/ERNTJ>

Huffer, D. and Graham, S. (2017). The Insta-Dead: the rhetoric of the human remains trade on Instagram, _Internet Archaeology_ 45. <https://doi.org/10.11141/ia.45.5>, code & data: <https://zenodo.org/record/546132>

Huffer, D. and Graham, S. (2018). Fleshing Out the Bones: Studying the Human Remains Trade with Tensorflow and Inception, _Journal of Computer Applications in Archaeology_ 1(1), pp.55-063. <https://doi.org/10.5334/jcaa.8>, code & data: <https:doi.org/10.17605/OSF.IO/9CFJA>

Ivanovaitė, L., Serwatka, K., Hoggard, C., Sauer, F., & Riede, F. (2020). All these Fantastic Cultures? Research History and Regionalization in the Late Palaeolithic Tanged Point Cultures of Eastern Europe. _European Journal of Archeology_, 23 (2), 162-185. doi:10.1017/eaa.2019.59 <https://osf.io/agrwb/> <https://github.com/CSHoggard/-Eastern-Europe-Tanged-Points>

Kandler, A., Crema, E.R., (2019). Analysing Cultural Frequency Data: Neutral Theory and Beyond, in: Prentiss, A.M. (Ed.), Handbook of Evolutionary Research in Archaeology. Springer International Publishing, Cham, pp. 83–108. https://doi.org/10.1007/978-3-030-11117-5_5  [GitHub repo](https://github.com/ercrema/HERAChp.KandlerCrema)

King, C. L., Millard, A. R., Gröcke, D. R., Standen, V. G., Arriaza, B. T., & Halcrow, S. E. (2018). Marine resource reliance in the human populations of the Atacama Desert, northern Chile–A view from prehistory. _Quaternary Science Reviews_, 182, 163-174. <https://doi.org/10.1016/j.quascirev.2017.12.009>

Kintigh, K.W. and Peeples, M.A., (2020). Estimating Population Growth Rates and Instantaneous Population from Periodized Settlement Data. Journal of Computer Applications in Archaeology, 3(1), pp.197–209. DOI: <http://doi.org/10.5334/jcaa.58> <https://github.com/kintigh/RoomAccum>

Lawrence D, Palmisano A, de Gruchy MW (2021). Collapse and continuity: A multi-proxy reconstruction of settlement organization and population trajectories in the Northern Fertile Crescent during the 4.2kya Rapid Climate Change event. _PLoS ONE_ 16(1): e0244871. <doi:10.1371/journal.pone.0244871>

Leplongeon, Alice, Clément Ménard, Vincent Bonhomme, and Eugenio Bortolini. (2020). “Backed Pieces and Their Variability in the Later Stone Age of the Horn of Africa.” _African Archaeological Review_. <https://doi.org/10.1007/s10437-020-09401-x> <https://doi.org/10.6084/m9.figshare.7825607>

Lewis, J. (2021). Probabilistic Modelling for Incorporating Uncertainty in Least Cost Path Results: A Postdictive Roman Road Case Study. _Journal of Archaeological Method and Theory_ https://doi.org/10.1007/s10816-021-09522-w

Lewis, J. (2020). Visibility of the Gask Ridge road from simulated Watchtowers: A Monte Carlo testing approach. Journal of Archaeological Science: Reports, 33, 102482. https://doi.org/10.1016/j.jasrep.2020.102482

Lightfoot E and O'Connell TC (2016). “On The Use of Biomineral Oxygen Isotope Data to Identify Human Migrants in the Archaeological Record: Intra-Sample Variation, Statistical Methods and Geographical Considerations.” PLoS ONE 11(4). [http://doi:10.1371/journal.pone.0153850](http://doi:10.1371/journal.pone.0153850), code and data: [https://www.repository.cam.ac.uk/handle/1810/252773](https://www.repository.cam.ac.uk/handle/1810/252773)

Lipo, C. P., Hunt, T. L., Horneman, R., & Bonhomme, V. (2016). Weapons of war? Rapa Nui mata’a morphometric analyses. _Antiquity_, 90(349), 172–187. <doi:10.15184/aqy.2015.189>  <https://github.com/clipo/mataaMorphometrics>

Lowe, K., Wallis, L., Pardoe, C., Marwick, B., Clarkson, C., Manne, T., Smith, M. and R. Fullagar (2014). Ground-penetrating radar and burial practices in western Arnhem Land, Australia. _Archaeology in Oceania_  49(3): 148–157 [http://onlinelibrary.wiley.com/doi/10.1002/arco.5039/abstract](http://onlinelibrary.wiley.com/doi/10.1002/arco.5039/abstract)

Mackay, Alex, Sam C. Lin, Lachlan S. Kenna, and Alex F. Blackwood. (2018). Variance in the Response of Silcrete to Rapid Heating Complicates Assumptions about Past Heat Treatment Methods.” _Archaeological and Anthropological Sciences_, June 20, 2018, 1–12. <https://doi.org/10.1007/s12520-018-0663-1>.

Mackay A, Sumner A, Jacobs Z, Marwick B, Bluff K and Shaw M (2014). Putslaagte 1 (PL1), the Doring River, and the later Middle Stone Age in southern Africa's Winter Rainfall Zone. _Quaternary International_ [http://dx.doi.org/10.1016/j.quaint.2014.05.007](http://dx.doi.org/10.1016/j.quaint.2014.05.007)

Marwick, B., Wang, L.-Y., Robinson, R., & Loiselle, H. (2019). How to Use Replication Assignments for Teaching Integrity in Empirical Archaeology. _Advances in Archaeological Practice_, 1–9.  <https://doi.org/10.1017/aap.2019.38>

Marwick, B., Hiscock, P., Sullivan, M., & Hughes, P. (2017). Landform boundary effects on Holocene forager landscape use in arid South Australia. _Journal of Archaeological Science: Reports_ <http://doi.org/10.1016/j.jasrep.2017.07.004>

Marwick, Ben, Elspeth Hayes, Chris Clarkson and Richard Fullagar (2017). Movement of lithics by trampling: An experiment in the Madjedbebe sediments, northern Australia. _Journal of Archaeological Science_ 79:73-85. <http://dx.doi.org/10.1016/j.jas.2017.01.008>, <https://github.com/benmarwick/mjbtramp>,  <http://dx.doi.org/10.17605/OSF.IO/32A87> 

Marwick, B., Van Vlack, H.G., Conrad, C., Shoocongdej, R., Thongcharoenchaikit, C., Kwak, S. (2016). Adaptations to sea level change and transitions to agriculture at Khao Toh Chong rockshelter, Peninsular Thailand, _Journal of Archaeological Science_  <http://dx.doi.org/10.1016/j.jas.2016.10.010>, <https://github.com/benmarwick/ktc11>, <https://osf.io/axxf8/>

Marwick, B, C. Clarkson, S. O'Connor & S. Collins (2016). "Pleistocene-aged stone artefacts from Jerimalai, East Timor: Long term conservatism in early modern human technology in island Southeast Asia" _Journal of Human Evolution_ DOI: <http://doi.org/10.1016/j.jhevol.2016.09.004>, <https://github.com/benmarwick/Pleistocene-aged-stone-artefacts-from-Jerimalai--East-Timor>, <https://osf.io/63zey>

Marwick, B., & Birch, S. (2018). A Standard for the Scholarly Citation of Archaeological Data as an Incentive to Data Sharing. _Advances in Archaeological Practice_ 1-19 <https://doi.org/10.1017/aap.2018.3>

Marwick, B. (2017). Computational reproducibility in archaeological research: Basic principles and a case study of their implementation. _Journal of Archaeological Method and Theory_ 1-27. [doi: 10.1007/s10816-015-9272-9](http://dx.doi.org/10.1007/s10816-015-9272-9), [text source repo](https://github.com/benmarwick/basic_computational_reproducibility_case_study)

Marwick, B., (2013). Multiple Optima in Hoabinhian flaked stone artefact palaeoeconomics and palaeoecology at two archaeological sites in Northwest Thailand. _Journal of Anthropological Archaeology_ 32, 553-564.  [http://dx.doi.org/10.1016/j.jaa.2013.08.004](http://dx.doi.org/10.1016/j.jaa.2013.08.004)

Marwick, B. (2013). Discovery of Emergent Issues and Controversies in Anthropology Using Text Mining, Topic Modeling, and Social Network Analysis of Microblog Content. In Yanchang Zhao, Yonghua Cen (eds) _Data Mining Applications with R_ Elsevier. p. 63-93 [https://github.com/benmarwick/AAA2011-Tweets](https://github.com/benmarwick/AAA2011-Tweets)

McLaughlin, T. Rowan, Gómez-Puche Magdalena, Cascalheira João, Bicho Nuno and Fernández-López de Pablo Javier (2021). Late Glacial and Early Holocene human demographic responses to climatic and environmental change in Atlantic Iberia _Philosophical Transactions of the Royal Society B: Biological Sciences_ B37620190724 <http://doi.org/10.1098/rstb.2019.0724>

McLaughlin, T.R. (2018). On Applications of Space–Time Modelling with Open-Source 14C Age Calibration. _Journal of Archaeological Method and Theory_  <https://doi.org/10.1007/s10816-018-9381-3>

McPherron, S. P., Abdolahzadeh, A., Archer, W., Chan, A., Djakovic, I., Dogandžić, T., ... & Reeves, J. (2020). Introducing platform surface interior angle (PSIA) and its role in flake formation, size and shape. Plos one, 15(11), e0241714. <https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0241714>

McPherron SP (2018). Additional statistical and graphical methods for analyzing site formation processes using artifact orientations. _PLOS ONE_ 13(1): e0190195. <https://doi.org/10.1371/journal.pone.0190195>

Nakoinz, O., D. Knitter (2016). _Modelling Human Behaviour in Landscapes. Basic Concepts and Modelling Elements_. Quantitative Archaeology and Archaeological Modelling 1. Springer, New York. <https://github.com/dakni/mhbil>, <https://github.com/ISAAKiel>

Negre, J., Muñoz, F., & Barceló, J. A. (2017). A Cost-Based Ripley’s K Function to Assess Social Strategies in Settlement Patterning. _Journal of Archaeological Method and Theory_, 1-18. <https://doi.org/10.1007/s10816-017-9358-7>

Negre, J., Muñoz, F., Lancelotti, C., (2016). Geostatistical modelling of chemical residues on archaeological floors in the presence of barriers, _Journal of Archaeological Science_ 70, 91-101. https://github.com/famuvie/ArchaeologicalFloors

Orton, D., Gaastra, J., & Vander Linden, M. (2016). Between the Danube and the Deep Blue Sea: Zooarchaeological Meta-Analysis Reveals Variability in the Spread and Development of Neolithic Farming across the Western Balkans. Open Quaternary, 2, 6. DOI: <http://doi.org/10.5334/oq.28> data & code: <http://eprints.whiterose.ac.uk/104121/>

Palmisano, A. (2017). Confronting scales of settlement hierarchy in state-level societies: Upper Mesopotamia and Central Anatolia in the Middle Bronze Age. _Journal of Archaeological Science: Reports_, 14, 220-240. <https://doi.org/10.1016/j.jasrep.2017.05.029>

Palmisano, A., Bevan, A., & Shennan, S. (2017). Comparing archaeological proxies for long-term population patterns: An example from central Italy. _Journal of Archaeological Science_, 87, 59-72. <https://doi.org/10.1016/j.jas.2017.10.001>

Palmisano, A., Lawrence, D., de Gruchy, M. W., Bevan, A., & Shennan, S. (2021). Holocene regional population dynamics and climatic trends in the Near East: A first comparison using archaeo-demographic proxies. Quaternary Science Reviews, 252, 106739. <https://doi.org/10.1016/j.quascirev.2020.106739>

Palmisano, A., Bevan, A., Kabelindde,A., Roberts, N., & Shennan, S. (2021). Long-Term Demographic Trends in Prehistoric Italy: climate impacts and regionalised socio-ecological trajectories. Journal of World Prehistory, 34 (3).<https://doi.org/10.1007/s10963-021-09159-3>

Pargeter, Justin, Paloma de la Peña, and Metin I. Eren. (2018). “Assessing Raw Material’s Role in Bipolar and Freehand Miniaturized Flake Shape, Technological Structure, and Fragmentation Rates.” Archaeological and Anthropological Sciences, May, 1–15. <https://doi.org/10.1007/s12520-018-0647-1> data & code: <https://osf.io/38tsn/>

Pargeter, J., Khreisheh, N., & Stout, D. (2019). Understanding stone tool-making skill acquisition: Experimental methods and evolutionary implications. _Journal of Human Evolution_, 133, 146-166. <https://osf.io/h5c8t/>

Pederzani, S., Aldeias, V., Dibble, H.L. et al. (2021). Reconstructing Late Pleistocene paleoclimate at the scale of human behavior: an example from the Neandertal occupation of La Ferrassie (France). _Scientific Reports_ 11, 1419  https://doi.org/10.1038/s41598-020-80777-1

Perri et al (2019). Dietary variation among indigenous Nicaraguan horticulturalists and their dogs: An ethnoarchaeological application of the Canine Surrogacy Approach _Journal of Anthropological Archaeology_ Volume 55,<https://doi.org/10.1016/j.jaa.2019.05.002> <https://osf.io/dbxe9/>

Phillips, N., Pargeter, J., Low, M. et al. (2018). Open-air preservation of miniaturised lithics: experimental research in the Cederberg Mountains, southern Africa. _Archaeological and Anthropological Sciences_ (2018). https://doi.org/10.1007/s12520-018-0617-7

Porčić, Marko, Blagojević Tamara, Pendić Jugoslav and Stefanović Sofija (2021). The Neolithic Demographic Transition in the Central Balkans: population dynamics reconstruction based on new radiocarbon evidence _Philosophical Transactions of the Royal Society B: Biological Sciences_ B37620190712 <http://doi.org/10.1098/rstb.2019.0712>

Porčić, M., Blagojević, T., Pendić, J., & Stefanović, S. (2020). The timing and tempo of the Neolithic expansion across the Central Balkans in the light of the new radiocarbon evidence. _Journal of Archaeological Science: Reports_, 33, 102528. <https://doi.org/10.1016/j.jasrep.2020.102528>

Porčić, M., Nikolić, M., (2016). The Approximate Bayesian Computation approach to reconstructing population dynamics and size from settlement data: demography of the Mesolithic-Neolithic transition at Lepenski Vir. _AArchaeological and Anthropological Sciences_ 8, 169–186. https://doi.org/10.1007/s12520-014-0223-2

Potì, A., Kehl, M., Broich, M., Carrión Marco, Y., Hutterer, R., Jentke, T., Linstädter, J., López-Sáez, J.A., Mikdad, A., Morales, J., Pérez-Díaz, S., Portillo, M., Schmid, C., Vidal-Matutano, P., Weniger, G.-C., (2019). Human occupation and environmental change in the western Maghreb during the Last Glacial Maximum (LGM) and the Late Glacial. New evidence from the Iberomaurusian site Ifri El Baroud (northeast Morocco). _Quaternary Science Reviews_ 220, 87–110. https://doi.org/10.1016/j.quascirev.2019.07.013

Price, M. D., Wolfhagen, J., and Otárola-Castillo, E. (2016). Confidence Intervals in the Analysis of Mortality and Survivorship Curves in Zooarchaeology. _American Antiquity_ 81(1): 157-73. <https://doi.org/10.7183/0002-7316.81.1.157>

Reeves, J. S., McPherron, S. P., Aldeias, V., Dibble, H. L., Goldberg, P., Sandgathe, D., & Turq, A. (2019). Measuring spatial structure in time-averaged deposits insights from Roc de Marsal, France. Archaeological and Anthropological Sciences. <https://doi.org/10.1007/s12520-019-00871-y>

Reynolds, N., & Green, C. (2019). Spatiotemporal modelling of radiocarbon dates using linear regression does not indicate a vector of demic dispersal associated with the earliest Gravettian assemblages in Europe. Journal of Archaeological Science: Reports, 27, 101958. https://doi.org/10.1016/j.jasrep.2019.101958

Reynolds, N., Germonpré, M., Bessudnov, A. A., & Sablin, M. V. (2019). The Late Gravettian Site of Kostënki 21 Layer III, Russia: a Chronocultural Reassessment Based on a New Interpretation of the Significance of Intra-site Spatial Patterning. _Journal of Paleolithic Archaeology_. <https://doi.org/10.1007/s41982-018-0018-6>

Režek, Ž., Dibble, H.L., McPherron, S.P., Braun, D.R., Lin, S.C., (2018). Two million years of flaking stone and the evolutionary efficiency of stone tool technology. _Nature Ecology & Evolution_ 1.<https://doi.org/10.1038/s41559-018-0488-4>, <https://doi.org/10.5281/zenodo.1194711>

Riede, F. C. Hoggard & S. Shennan (2019). Reconciling material cultures in archaeology with genetic data requires robust cultural evolutionary taxonomies. _Palgrave Communications_ 5, Article number: 55 (2019)   https://www.nature.com/articles/s41599-019-0260-7#Fn1

Riris, P., Silva, F. (2021). Resolution and the detection of cultural dispersals: development and application of spatiotemporal methods in Lowland South America. _Humanities and Social Sciences Communications_ 8, 36  https://doi.org/10.1057/s41599-021-00717-w

Riris, P. (2020). Spatial structure among the geometric earthworks of western Amazonia (Acre, Brazil). _Journal of Anthropological Archaeology_, 59, 101177. <https://doi.org/10.1016/j.jaa.2020.101177> <https://doi.org/10.17605/OSF.IO/NG896>

Riris, P., & Arroyo-Kalin, M. (2019). Widespread population decline in South America correlates with mid-Holocene climate change. _Scientific reports_, 9(1), 6850.

Riris, P. (2018). Dates as Data Revisited: A Statistical Examination of the Peruvian Preceramic Radiocarbon Record. _Journal of Archaeological Science_ 97 (September 1, 2018): 67–76.<https://doi.org/10.1016/j.jas.2018.06.008>

Roberts, N., Woodbridge, J., Bevan, A., Palmisano, A., Shennan, S., & Asouti, E. (2018). Human responses and non-responses to climatic variations during the last Glacial-Interglacial transition in the eastern Mediterranean. Quaternary Science Reviews, 184, 47-67. <https://doi.org/10.1016/j.quascirev.2017.09.011>

Robinson, Erick, Bocinsky R. Kyle, Bird Darcy, Freeman Jacob and Kelly Robert L. (2021). Dendrochronological dates confirm a Late Prehistoric population decline in the American Southwest derived from radiocarbon dates _Philosophical Transactions of the Royal Society B: Biological Sciences_ B37620190718 <http://doi.org/10.1098/rstb.2019.0718>

Roscoe, Paul, Sandweiss Daniel H. and Robinson Erick (2021). Population density and size facilitate interactive capacity and the rise of the state _Philosophical Transactions of the Royal Society B: Biological Sciences_ B37620190725 http://doi.org/10.1098/rstb.2019.0725

Rubio-Campillo, X., Montanier,, J.M., Rull, G., Bermúdez Lorenzo, J.M., Moros Díaz, J., Pérez González, J., Remesal Rodríguez, J. (2018). The ecology of Roman trade. Reconstructing provincial connectivity with similarity measures, Journal of Archaeological Science, 92, pp. 37-47. doi:10.1016/j.jas.2018.02.010 <https://github.com/xrubio/ecologyStamps>

Rubio-Campillo, X., Coto-Sarmiento, M., Pérez-Gonzalez, J. and Remesal Rodríguez, J. (2017). Bayesian analysis and free market trade within the Roman Empire, Antiquity, 91(359), pp. 1241–1252. doi:10.15184/aqy.2017.131 <https://github.com/xrubio/bayesRome>

Sanger, M.C., Bourcy, S., Ogden, Q.M. et al. (2020). Post-marital Residence Patterns in the Late Archaic Coastal Southeast USA: Similarities in Stone Tools Revealed by Geometric Morphometrics. _Journal of Archaeological Method and Theory_ 27, 327–359  <https://doi.org/10.1007/s10816-019-09435-9> <https://orb.binghamton.edu/dissertation_and_theses/46/>

Schauer, Peter, Andrew Bevan, Stephen Shennan, Kevan Edinborough, Tim Kerig, Mike Parker Pearson (2020). British Neolithic axe distributions and their implications. _Journal of Archaeological Method and Theory_ 27, 836–859. <https://doi.org/10.1007/s10816-019-09438-6>

Schmid, C. (2019). Evaluating Cultural Transmission in Bronze Age burial rites of Central, Northern and Northwestern Europe using radiocarbon data. _Adaptive Behavior_, 1059712319860842. <https://osf.io/b6np2/>

Schmidt, S. C. (2020). Siedlungsgrößen und Abstände zwischen Siedlungsstandorten – eine geostatistische Analyse von Transektdaten, _Praehistorische Zeitschrift_, 94(2), 499-528. doi: https://doi.org/10.1515/pz-2019-0015 

Schmidt, Isabell, Hilpert Johanna, Kretschmer Inga, Peters Robin, Broich Manuel, Schiesberg Sara, Vogels Oliver, Wendt Karl Peter, Zimmermann Andreas and Maier Andreas (2021). Approaching prehistoric demography: proxies, scales and scope of the Cologne Protocol in European contexts _Philosophical Transactions of the Royal Society B: Biological Sciences_ B37620190714 <http://doi.org/10.1098/rstb.2019.0714>

Schmidt, S.C. and Marwick, B., (2020). Tool-Driven Revolutions in Archaeological Science. Journal of Computer Applications in Archaeology, 3(1), pp.18–32. DOI: <http://doi.org/10.5334/jcaa.29>

Selden Jr., R. Z., Dockall, J. E., Bousman, C. B., & Perttula, T. K. (2021). Shape as a function of time + raw material + burial context? An exploratory analysis of Perdiz arrow points from the ancestral Caddo area of the American Southeast. _Journal of Archaeological Science: Reports_, 37, 102916. https://doi.org/10.1016/j.jasrep.2021.102916

Selden, R. Z., Dockall, J. E., & Dubied, M. (2020). A quantitative assessment of intraspecific morphological variation in Gahagan bifaces from the southern Caddo area and central Texas. Southeastern Archaeology, 39(2), pp.125–145. DOI: <https://doi.org/10.1080/0734578X.2020.1744416> data & code: <https://osf.io/2g95w/>

Shennan, SJ, Enrico R. Crema, Tim Kerig, (2014). Isolation-by-distance, homophily, and 'core' vs. 'package' cultural evolution models in Neolithic Europe, _Evolution and Human Behavior_, Available online 2 October 2014,  [http://dx.doi.org/10.1016/j.evolhumbehav.2014.09.006](http://www.sciencedirect.com/science/article/pii/S1090513814001251)

Sinensky, R. J., and A. Farahani. (2018). DIVERSITY-DISTURBANCE RELATIONSHIPS IN THE LATE ARCHAIC SOUTHWEST: IMPLICATIONS FOR FARMER-FORAGER FOODWAYS American Antiquity 83 (2): 364–364. <https://doi.org/10.1017/aaq.2017.74>

Silva, F., (2020). A probabilistic framework and significance test for the analysis of structural orientations in skyscape archaeology. Journal of Archaeological Science 118, 105138. https://doi.org/10.1016/j.jas.2020.105138

Steele, Teresa E., Alex Mackay, Kathryn E. Fitzsimmons, Marina Igreja, Ben Marwick, Jayson Orton, Steve Schwortz, and Mareike C. Stahlschmidt (2016). "Varsche Rivier 003: A Middle and Later Stone Age Site with Still Bay and Howieson's Poort Assemblages in Southern Namaqualand, South Africa" _PaleoAnthropology_ 2016:100-163 <http://www.paleoanthro.org/media/journal/content/PA20160100.pdf>, < http://dx.doi.org/10.5281/zenodo.31903> 

Stewart, M., Carleton, W.C. & Groucutt, H.S. (2021). Climate change, not human population growth, correlates with Late Quaternary megafauna declines in North America. _Nature communications_ 12, 965 https://doi.org/10.1038/s41467-021-21201-8

Stoddart, S., Palmisano, A.,Redhouse, D., Barker, G., di Paola, G., Motta, L., Rasmussen, T., Samuels, T. & Witcher, R. (2020). Patterns of EtruscanUrbanism. Front. Digit. Humanit. 7:1. <https://doi.org/10.3389/fdigh.2020.00001>

Strawhacker, C., Snitker, G., Peeples, M. A., Kinzig, A. P., Kintigh, K. W., Bocinsky, K., ... & Sandor, J. A. (2020). A Landscape Perspective on Climate-Driven Risks to Food Security: Exploring the Relationship between Climate and Social Transformation in the Prehispanic US Southwest. _American Antiquity_, 85(3), 427-451.  <https://doi.org/10.1017/aaq.2020.35> <https://github.com/gsnitker/LTVTP> <https://core.tdar.org/collection/14044/long-term-vulnerability-and-transformation-project-ltvtp-documents-and-data>

Suárez, R., & Cardillo, M. (2019). Life history or stylistic variation? A geometric morphometric method for evaluation of Fishtail point variability. Journal of Archaeological Science: Reports, 27, 101997. <https://doi.org/10.1016/j.jasrep.2019.101997>

Suryanarayan, A., Cubas, M., Craig, O. E., Heron, C. P., Shinde, V. S., Singh, R. N., O'Connell, T. C., Petrie, C. A. (2021). Lipid residues in pottery from the Indus Civilisation in northwest India. _Journal of Archaeological Science_125. <https://doi.org/10.1016/j.jas.2020.105291> 

Tallavaara, Miikka and Jørgensen Erlend Kirkeng (2021). Why are population growth rate estimates of past and present hunter–gatherers so different? _Philosophical Transactions of the Royal Society B: Biological Sciences_ B37620190708 http://doi.org/10.1098/rstb.2019.0708

Timpson, Adrian, Barberena Ramiro, Thomas Mark G., Méndez César and Manning Katie (2021). Directly modelling population dynamics in the South American Arid Diagonal using 14C dates _Philosophical Transactions of the Royal Society B: Biological Sciences_ B37620190723 <http://doi.org/10.1098/rstb.2019.0723>

Ullah, Isaac I. T., Ian Kuijt, and Jacob Freeman. (2015). “Toward a Theory of Punctuated Subsistence Change.” _Proceedings of the National Academy of Sciences_ 112 (31): 9579–84. <https://doi.org/10.1073/pnas.1503628112>. <http://figshare.com/articles/Cross_cultural_data_for_multivariate_analysis_of_subsistence_strategies/1404233>

Vander Linden, Marc and Silva Fabio (2021). Dispersals as demographic processes: testing and describing the spread of the Neolithic in the Balkans _Philosophical Transactions of the Royal Society B: Biological Sciences_ B37620200231 http://doi.org/10.1098/rstb.2020.0231

Vignoles, Anais, William E. Banks, Laurent Klaric, Masa Kageyama, Marlon E. Cobos, Daniel Romero-Alvarez. (2020). Investigating relationships between technological variability and ecology in the Middle Gravettian (ca. 32-28 ka cal. BP) in France. (2020), OSF, ud3hj, ver. 3 peer-reviewed and recommended by PCI Archaeology. <https://doi.org/10.31219/osf.io/ud3hj>

Wang, L. and Marwick, B. (2020). Standardization of ceramic shape: A case study from the Iron Age pottery from northeastern Taiwan. _Journal of Archaeological Science: Reports_ 33. <https://doi.org/10.1016/j.jasrep.2020.102554> <https://github.com/LiYingWang/kwl.pottery> <https://osf.io/abvgf/>

Wang, L. and Marwick, B. (2020). Ornaments as indicators of social changes resulting from indirect effects of colonialism in northeastern Taiwan. _Archaeological Research in Asia_. <https://doi.org/10.1016/j.ara.2020.100226> <https://github.com/LiYingWang/kwl-ornaments> <https://osf.io/r8yga/>

Weiss, Marcel. (2020). “The Lichtenberg Keilmesser - It’s All about the Angle.” _PLOS ONE_ 15(10): e0239718. <https://doi.org/10.1371/journal.pone.0239718>

Weitzel, E. M. (2019). Declining foraging efficiency in the Middle Tennessee River Valley prior to initial domestication. _American Antiquity_, 1-24. https://doi.org/10.1017/aaq.2018.86 https://osf.io/2gub7/

Wilczek, J., Monna, F., Navarro, N., & Chateau-Smith, C. (2021). A computer tool to identify best matches for pottery fragments. Journal of Archaeological Science: Reports, 37, 102891. https://doi.org/10.1016/j.jasrep.2021.102891

Wolfhagen, J. (2020). Re-examining the use of the LSI technique in zooarchaeology. _Journal of Archaeological Science_ Volume 123, November 2020, 105254 https://doi.org/10.1016/j.jas.2020.105254 https://osf.io/4k62y/

Wolfhagen, J. and Price, M. D. (2017). A probabilistic model for distinguishing between sheep and goat postcranial remains. _Journal of Archaeological Science: Reports_ 12: 625-31. <https://doi.org/10.1016/j.jasrep.2017.02.022>

Wren, C. D., & Burke, A. (2019). Habitat suitability and the genetic structure of human populations during the Last Glacial Maximum (LGM) in Western Europe. PloS one, 14(6), e0217996. <https://osf.io/n24rq/>

Wren, C. D., Botha, S., De Vynck, J., Janssen, M. A., Hill, K., Shook, E., Marean, C. W. (2019). The foraging potential of the Holocene Cape south coast of South Africa without the Palaeo-Agulhas Plain. _Quaternary Science Reviews_, 105789. <https://doi.org/10.1016/j.quascirev.2019.06.012>

Yaworsky, P. M., Vernon, K. B., Spangler, J. D., Brewer, S. C., & Codding, B. F. (2020). Advancing predictive modeling in archaeology: An evaluation of regression and machine learning methods on the Grand Staircase-Escalante National Monument. _PloS one_, 15(10), e0239424. https://doi.org/10.1371/journal.pone.0239424



#### Contributors

[Ben Marwick](https://github.com/benmarwick), Agustin Diez Castillo, Allar Haav, Sebastian Heath, Phil Riris, Tom Brughmans, Lee Drake, Stefano Costa, [Enrico Crema](https://github.com/ercrema), [Domenico Giusti](https://github.com/dncgst), Matt Peeples, Mark Madsen, Daniel Contreras, [Tal Galili](https://github.com/talgalili), [Li-Ying Wang](https://github.com/LiYingWang)
