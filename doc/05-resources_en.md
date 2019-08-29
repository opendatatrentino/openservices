#Representation of resources

## Content

[Example of content in json format](example/content.json)

The resource contained represents the heart of the API. It is exposed as an object composed of two properties that represent its metadata and the actual data.

| identifier | Type of data | Description |
|: ------------- |: --------------- |: ---------------- ---------------------------- |
| [metadata](# metadata) | object | Representation of content metadata |
| [date](# date) | object | Representation of content data |

### Metadata

Metadata is information that cannot be referred to the actual content of the object but to its context. Through the metadata it is possible to reach useful information for the research such as the unique identifier of the resource, the class of content used, the dates of publication and modification ...

| identifier | Type of data | Description | Notes |
|: ------------- |: --------------- |: ---------------- ------------------------- | ---- |
| id | integer | Unique ID of the content in the API server | Read only |
| remoteId | string | Unique ID of the content in the API server set by the editor or by the automatic import process: for design its length cannot exceed 100 characters | |
| classIdentifier | string | Identifier of the content class used by the exposed resource | |
| class | uri | Access URL to the class resource used by the exposed resource | Read only |
| sectionIdentifier | string | Identifier of the section used by the exposed resource | |
| stateIdentifiers | array | Array of status identifiers (in the format <stategroup_identifier>. <state_identifier> used by the exposed resource | |
| published | Date ISO 8601 | Date of publication of the content | Read only |
| modified | Date ISO 8601 | Date of last modification of the content | Read only |
| languages ​​| array | Array of language identifiers of the available translations of the exposed resource | Read only |
| name | hash | Associative array of the resource name for each available translation | Read only |
| parentNodes | array | Array of the Nodes Ids in which the information object is placed | |
| link | uri | Access URL to the requested resource | Read only |

### Data

| identifier | Type of data | Description |
|: ------------- |: --------------- |: ---------------- ---------------------------- |
| (Language identifier) ​​| object | Representation of content attributes |

The Data resource exposes the information content of the Content for each available translation. Each language identifier corresponds to a key-value object where each key is the attribute identifier and each value is represented by a primitive or structured data type (see the paragraph "[Data types] (# types-of -given)").
Given the flexible nature of the eZPublish content model it is necessary to derive the structure of the Data resource through the definition of the class that can be reached from the url exposed in `` content.metadata.class``` (see the paragraph "[Class] (# class ) ").


## SearchResults
| identifier | Type of data | Description |
|: ------------- |: --------------- |: ---------------- ---------------------------- |
| query | string | Search string |
| nextPageQuery | string or null | String to receive the next page of results |
| totalCount | integer | Total number of content obtained from the search |
| searchHits | Array of [Content](05-resources#content) or [FeatureCollection](http://geojson.org/geojson-spec.html#feature-collection-objects) | Search results |

## Class

## Data types
