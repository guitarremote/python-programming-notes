### Python Basics Notes

Various data containers available:

* **Lists** 
* **Dictionaries** -  concists of data in key-value pairs
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
Other important basics

* **Functions**
* **Control-flows**
* **if-else**
* **Loops (for & while)**
* **List comprehensions**
* **Lambda functions** 

```python
```

Importing local data
```python
!ls #explore working directory
file=open('filename.txt',mode='r')
file.read() # prints the entire txt file
file.readline() # prints line by line
file.close()

import pandas as pd
data=pd.read_csv(filename)
data.head()
```

Importing data from web - Important modules

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
