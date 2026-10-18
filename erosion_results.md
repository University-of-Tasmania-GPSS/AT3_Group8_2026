# Results
## Derwent Estuary

::::{tab-set}

:::{tab-item} CVI
```{figure} figures/map_cvi_full.png
:alt: CVI erosion susceptibility for the Derwent estuary
:width: 100%

CVI output for the Derwent Estuary
```
:::

:::{tab-item} Fuzzy Gamma Overlay
```{figure} figures/map_fuzzy_full.png
:alt: Fuzzy overlay erosion susceptibility for the Derwent estuary
:width: 100%

Fuzzy Gamma Overlay output for the Derwent Estuary (gamma value 0.9)
```
:::

::::

## Long Beach Area

::::{tab-set}

:::{tab-item} CVI
```{figure} figures/map_cvi_zoom.png
:alt: CVI erosion susceptibility, zoomed to the sinkhole area
:width: 100%

CVI output for the Long Beach area
```
:::

:::{tab-item} Fuzzy Gamma Overlay
```{figure} figures/map_fuzzy_zoom.png
:alt: Fuzzy overlay erosion susceptibility, zoomed to the sinkhole area
:width: 100%

Fuzzy Gamma Overlay output for Long Beach (gamma value 0.9)
```
:::

::::

## Evaluation

Both datasets are spatially coherent with very little artefacts depicted in both Long Beach study area outputs. Despite this, the Fuzzy Gamma model does do a much better job of removing the artefacts in the model and is much more uniform in nature. It is however known that erosion is not uniform in nature and there can experience very localised changes in erosion meaning this not not of benefit to the Fuzzy Gamma model itself. 

Using theList erosion map as the source of truth, the Fuzzy Gamma model is the more effective model as it better detects more of the beach which is defined as high susceptibility in theList map. It should however be noted that there is severe limitations in this dataset and is not the same accuracy of this study.

Due to its improved localised erosion detection, the CVI model is deemed to be the more effective model. Not only this but as it is backed by literature which describes it as the most effective model with heavy usage in studies all over the world (ElKotby, 2026). Thus making CVI the preferred model over the Fuzzy Gamma.

&nbsp;

## Limitations
As previously touched on, there are limitations in the data to detect man made sea wall erosion for a number of factors. The geology layer used to classify the sea wall is only 25 metres resolution and only classifies natural surfaces. This means a sea wall which is likely to be maximum 5 metres in width is not going to show up in the dataset. 

Due to limitations in literature available, the table that was used to classify geology was based on mountainous geologies and not estuary meaning there may be innacuracies in this data.

The ERA5 wind data does not account for localised changes in the wind due hills or valleys meanining localised wave data may be skewed.

The fetch tool also is not an entirely accurate measure of wave height as it does not account for local conditions such as rocks in the area, water depth change or tides which also all affect wave height 