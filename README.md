# Web API opendata

Le OpenData API offrono l'accesso in lettura dei contenuti, l'accesso alla definizione delle classi e l'accesso all'elenco delle sezioni e degli stati dei contenuti.

## Accesso alle API
E' possibile accedere alle API attraverso una richiesta HTTP al server API. Il server restituirà la risorsa richiesta con uno status code HTTP coerente con il risultato della richiesta fatta.

### Formato della risposta
Il formato di default della risposta dei moduli ```content``` è [JSON](http://www.json.org/).
Il formato di default della risposta dei moduli ```geo``` è [geoJSON](http://geojson.org/).

### Autenticazione
Alcune richieste richiedono che il client effettui l'autenticazione.
Al momento è disponibile **l'autenticazione [Basic](https://it.wikipedia.org/wiki/Basic_access_authentication)**, è in roadmap l'implementazione del formato Oauth/Oauth2.


## API di contenuto

- [Lettura di un contenuto](doc/01-content-read.md)
- [Ricerca di un contenuto ](doc/02-content-search.md)
- [Lettura di un punto geografico](doc/03-geo-read.md)
- [Ricerca di punti geografici](doc/04-geo-search.md)
- [Rappresentazione delle risorse](doc/05-resources.md)
- [La query di ricerca](doc/06-search-query.md)

## ENGLISH VERSION
Una versione in inglese di queste istruzioni è disponibile [qui](https://github.com/opendatatrentino/openservices)
