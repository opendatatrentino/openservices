# Representation of resources

## Content

[Example of content in json format](example/content.json)

The resource contained represents the heart of the API. It is exposed as an object composed of two properties that represent its metadata and the actual data.

| Identifier| Data Type  | Description                                 |
|:------------- |:---------------|:--------------------------------------------|
| [metadata](#metadata)      | object        | Representation of content metadata |
| [data](#data)          | object        | Representation of content data     |

### Metadata

Metadata is information that cannot be referred to the actual content of the object but to its context. Through the metadata it is possible to reach useful information for the research such as the unique identifier of the resource, the class of content used, the dates of publication and modification ...

| Identifier| Data Type  | Description                                 | Note |
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

| Identifier| Data Type  | Description                                 |
|:------------- |:---------------|:--------------------------------------------|
| (Identificatore di lingua)      | object        | Rappresentazione degli attributi del contenuto |

The Data resource exposes the information content of the Content for each available translation. Each language identifier corresponds to a key-value object where each key is the attribute identifier and each value is represented by a primitive or structured data type (see the paragraph "[Data types](#types-of-given)").
Given the flexible nature of the eZPublish content model it is necessary to derive the structure of the Data resource through the definition of the class that can be reached from the url exposed in ```content.metadata.class``` (see the paragraph "[Class](#class)").

## SearchResults
| Identifier| Data Type  | Description                                 |
|:------------- |:---------------|:--------------------------------------------|
| query      | string        | Stringa di ricerca |
| nextPageQuery          | string oppure null        | Stringa per ricevere la pagina successiva dei risultati      |
| totalCount      | integer        | Numero totale di contenuti ottenuti dalla ricerca |
| searchHits      | Array di [Content](05-resources#content) oppure [FeatureCollection](http://geojson.org/geojson-spec.html#feature-collection-objects)        | Risultati della ricerca |

## Class

## Data types
