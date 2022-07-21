# jsondeepsearch

Recursive deep search for keys or values in JSON structured nested and mixed python dictionary.

> There is a small difference between JSON and python dictionaries: in JSON keys are only strings like "key".


## functions:

``` lookforkey(jsondict, key) ```

Search the key in dictionary. The key is a string in quotes like "key".

Returns a tuple of two: a ```dict``` (last match: ```{key:value}```) and a ```list``` (all matches: ```[key, value, original dict name with absolute indexes]```)) 

``` lookforvalue(jsondict, value) ```

Search the value in dictionary. The value can be any type of variables, sequences or mixed structure. 

Returns a tuple of two: a ```dict``` (last match: ```{key: value}```) and a ```list``` (all matches: ```[key, value, original dict name with absolute indexes]```). 
For single values of array the dict is empty (no pairs {key: value}, but only "value")

> Do not use expression as first parameter by calling these functions, use only names of dictionaries.

1) Read JSON file and convert it to dict: 
```
import json
myfile = open("file.json"), "r")
mytext = myfile.read()
myjson = json.loads(mytext)
myfile.close()
```

Then call functions
```
import 
result = lookforkey(myjson, "any")
result = lookforvalue(myjson, *any*)
```

