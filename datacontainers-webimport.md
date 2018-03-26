### Container objects and importing data(local and web) 

Various data containers available:

* **Lists** -One of the most fundamental data structures in any language is the array. Python doesn't have a native array data structure, but it has the list which is much more general and can be used as a multidimensional array quite easily.
* **Dictionaries** -  consists of data in key-value pairs
* **Tuples** - Immutable objects, can contain multiple data types
* **Sets** - Contains only distinct values
* **Dataframes** (`pandas`) - Like a matrix, but different data types can be present 

``` python
import pandas as pd

ls= [1,2,3,4,'X'] #list
dict={1:'a',2:'b'},3:'c'} #dictionary
tup=(1,2,3) #tuple
x=set([1,1,2,3]) 
print(x) #will result to {1,2,3}
df= pd.DataFrame(data=[[1,2],[3,4]]) #Dataframe
```
For extracting data from dictionaries, say for instance the dictionary `dict` defined previously. Using `dict['d']`will give an error as there is not key named `'d'` in the dictionary. The `.get()` method comes in very handy in such cases. Say you have a script that is iterating over a list of key values and one key isn't present in the dictionary, in such cases using the `.get()` method (returns  `None` by default) helps us handle the erros. The return can also be customzed in case a key is not found. For example, using `dict.get('d','')` would return an empty string 


#### Importing local data
```python

file=open('filename.txt',mode='r')
file.read() # prints the entire txt file
file.readline() # prints line by line
file.close()

import pandas as pd
data=pd.read_csv(filename)
data.head()
```

#### Importing data from web - Important modules

* `urllib`
* `requests`
* `BeautfulSoup`
```python
from  urllib.request import urlretrieve
urlretrieve("https://www.somewebsite.com/files/some.csv",'some.csv')

from urllib.open import urlopen,Request
url="https://www.somewebsite.com"
r=requests.get(url)
response=urlopen(request)
html=response.read()
response.close()

#Using requests
import requests
url="https://www.somewebsite.com"
r=requests.get(url) #Single line
html=r.text #Get the html string

from bs4 import BeautifulSoup
soup=BeautifulSoup(html)
print(soup.prettify())
``` 
