---
layout: default
---

##  FT_DENOISE_TSR

Note that this reference documentation is identical to the help that is displayed in MATLAB when you type "help ft_denoise_tsr".

`<html>``<pre>`
    `<a href=/reference/ft_denoise_tsr>``<font color=green>`FT_DENOISE_TSR`</font>``</a>` performs a regression analysis, using a (time-shifted set
    of) reference signal(s) as independent variable. It is a generic
    implementation of the method described by De Cheveigne 
    (https://doi.org/10.1016/j.jneumeth.2007.06.003), or can be
    used to compute temporal-response-functions (see e.g. Crosse 
    (https://doi.org/10.3389/fnhum.2016.00604)), or
    spatial filters based on canonical correlation (see Thielen
    (https://doi.org/10.1371/journal.pone.0133797))
 
    Use as
    [dataout] = ft_denoise_tsr(cfg, data)
    
    or as
    [dataout] = ft_denoise_tsr(cfg, data, refdata)
 
    where "data" is a raw data structure that was obtained with `<a href=/reference/ft_preprocessing>``<font color=green>`FT_PREPROCESSING`</font>``</a>`. If
    you specify the additional input "refdata", the specified reference channels for
    the regression will be taken from this second data structure. This can be useful
    when reference-channel specific preprocessing needs to be done (e.g. low-pass
    filtering).
 
    The output structure dataout contains the denoised data in a format that is
    consistent with the output of `<a href=/reference/ft_preprocessing>``<font color=green>`FT_PREPROCESSING`</font>``</a>`.
 
    The configuration options ar
 
    cfg.refchannel         = the channels used as reference signal (default = 'MEGREF'), see `<a href=/reference/ft_selectdata>``<font color=green>`FT_SELECTDATA`</font>``</a>`
    cfg.channel            = the channels to be denoised (default = 'all'), see `<a href=/reference/ft_selectdata>``<font color=green>`FT_SELECTDATA`</font>``</a>` 
    cfg.method             = string, 'mlr', 'cca', 'pls', 'svd', option specifying the criterion for the regression
                             (default = 'mlr')
    cfg.reflags            = integer array, specifying temporal lags (in msec) by which to shift refchannel
                             with respect to data channels
    cfg.trials             = integer array, trials to be used in regression, see `<a href=/reference/ft_selectdata>``<font color=green>`FT_SELECTDATA`</font>``</a>`
    cfg.testtrials         = cell array or string, trial indices to be used as test folds in a cross-validation scheme
                             (numel(cfg.testrials == number of folds))
    cfg.nfold              = scalar, indicating the number of test folds to
                             use in a cross-validation scheme
    cfg.standardiserefdata = string, 'yes' or 'no', whether or not to standardise reference data
                             prior to the regression (default = 'no')
    cfg.standardisedata    = string, 'yes' or 'no', whether or not to standardise dependent variable
                             prior to the regression (default = 'no')
    cfg.demeanrefdata      = string, 'yes' or 'no', whether or not to make
                             reference data zero mean prior to the regression (default = 'no')
    cfg.demeandata         = string, 'yes' or 'no', whether or not to make
                             dependent variable zero mean prior to the regression (default = 'no')
    cfg.threshold          = integer array, ([1 by 2] or [1 by numel(cfg.channel) + numel(cfg.reflags)]), 
                             regularization or shrinkage ('lambda') parameter to be loaded on the diagonal of the
                             penalty term (if cfg.method == 'mlrridge' or 'mlrqridge')
    cfg.updatesens         = string, 'yes' or 'no' (default = 'yes')
    cfg.perchannel         = string, 'yes' or 'no', or logical, whether or not to perform estimation of beta weights
                             separately per channel
    cfg.output             = string, 'model' or 'residual' (defaul = 'model'), 
                             specifies what is outputed in .trial field in &lt;dataout&gt; 
    cfg.performance        = string, 'Pearson' or 'r-squared' (default =
                             'Pearson'), indicating what performance metric is outputed in .weights(k).performance
                             field of &lt;dataout&gt; for the k-th fold     
 
    === cfg.threshold
    if cfg.threshold is 1 x 2 integer array, cfg.threshold(1) parameter scales uniformly
    in the dimension of predictor variable and cfg.threshold(2) in the space of
    response variable
 
 
`</pre>``</html>`
