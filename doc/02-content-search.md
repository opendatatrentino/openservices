# Ricerca di un contenuto

```GET content/search/$Query```

La risposta in JSON è un oggetto [SearchResults](05-resources.md#searchresults)

La varibile obbligatoria ```$Query``` rappresenta la stringa di ricerca.
Il server API riconosce [un meta-linguaggio](06-search-query.md) per filtrare i contenuti.