# Validation

## Long Beach

```{figure} figures/thelist_erosion.png
:alt: Erosion data derived from theLIST for Long Beach
:width: 75%
:align: center

Erosion data derived from theLIST for the Long Beach area.
```

::::{grid} 1 1 2 2
:gutter: 2

:::{grid-item}
```{figure} figures/map_cvi_zoom.png
:alt: CVI erosion susceptibility, zoomed to Long Beach
:width: 100%

CVI output for the Long Beach area.
```
:::

:::{grid-item}
```{figure} figures/map_fuzzy_zoom.png
:alt: Fuzzy overlay erosion susceptibility, zoomed to Long Beach
:width: 100%

Fuzzy Gamma Overlay output for Long Beach (gamma value 0.9).
```
:::
::::


## Derwent Estuary

```{figure} figures/list_erosion.png
:alt: Erosion data from the LIST coastline dataset for the Derwent Estuary
:width: 50%
:align: center

Erosion data derived from LIST for the Derwent Estuary.
```

::::{grid} 1 1 2 2
:gutter: 2

:::{grid-item}
```{figure} figures/map_cvi_full.png
:alt: CVI erosion susceptibility for the Derwent Estuary
:width: 100%

CVI output for the Derwent Estuary.
```
:::

:::{grid-item}
```{figure} figures/map_fuzzy_full.png
:alt: Fuzzy overlay erosion susceptibility for the Derwent Estuary
:width: 100%

Fuzzy Gamma Overlay output for the Derwent Estuary (gamma value 0.9).
```
:::
::::


## Interpretation
As the list imagery depicts, there was little data that could act as a source of truth available to use. Hence, there was a requirement to establish our own erosion model. Despite this, there were several factors in the output that were able to effectively validate the data.

### 1. Known sinkhole location

The area where the known sinkhole is marked as very high sinkhole susceptibility.

### 2. Sandy beaches

Visual inspection of the data suggests that both the CVI and the Fuzzy Gamma outputs are valid. Both models mark every sandy beach in the estuary as “high susceptibility”. This output is correct, as it is known that fine sediments like sand are highly susceptible to erosion (Moosdorf et al., 2018). These these areas also experience a significant amount of wave power, suggesting that these areas have been classified correctly.

### 3. Upstream river areas

Further illustration that the model is behaving as expected is depicted further up the river. According to the output maps, the areas further up the river (where the river width decreases) in the majority are classified as low erosion susceptibility. This illustrates that the wave model is performing as it should, as these areas were classified as experiencing low wave power and thus low erosion susceptibility.