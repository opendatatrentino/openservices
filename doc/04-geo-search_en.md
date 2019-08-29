# Search for geographic points

```GET geo/search/$Query```

The answer in geoJSON is an object [FeatureCollection](http://geojson.org/geojson-spec.html#feature-collection-objects)

The mandatory variable ```$Query``` represents the search string.
The API server recognizes [a meta-language](06-search-query_en.md) to filter the contents.
