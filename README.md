# jsondeepsearch

Recursive deep search for keys or values in JSON structured nested and mixed python dictionary.

> There is a small difference between JSON and python dictionaries: in JSON keys are only strings like "key".
> Do not use expressions as parameters by calling the following functions, use only names of variables, dictionaries and sequences

## functions:

**lookforkey(jsondict, key)**

Search the key in dictionary. The key is a string in quotes like "key".

Returns a tuple with a dict (last match: {key:value}) and a list (all matches: [key, value, absolute index including original dictionary name])) 

**lookforvalue(jsondict, value)**

Search the value in dictionary.

The value can be any type of variables, sequences or mixed structure.

Returns a tuple with of two: a dict (last match: {key: value}) and a list (all matches: [key, value, absolute index including original dictionary name]) 
For single values of array the dict is empty (no pairs "key":"value", but only "value")
