# Web API opendata

OpenData APIs offer read access to content, access to class definition and access to the list of sections and content statuses.

## Access to the API
It is possible to access the API through an HTTP request to the API server. The server will return the requested resource with an HTTP status code consistent with the result of the request made.

### Format of the response
The default response format of the ```content``` modules is [JSON] (http://www.json.org/).
The default response format of the ```geo``` modules is [geoJSON] (http://geojson.org/).

### Authentication
Some requests require the client to authenticate.
At the moment ** authentication is available [Basic] (https://it.wikipedia.org/wiki/Basic_access_authentication) **, the implementation of the Oauth / Oauth2 format is in the roadmap.


## Content API

- [Read content] (doc/01-content-read_en.md)
- [Search for content] (doc/02-content-search_en.md)
- [Reading of a geographical point] (doc/03-geo-read_en.md)
- [Search for geographic points] (doc/04-geo-search_en.md)
- [Resource representation] (doc/05-resources_en.md)
- [Search query] (doc/06-search-query_en.md)
