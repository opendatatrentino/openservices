#La query di ricerca

Per eseguire una query occorre specificare una stringa di ricerca Query.

La Query viene effettuata attraverso i **filtri** e i **parametri**.

## Filtri
I filtri sono composti dai un identificatore, un operatore e un valore.

Ad esempio:

```titolo = 'Mercatino di Natale'```

In questo esempio, il campo è "titolo", l'operatore è "=" e il valore è "'Mercatino di Natale'".
Si sta chiedendo al motore di ricerca di restituire tutti i contenuti che hanno un attributo il cui è identificatore "titolo" contiene il valore 'Mercatino di Natale'.

### Operatori per i filtri
Operatore | Tipo di valore atteso | Esempio
------------- | ------------- | -------------
=  | Stringa compresa tra apici  | titolo = 'Nel mezzo del cammin'
!=  | Stringa compresa tra apici  | titolo != 'Nel mezzo del cammin'
in e la sua negazione !=  | Array di stringhe  | titolo in ['Nel mezzo del cammin di nostra vita','La gloria di colui che tutto move']
contains e la sua negazione !contains  | Array di stringhe  | titolo contains ['Nel mezzo del cammin di nostra vita','La gloria di colui che tutto move']
range e la sua negazione !range   | Array di 2 stringhe  | from_time range [2014-01-01,2014-12-31]

L'operatore "contains" produce in AND logico: tutti i titoli che contengono le stringhe 'Nel mezzo del cammin di nostra vita' e 'La gloria di colui che tutto move' contemporaneamente.

L'operatore "in" produce in OR logico: tutti i titoli che contengono la stringa 'Nel mezzo del cammin di nostra vita' oppure la stringa 'La gloria di colui che tutto move'.


### Parametri
Operatore | Tipo di valore atteso | Esempio | Utilizzo
------------- | ------------- | ------------- | -------------
sort  | Hash | sort [published => desc] | Ordinamento
limit  | intero | limit 10 | Numero di risultati per pagina (massimo 100, default 30)
offset | intero  | offset 10 | Offset per la paginazione
classes  | stringa o Array di stringhe  | classes 'event' oppure classes ['event','article'] | restrizione sui tipi di contenuto
subtree  | Array di interi  | subtree [2,43,54] | restrizione di sotto albero


I parametri servono a modificare l'ambito di ricerca e sono rappresentati da una chiave e da un valore.
```classes 'event'```

In questo esempio la chiave è "classes" e il valore "'event'". Si sta chiedendo al motore di ricerca di restiruire tutti contenuti di classe "event".

Ecco un esempio che usa filtri e parametri:
```titolo = 'Mercatino di Natale' classes 'event'```

E' possibile eseguire ricerche più complesse. 
Ad esempio per ricerca gli eventi della settimana prosssima:

```from_time range [today,next week] or to_time range [today,next week]  or ( from_time range [*,today] and to_time range [next week,*]  ) classes event sort [published => desc]```

Il server API mette a disposizione di default una console raggiungibile da (www.domain.tdl/opendata/console)