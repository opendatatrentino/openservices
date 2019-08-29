# Rappresentazione delle risorse

## Content

[Esempio di content in formato json](example/content.json)

La risorsa contenuto rappresenta il cuore delle API. Essa viene esposta come un oggetto composto da due proprietà che ne rappresentano i metadati e i dati veri e propri.

| Identificatore| Tipo di dato  | Descrizione                                 |
|:------------- |:---------------|:--------------------------------------------|
| [metadata](#metadata)      | object        | Rappresentazione dei metadati del contenuto |
| [data](#data)          | object        | Rappresentazione dei dati del contenuto     |

### Metadata

I metadati sono informazioni non riferibili al contentuto vero e proprio dell'oggetto ma al suo contesto. Attraverso i metadati è possibile raggiungere informazioni utiliu per la ricerca quali l'identificativo unico della risorsa, la classe di contenuto utilizzata, le date di pubblicazione e di modifica...

| Identificatore| Tipo di dato  | Descrizione                                 | Note |
|:------------- |:---------------|:-----------------------------------------|:----|
| id            | integer       | Id univoco del contenuto nel server API     | Sola lettura |
| remoteId      | string        | Id univoco del contenuto nel server API impostato dal redattore o dal processo di importazione automatica: per design la sua lunghezza non può superare i 100 caratteri     | |
| classIdentifier  | string       | Identificatore della classe di contenuto utilizzata dalla risorsa esposta     | |
| class  | uri       | Url di accesso alla risorsa classe utilizzata dalla risorsa esposta     | Sola lettura |
| sectionIdentifier            | string       | Identificatore della sezione utilizzata dalla risorsa esposta     | |
| stateIdentifiers            | array       | Array degli identificatori di stato (nel formato <stategroup_identifier>.<state_identifier>  utilizzati dalla risorsa esposta   | |
| published            | Date ISO 8601   | Data di pubblicazione del contenuto     | Sola lettura |
| modified            | Date ISO 8601   | Data di ultima modifica del contenuto     | Sola lettura |
| languages            | array   | Array degli identificatori di lingua delle traduzioni disponibili della risorsa esposta     | Sola lettura |
| name | hash | Array associativo del nome della risorsa per ciascuna traduzione disponibile | Sola lettura |
| parentNodes            | array       | Array dei Id dei Nodi in cui è collocato l'oggetto informativo     | |
| link            | uri       | Url di accesso alla risorsa richiesta     | Sola lettura |

### Data

| Identificatore| Tipo di dato  | Descrizione                                 |
|:------------- |:---------------|:--------------------------------------------|
| (Identificatore di lingua)      | object        | Rappresentazione degli attributi del contenuto |

La risorsa Data espone il contenuto informativo del Content per ciascuna traduzione disponibile. Ad ogni identificatore di lingua corrisponde da un oggetto chiave-valore dove ciascuna chiave è l'identificatore dell'attributo e ciascun valore è rappresentato da un tipo di dato primitivo o strutturato (vedi il paragrafo "[Tipi di dato](#tipi-di-dato)").
Data la natura flessibile del content model di eZPublish è necessario ricavare la struttura della risorsa Data attravero la definizione della classe raggiungibile dall'url esposto in ```content.metadata.class``` (vedi il paragrafo "[Class](#class)").


## SearchResults
| Identificatore| Tipo di dato  | Descrizione                                 |
|:------------- |:---------------|:--------------------------------------------|
| query      | string        | Stringa di ricerca |
| nextPageQuery          | string oppure null        | Stringa per ricevere la pagina successiva dei risultati      |
| totalCount      | integer        | Numero totale di contenuti ottenuti dalla ricerca |
| searchHits      | Array di [Content](05-resources#content) oppure [FeatureCollection](http://geojson.org/geojson-spec.html#feature-collection-objects)        | Risultati della ricerca |

## Class

## Tipi di dato
