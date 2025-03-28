---
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Interactive Map

## Leaflet

Including Jupyter Widgets within a Quarto document is as easy as including a plot. For example, here is how we embed a Leaflet map:

```{code-cell} ipython3
from ipyleaflet import Map, basemaps, basemap_to_tiles

m = Map(
    basemap=basemap_to_tiles(basemaps.NASAGIBS.ModisTerraTrueColorCR, "2017-04-08"),
    center=(52.204793, 360.121558),
    zoom=4
)
m
```

## Plotly

Plotly is an interactive graphics library that can also be used with the Jupyter engine. Here’s an example of using Plotly:

```{code-cell} ipython3
import plotly.express as px
df = px.data.election()
fig = px.scatter_3d(df, x="Joly", y="Coderre", z="Bergeron", color="winner", size="total", hover_name="district",symbol="result", color_discrete_map = {"Joly": "blue", "Bergeron": "green", "Coderre":"red"})

fig.show()
```