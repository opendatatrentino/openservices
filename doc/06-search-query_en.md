# The search query

To execute a query, a Query search string must be specified.
The query is made through the **filters** and the **parameters**.

## Filters
Filters are composed of an identifier, an operator and a value.

For example:
```title = 'Christmas Market'```

In this example, the field is "title", the operator is "=" and the value is "'Christmas market'".
The search engine is being asked to return all content that has an attribute whose "title" identifier contains the value 'Christmas Market'.

### Filtering Operators
Operator | Expected value type | Example
------------- | ------------- | -------------
=  | String between quotes  | title = 'Nel mezzo del cammin'
!=  | String between quotes  | title != 'Nel mezzo del cammin'
in and negation !=  | string Array  | title in ['Nel mezzo del cammin di nostra vita','La gloria di colui che tutto move']
contains and negation !contains  | string Array  | title contains ['Nel mezzo del cammin di nostra vita','La gloria di colui che tutto move']
range and negation !range   | 2 string Array  | from_time range [2014-01-01,2014-12-31]

The "contains" operator produces in logical AND: all the titles that contain the strings 'In the middle of the journey of our life' and 'The glory of the one who moves everything' simultaneously.

The "in" operator produces in logical OR: all the titles that contain the string 'In the middle of the journey of our life' or the string 'The glory of the one who moves everything'.


### Parameters
Operator | Expected value type | Example | Usage
------------- | ------------- | ------------- | -------------
sort  | Hash | sort [published => desc] | Ordering
limit  | integer | limit 10 | Nber of results by page (max 100, default 30)
offset | integer | offset 10 | paging Offset
classes  | string o string Array  | classes 'event' or classes ['event','article'] | restriction of content types
subtree  | integer Array  | subtree [2,43,54] | restriction of subtree


The parameters are used to change the search scope and are represented by a key and a value.
```classes 'event'```

In this example the key is "classes" and the value "'event'". The search engine is being asked to return all "event" class content.

Here is an example that uses filters and parameters:
```titolo = 'Christmas market' classes' event'````

It is possible to perform more complex searches.
For example, to search for the events of the next week:

```from_time range [today, next week] or to_time range [today, next week] or (from_time range [*, today] and to_time range [next week, *]) classes event sort [published => desc]` `

The API server provides a console available by default at this URL, with a real DNS domain (www.domain.tdl/opendata/console)
