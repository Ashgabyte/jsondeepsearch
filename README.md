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
For single values of array the dict is empty (no pairs {key: value}, but only found values in a list)

> Do not use expression as first parameter by calling these functions, use only names of dictionaries.

Example of using:

1) Read JSON file and convert it to dict: 
```
import json
myfile = open("file.json"), "r")
mytext = myfile.read()
myjson = json.loads(mytext)
myfile.close()
```

2) Then call functions:
```
import 
mykey = "name" # OR
mykey = "uuid"
result = lookforkey(myjson, "any")
# result[0] - a dict with pair {key:value} - last natch
# result[1] - a list with [key, value, index] - all matches
```

```
import 
myvalue = "Max" # OR
myvalue = 123 # OR
myvalue = [0, 10, 20] # OR
myvalue = {'properties':{'length': 20, 'width': 10, 'height': 5}} # OR
myvalue = (36.6, 97.88) # OR
myvalue = {'array':[1, 2, 3]}
result = lookforvalue(myjson, myvalue)
# result[0] - a dict with pair {key:value} - last natch
# result[1] - a list with [key, value, index] - all matches
```
