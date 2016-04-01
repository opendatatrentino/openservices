# Ricerca di punti geografici

```GET geo/search/$Query```

La risposta in geoJSON è un oggetto [FeatureCollection](http://geojson.org/geojson-spec.html#feature-collection-objects)

La varibile obbligatoria ```$Query``` rappresenta la stringa di ricerca.
Il server API riconosce [un meta-linguaggio](06-search-query.md) per filtrare i contenuti.