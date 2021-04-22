```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter
```


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter
data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')
data.sample(5)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>imdb_id</th>
      <th>budget</th>
      <th>revenue</th>
      <th>original_title</th>
      <th>cast</th>
      <th>director</th>
      <th>tagline</th>
      <th>overview</th>
      <th>runtime</th>
      <th>genres</th>
      <th>production_companies</th>
      <th>release_date</th>
      <th>vote_average</th>
      <th>release_year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>486</th>
      <td>tt1423894</td>
      <td>30000000</td>
      <td>8454301</td>
      <td>Barney's Version</td>
      <td>Paul Giamatti|Dustin Hoffman|Rosamund Pike|Min...</td>
      <td>Richard J. Lewis</td>
      <td>First he got married. Then he got married agai...</td>
      <td>The picaresque and touching story of the polit...</td>
      <td>134</td>
      <td>Comedy|Drama</td>
      <td>Serendipity Point Films</td>
      <td>10/26/2010</td>
      <td>6.9</td>
      <td>2010</td>
    </tr>
    <tr>
      <th>1401</th>
      <td>tt0432291</td>
      <td>18000000</td>
      <td>46201432</td>
      <td>The Fog</td>
      <td>Tom Welling|Maggie Grace|Selma Blair|DeRay Dav...</td>
      <td>Rupert Wainwright</td>
      <td>Their PAST Has Come Back To HAUNT THEM</td>
      <td>Trapped within an eerie mist, the residents of...</td>
      <td>100</td>
      <td>Horror|Thriller</td>
      <td>Revolution Studios|Debra Hill Productions</td>
      <td>10/14/2005</td>
      <td>4.2</td>
      <td>2005</td>
    </tr>
    <tr>
      <th>186</th>
      <td>tt0864835</td>
      <td>145000000</td>
      <td>272912430</td>
      <td>Mr. Peabody &amp; Sherman</td>
      <td>Ty Burrell|Max Charles|Ariel Winter|Allison Ja...</td>
      <td>Rob Minkoff</td>
      <td>He's Leaving His Mark On History</td>
      <td>A young boy and his dog, who happens to have a...</td>
      <td>92</td>
      <td>Animation|Adventure|Family</td>
      <td>20th Century Fox</td>
      <td>02/07/2014</td>
      <td>6.8</td>
      <td>2014</td>
    </tr>
    <tr>
      <th>403</th>
      <td>tt0985694</td>
      <td>20000000</td>
      <td>31327899</td>
      <td>Machete</td>
      <td>Danny Trejo|Michelle Rodriguez|Jessica Alba|Ro...</td>
      <td>Robert Rodriguez|Ethan Maniquis</td>
      <td>He was given an offer he couldn't refuse...</td>
      <td>After being set-up and betrayed by the man who...</td>
      <td>105</td>
      <td>Action|Comedy|Thriller</td>
      <td>Dune Entertainment|Dune Entertainment III|Trou...</td>
      <td>09/01/2010</td>
      <td>6.2</td>
      <td>2010</td>
    </tr>
    <tr>
      <th>1718</th>
      <td>tt0211933</td>
      <td>86000000</td>
      <td>14373825</td>
      <td>Awake</td>
      <td>Hayden Christensen|Jessica Alba|Terrence Howar...</td>
      <td>Joby Harold</td>
      <td>Every year, one in 700 people wake up during s...</td>
      <td>While undergoing heart surgery, a man experien...</td>
      <td>84</td>
      <td>Thriller|Crime|Mystery</td>
      <td>The Weinstein Company|Open City Films|GreeneSt...</td>
      <td>11/28/2007</td>
      <td>6.3</td>
      <td>2007</td>
    </tr>
  </tbody>
</table>
</div>




```python
data.describe()
```

# Предобработка


```python
answers = {} # создадим словарь для ответов

# тут другие ваши предобработки колонок например:

#the time given in the dataset is in string format.
#So we need to change this in datetime format
# ...

data['profit'] = data['revenue'] - data['budget']
```

# 1. У какого фильма из списка самый большой бюджет?

Использовать варианты ответов в коде решения запрещено.    
Вы думаете и в жизни у вас будут варианты ответов?)


```python
# в словарь вставляем номер вопроса и ваш ответ на него
# Пример: 
answers['1'] = '2. Spider-Man 3 (tt0413300)'
# запишите свой вариант ответа
answers['1'] = '...'
# если ответили верно, можете добавить комментарий со значком "+"
```


```python
# тут пишем ваш код для решения данного вопроса:
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter
data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')
data2 = data.loc[data['budget'] == data.budget.max()]
data.loc[data['budget'] == data.budget.max()]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>imdb_id</th>
      <th>budget</th>
      <th>revenue</th>
      <th>original_title</th>
      <th>cast</th>
      <th>director</th>
      <th>tagline</th>
      <th>overview</th>
      <th>runtime</th>
      <th>genres</th>
      <th>production_companies</th>
      <th>release_date</th>
      <th>vote_average</th>
      <th>release_year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>723</th>
      <td>tt1298650</td>
      <td>380000000</td>
      <td>1021683000</td>
      <td>Pirates of the Caribbean: On Stranger Tides</td>
      <td>Johnny Depp|PenÃ©lope Cruz|Geoffrey Rush|Ian M...</td>
      <td>Rob Marshall</td>
      <td>Live Forever Or Die Trying.</td>
      <td>Captain Jack Sparrow crosses paths with a woma...</td>
      <td>136</td>
      <td>Adventure|Action|Fantasy</td>
      <td>Walt Disney Pictures|Jerry Bruckheimer Films|M...</td>
      <td>05/11/2011</td>
      <td>6.3</td>
      <td>2011</td>
    </tr>
  </tbody>
</table>
</div>



ВАРИАНТ 2


```python
# можно добавлять разные варианты решения
```

# 2. Какой из фильмов самый длительный (в минутах)?


```python
# думаю логику работы с этим словарем вы уже поняли, 
# по этому не буду больше его дублировать
answers['2'] = '...'
```


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter
data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')
data = data.loc[data['runtime'] == data.runtime.max()]
data.loc[data['runtime'] == data.runtime.max()]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>imdb_id</th>
      <th>budget</th>
      <th>revenue</th>
      <th>original_title</th>
      <th>cast</th>
      <th>director</th>
      <th>tagline</th>
      <th>overview</th>
      <th>runtime</th>
      <th>genres</th>
      <th>production_companies</th>
      <th>release_date</th>
      <th>vote_average</th>
      <th>release_year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1157</th>
      <td>tt0279111</td>
      <td>56000000</td>
      <td>12923936</td>
      <td>Gods and Generals</td>
      <td>Stephen Lang|Jeff Daniels|Robert Duvall|Kevin ...</td>
      <td>Ronald F. Maxwell</td>
      <td>The nations heart was touched by...</td>
      <td>The film centers mostly around the personal an...</td>
      <td>214</td>
      <td>Drama|History|War</td>
      <td>Turner Pictures|Antietam Filmworks</td>
      <td>2/21/2003</td>
      <td>5.8</td>
      <td>2003</td>
    </tr>
  </tbody>
</table>
</div>



# 3. Какой из фильмов самый короткий (в минутах)?






```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter
data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')
data = data.loc[data['runtime'] == data.runtime.min()]
data.loc[data['runtime'] == data.runtime.min()]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>imdb_id</th>
      <th>budget</th>
      <th>revenue</th>
      <th>original_title</th>
      <th>cast</th>
      <th>director</th>
      <th>tagline</th>
      <th>overview</th>
      <th>runtime</th>
      <th>genres</th>
      <th>production_companies</th>
      <th>release_date</th>
      <th>vote_average</th>
      <th>release_year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>768</th>
      <td>tt1449283</td>
      <td>30000000</td>
      <td>14460000</td>
      <td>Winnie the Pooh</td>
      <td>Jim Cummings|Travis Oates|Jim Cummings|Bud Luc...</td>
      <td>Stephen Anderson|Don Hall</td>
      <td>Oh Pooh.</td>
      <td>During an ordinary day in Hundred Acre Wood, W...</td>
      <td>63</td>
      <td>Animation|Family</td>
      <td>Walt Disney Pictures|Walt Disney Animation Stu...</td>
      <td>4/13/2011</td>
      <td>6.8</td>
      <td>2011</td>
    </tr>
  </tbody>
</table>
</div>



# 4. Какова средняя длительность фильмов?



```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter
data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')
data.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>budget</th>
      <th>revenue</th>
      <th>runtime</th>
      <th>vote_average</th>
      <th>release_year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1.889000e+03</td>
      <td>1.889000e+03</td>
      <td>1889.000000</td>
      <td>1889.000000</td>
      <td>1889.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>5.431083e+07</td>
      <td>1.553653e+08</td>
      <td>109.658549</td>
      <td>6.140762</td>
      <td>2007.860773</td>
    </tr>
    <tr>
      <th>std</th>
      <td>4.858721e+07</td>
      <td>2.146698e+08</td>
      <td>18.017041</td>
      <td>0.764763</td>
      <td>4.468841</td>
    </tr>
    <tr>
      <th>min</th>
      <td>5.000000e+06</td>
      <td>2.033165e+06</td>
      <td>63.000000</td>
      <td>3.300000</td>
      <td>2000.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2.000000e+07</td>
      <td>3.456058e+07</td>
      <td>97.000000</td>
      <td>5.600000</td>
      <td>2004.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>3.800000e+07</td>
      <td>8.361541e+07</td>
      <td>107.000000</td>
      <td>6.100000</td>
      <td>2008.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>7.200000e+07</td>
      <td>1.782626e+08</td>
      <td>120.000000</td>
      <td>6.600000</td>
      <td>2012.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3.800000e+08</td>
      <td>2.781506e+09</td>
      <td>214.000000</td>
      <td>8.100000</td>
      <td>2015.000000</td>
    </tr>
  </tbody>
</table>
</div>



# 5. Каково медианное значение длительности фильмов? 


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter
data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')
data.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>budget</th>
      <th>revenue</th>
      <th>runtime</th>
      <th>vote_average</th>
      <th>release_year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1.889000e+03</td>
      <td>1.889000e+03</td>
      <td>1889.000000</td>
      <td>1889.000000</td>
      <td>1889.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>5.431083e+07</td>
      <td>1.553653e+08</td>
      <td>109.658549</td>
      <td>6.140762</td>
      <td>2007.860773</td>
    </tr>
    <tr>
      <th>std</th>
      <td>4.858721e+07</td>
      <td>2.146698e+08</td>
      <td>18.017041</td>
      <td>0.764763</td>
      <td>4.468841</td>
    </tr>
    <tr>
      <th>min</th>
      <td>5.000000e+06</td>
      <td>2.033165e+06</td>
      <td>63.000000</td>
      <td>3.300000</td>
      <td>2000.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2.000000e+07</td>
      <td>3.456058e+07</td>
      <td>97.000000</td>
      <td>5.600000</td>
      <td>2004.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>3.800000e+07</td>
      <td>8.361541e+07</td>
      <td>107.000000</td>
      <td>6.100000</td>
      <td>2008.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>7.200000e+07</td>
      <td>1.782626e+08</td>
      <td>120.000000</td>
      <td>6.600000</td>
      <td>2012.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3.800000e+08</td>
      <td>2.781506e+09</td>
      <td>214.000000</td>
      <td>8.100000</td>
      <td>2015.000000</td>
    </tr>
  </tbody>
</table>
</div>



# 6. Какой самый прибыльный фильм?
#### Внимание! Здесь и далее под «прибылью» или «убытками» понимается разность между сборами и бюджетом фильма. (прибыль = сборы - бюджет) в нашем датасете это будет (profit = revenue - budget) 


```python
# лучше код получения столбца profit вынести в Предобработку что в начале
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data.groupby('original_title')['revenue'].agg(['sum']).sort_values('sum', ascending=False).head(5)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>sum</th>
    </tr>
    <tr>
      <th>original_title</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Avatar</th>
      <td>2781505847</td>
    </tr>
    <tr>
      <th>Star Wars: The Force Awakens</th>
      <td>2068178225</td>
    </tr>
    <tr>
      <th>The Avengers</th>
      <td>1519557910</td>
    </tr>
    <tr>
      <th>Jurassic World</th>
      <td>1513528810</td>
    </tr>
    <tr>
      <th>Furious 7</th>
      <td>1506249360</td>
    </tr>
  </tbody>
</table>
</div>



# 7. Какой фильм самый убыточный? 


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data['loss'] = data['budget'] - data['revenue']

loss_release = data[(data['original_title']).revenue.min()
data[(data.revenue == loss_release) & (data['original_title'])].original_title.unique()
```


      File "<ipython-input-23-b46c91fa14b4>", line 12
        data[(data.revenue == loss_release) & (data['original_title'])].original_title.unique()
        ^
    SyntaxError: invalid syntax
    


# 8. У скольких фильмов из датасета объем сборов оказался выше бюджета?


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data['profit'] = data['revenue'] - data['budget']

data2 = data[data['profit']].value_counts()

data.groupby('genres')['revenue'].agg(['sum']).sort_values('sum', ascending=False)
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-10-45663b6ad61b> in <module>
          9 data['profit'] = data['revenue'] - data['budget']
         10 
    ---> 11 data2 = data[data['profit']].value_counts()
    

    ~\Anaconda3\lib\site-packages\pandas\core\frame.py in __getitem__(self, key)
       2906             if is_iterator(key):
       2907                 key = list(key)
    -> 2908             indexer = self.loc._get_listlike_indexer(key, axis=1, raise_missing=True)[1]
       2909 
       2910         # take() does not accept boolean indexers
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexing.py in _get_listlike_indexer(self, key, axis, raise_missing)
       1252             keyarr, indexer, new_indexer = ax._reindex_non_unique(keyarr)
       1253 
    -> 1254         self._validate_read_indexer(keyarr, indexer, axis, raise_missing=raise_missing)
       1255         return keyarr, indexer
       1256 
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexing.py in _validate_read_indexer(self, key, indexer, axis, raise_missing)
       1296             if missing == len(indexer):
       1297                 axis_name = self.obj._get_axis_name(axis)
    -> 1298                 raise KeyError(f"None of [{key}] are in the [{axis_name}]")
       1299 
       1300             # We (temporarily) allow for some missing keys with .loc, except in
    

    KeyError: "None of [Int64Index([1363528810,  228436354,  185238201, 1868178225, 1316249360,\n             397950503,  285603537,  487380321, 1082730962,  678708609,\n            ...\n              -6439124,  -19814759,  -10300000,  -11627590,   12609995,\n              82299717,   -8444012,  -40865180,   -3962091,   -9782502],\n           dtype='int64', length=1889)] are in the [columns]"


# 9. Какой фильм оказался самым кассовым в 2008 году?


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

movie = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

max_release = movie[(movie['release_year'] == 2008)].revenue.max()
movie[(movie.revenue == max_release) & (movie['release_year'] == 2008)].original_title.unique()
```




    array(['The Dark Knight'], dtype=object)



# 10. Самый убыточный фильм за период с 2012 по 2014 г. (включительно)?



```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data['loss'] = data['budget'] - data['revenue']

movie = data[data.release_year.isin([2012, 2013, 2014])].sort_values(by='loss', ascending=True)
```

# 11. Какого жанра фильмов больше всего?


```python
# эту задачу тоже можно решать разными подходами, попробуй реализовать разные варианты
# если будешь добавлять функцию - выноси ее в предобработку что в начале
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

Counter(data.genres.str.split('|').sum()).most_common(1)
```




    [('Drama', 782)]



ВАРИАНТ 2


```python

```

# 12. Фильмы какого жанра чаще всего становятся прибыльными? 


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data.groupby('genres')['revenue'].agg(['sum']).sort_values('sum', ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>sum</th>
    </tr>
    <tr>
      <th>genres</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Comedy</th>
      <td>13824627476</td>
    </tr>
    <tr>
      <th>Drama</th>
      <td>8387405274</td>
    </tr>
    <tr>
      <th>Comedy|Romance</th>
      <td>7780858585</td>
    </tr>
    <tr>
      <th>Adventure|Fantasy|Action</th>
      <td>7428942514</td>
    </tr>
    <tr>
      <th>Animation|Family</th>
      <td>6143878732</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>Mystery|Drama|Crime|Thriller|Horror</th>
      <td>3533227</td>
    </tr>
    <tr>
      <th>Comedy|Music|War</th>
      <td>3020664</td>
    </tr>
    <tr>
      <th>Crime|Horror|Thriller</th>
      <td>2626800</td>
    </tr>
    <tr>
      <th>Action|Adventure|Fantasy|Horror</th>
      <td>2405420</td>
    </tr>
    <tr>
      <th>Drama|Music|Adventure|Fantasy</th>
      <td>2333684</td>
    </tr>
  </tbody>
</table>
<p>652 rows × 1 columns</p>
</div>



# 13. У какого режиссера самые большие суммарные кассовые сборы?


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data.groupby('director')['revenue'].agg(['sum']).sort_values('sum', ascending=False)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>sum</th>
    </tr>
    <tr>
      <th>director</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Peter Jackson</th>
      <td>6490593685</td>
    </tr>
    <tr>
      <th>Christopher Nolan</th>
      <td>4167548502</td>
    </tr>
    <tr>
      <th>David Yates</th>
      <td>4154295625</td>
    </tr>
    <tr>
      <th>Michael Bay</th>
      <td>3886938960</td>
    </tr>
    <tr>
      <th>J.J. Abrams</th>
      <td>3579169916</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
    </tr>
    <tr>
      <th>David MichÃ´d</th>
      <td>2295423</td>
    </tr>
    <tr>
      <th>Steven Shainberg</th>
      <td>2281089</td>
    </tr>
    <tr>
      <th>Paul Schrader</th>
      <td>2062066</td>
    </tr>
    <tr>
      <th>Keanu Reeves</th>
      <td>2054941</td>
    </tr>
    <tr>
      <th>Simon Hunter</th>
      <td>2033165</td>
    </tr>
  </tbody>
</table>
<p>957 rows × 1 columns</p>
</div>



# 14. Какой режисер снял больше всего фильмов в стиле Action?


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data[data.genres.str.contains('Action')].director.str.split('|').explode().value_counts().index[0]
```




    'Robert Rodriguez'



# 15. Фильмы с каким актером принесли самые высокие кассовые сборы в 2012 году? 


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data_2012 = data[data.release_year == 2012]
data_2012.cast.apply(lambda x: x.split(', '))
data_2012 = data_2012.explode('cast')
display(data_2012.groupby('cast')['revenue'].sum().sort_values(ascending=False).head(1))
```


    cast
    Robert Downey Jr.|Chris Evans|Mark Ruffalo|Chris Hemsworth|Scarlett Johansson    1519557910
    Name: revenue, dtype: int64


# 16. Какой актер снялся в большем количестве высокобюджетных фильмов?


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data2 = data.copy
data2 = data2.cast.apply(lambda x: x.split(','))
data2 = data2.explode('cast')
display(data2.groupby('cast')['budget'].sum().sort_values(ascending=False).head(10))
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-146-60a7b61fe6cc> in <module>
          8 
          9 data2 = data.copy
    ---> 10 data2 = data2.cast.apply(lambda x: x.split(','))
         11 data2 = data2.explode('cast')
         12 display(data2.groupby('cast')['budget'].sum().sort_values(ascending=False).head(10))
    

    AttributeError: 'function' object has no attribute 'cast'


# 17. В фильмах какого жанра больше всего снимался Nicolas Cage? 


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data_cage = movie.copy()
data_cage['all_genres'] = data_cage.genres.str.split('|')
data_cage['actor'] = data_cage[data_cage['cast'].str.contains('Nicolas Cage', na=False)]
data_cage = data_cage[['all_genres', 'actor']]
data_cage
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    ~\Anaconda3\lib\site-packages\pandas\core\indexes\base.py in get_loc(self, key, method, tolerance)
       2894             try:
    -> 2895                 return self._engine.get_loc(casted_key)
       2896             except KeyError as err:
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\index.pyx in pandas._libs.index.IndexEngine.get_loc()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.PyObjectHashTable.get_item()
    

    pandas\_libs\hashtable_class_helper.pxi in pandas._libs.hashtable.PyObjectHashTable.get_item()
    

    KeyError: 'actor'

    
    The above exception was the direct cause of the following exception:
    

    KeyError                                  Traceback (most recent call last)

    ~\Anaconda3\lib\site-packages\pandas\core\generic.py in _set_item(self, key, value)
       3573         try:
    -> 3574             loc = self._info_axis.get_loc(key)
       3575         except KeyError:
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexes\base.py in get_loc(self, key, method, tolerance)
       2896             except KeyError as err:
    -> 2897                 raise KeyError(key) from err
       2898 
    

    KeyError: 'actor'

    
    During handling of the above exception, another exception occurred:
    

    ValueError                                Traceback (most recent call last)

    <ipython-input-133-5a3ab592c97b> in <module>
          9 data_cage = movie.copy()
         10 data_cage['all_genres'] = data_cage.genres.str.split('|')
    ---> 11 data_cage['actor'] = data_cage[data_cage['cast'].str.contains('Nicolas Cage', na=False)]
         12 data_cage = data_cage[['all_genres', 'actor']]
         13 data_cage
    

    ~\Anaconda3\lib\site-packages\pandas\core\frame.py in __setitem__(self, key, value)
       3038         else:
       3039             # set column
    -> 3040             self._set_item(key, value)
       3041 
       3042     def _setitem_slice(self, key: slice, value):
    

    ~\Anaconda3\lib\site-packages\pandas\core\frame.py in _set_item(self, key, value)
       3115         self._ensure_valid_index(value)
       3116         value = self._sanitize_column(key, value)
    -> 3117         NDFrame._set_item(self, key, value)
       3118 
       3119         # check if we are modifying a copy
    

    ~\Anaconda3\lib\site-packages\pandas\core\generic.py in _set_item(self, key, value)
       3575         except KeyError:
       3576             # This item wasn't present, just insert at end
    -> 3577             self._mgr.insert(len(self._info_axis), key, value)
       3578             return
       3579 
    

    ~\Anaconda3\lib\site-packages\pandas\core\internals\managers.py in insert(self, loc, item, value, allow_duplicates)
       1187             value = _safe_reshape(value, (1,) + value.shape)
       1188 
    -> 1189         block = make_block(values=value, ndim=self.ndim, placement=slice(loc, loc + 1))
       1190 
       1191         for blkno, count in _fast_count_smallints(self.blknos[loc:]):
    

    ~\Anaconda3\lib\site-packages\pandas\core\internals\blocks.py in make_block(values, placement, klass, ndim, dtype)
       2720         values = DatetimeArray._simple_new(values, dtype=dtype)
       2721 
    -> 2722     return klass(values, ndim=ndim, placement=placement)
       2723 
       2724 
    

    ~\Anaconda3\lib\site-packages\pandas\core\internals\blocks.py in __init__(self, values, placement, ndim)
       2376             values = np.array(values, dtype=object)
       2377 
    -> 2378         super().__init__(values, ndim=ndim, placement=placement)
       2379 
       2380     @property
    

    ~\Anaconda3\lib\site-packages\pandas\core\internals\blocks.py in __init__(self, values, placement, ndim)
        128 
        129         if self._validate_ndim and self.ndim and len(self.mgr_locs) != len(self.values):
    --> 130             raise ValueError(
        131                 f"Wrong number of items passed {len(self.values)}, "
        132                 f"placement implies {len(self.mgr_locs)}"
    

    ValueError: Wrong number of items passed 15, placement implies 1


# 18. Самый убыточный фильм от Paramount Pictures


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data['loss'] = data['budget'] - data['revenue']

display(data['loss'], data['original_title'],[data.production_companies.str.contains('Paramount Pictures', na=False)])
```


    0      -1363528810
    1       -228436354
    2       -185238201
    3      -1868178225
    4      -1316249360
               ...    
    1884     -82299717
    1885       8444012
    1886      40865180
    1887       3962091
    1888       9782502
    Name: loss, Length: 1889, dtype: int64



    0                             Jurassic World
    1                         Mad Max: Fury Road
    2                                  Insurgent
    3               Star Wars: The Force Awakens
    4                                  Furious 7
                            ...                 
    1884                                   X-Men
    1885                      The Little Vampire
    1886    The Adventures of Rocky & Bullwinkle
    1887                              Hanging Up
    1888                            The In Crowd
    Name: original_title, Length: 1889, dtype: object



    [0       False
     1       False
     2       False
     3       False
     4       False
             ...  
     1884    False
     1885    False
     1886    False
     1887    False
     1888    False
     Name: production_companies, Length: 1889, dtype: bool]


# 19. Какой год стал самым успешным по суммарным кассовым сборам?


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data['profit'] = data['revenue'] - data['budget']

display(data.groupby(data['release_year']).data['profit'].sum().sort_values(ascending=False))
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-16-1a5853545ec0> in <module>
          9 data['profit'] = data['revenue'] - data['budget']
         10 
    ---> 11 display(data.groupby(data['release_year']).data['profit'].sum().sort_values(ascending=False))
    

    ~\Anaconda3\lib\site-packages\pandas\core\groupby\groupby.py in __getattr__(self, attr)
        701             return self[attr]
        702 
    --> 703         raise AttributeError(
        704             f"'{type(self).__name__}' object has no attribute '{attr}'"
        705         )
    

    AttributeError: 'DataFrameGroupBy' object has no attribute 'data'


# 20. Какой самый прибыльный год для студии Warner Bros?


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data['profit'] = data['revenue'] - data['budget']

display(data[data.production_companies.str.contains('Warner Bros', na=False)].groupby(data['release_year'])['profit'].sum().sort_values(ascending=False))
```


    release_year
    2014    2295464519
    2007    2201675217
    2008    2134595031
    2010    1974712985
    2011    1871393682
    2003    1855493377
    2009    1822454136
    2013    1636453400
    2004    1631933725
    2005    1551980298
    2001    1343545668
    2012    1258020056
    2002    1022709901
    2015     870368348
    2006     620170743
    2000     452631386
    Name: profit, dtype: int64


# 21. В каком месяце за все годы суммарно вышло больше всего фильмов?


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

display(data[data.release_date.dt.month].sum().sort_values(ascending=False))
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-14-498d7d3e20e7> in <module>
          7 data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')
          8 
    ----> 9 display(data[data.release_date.dt.month].sum().sort_values(ascending=False))
    

    ~\Anaconda3\lib\site-packages\pandas\core\generic.py in __getattr__(self, name)
       5133             or name in self._accessors
       5134         ):
    -> 5135             return object.__getattribute__(self, name)
       5136         else:
       5137             if self._info_axis._can_hold_identifiers_and_holds_name(name):
    

    ~\Anaconda3\lib\site-packages\pandas\core\accessor.py in __get__(self, obj, cls)
        185             # we're accessing the attribute of the class, i.e., Dataset.geo
        186             return self._accessor
    --> 187         accessor_obj = self._accessor(obj)
        188         # Replace the property with the accessor object. Inspired by:
        189         # https://www.pydanny.com/cached-property.html
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexes\accessors.py in __new__(cls, data)
        478             return PeriodProperties(data, orig)
        479 
    --> 480         raise AttributeError("Can only use .dt accessor with datetimelike values")
    

    AttributeError: Can only use .dt accessor with datetimelike values


# 22. Сколько суммарно вышло фильмов летом? (за июнь, июль, август)


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

summer_movie = data[data.release_date.dt.month.isin(['6', '7', '8'])].copy()
summer_movie_count = summer_movie.value_counts()
print(summer_movie, summer_movie_count)
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-12-becdc4e8bbc5> in <module>
          7 data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')
          8 
    ----> 9 summer_movie = data[data.release_date.dt.month.isin(['6', '7', '8'])].copy()
         10 summer_movie_count = summer_movie.value_counts()
         11 print(summer_movie, summer_movie_count)
    

    ~\Anaconda3\lib\site-packages\pandas\core\generic.py in __getattr__(self, name)
       5133             or name in self._accessors
       5134         ):
    -> 5135             return object.__getattribute__(self, name)
       5136         else:
       5137             if self._info_axis._can_hold_identifiers_and_holds_name(name):
    

    ~\Anaconda3\lib\site-packages\pandas\core\accessor.py in __get__(self, obj, cls)
        185             # we're accessing the attribute of the class, i.e., Dataset.geo
        186             return self._accessor
    --> 187         accessor_obj = self._accessor(obj)
        188         # Replace the property with the accessor object. Inspired by:
        189         # https://www.pydanny.com/cached-property.html
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexes\accessors.py in __new__(cls, data)
        478             return PeriodProperties(data, orig)
        479 
    --> 480         raise AttributeError("Can only use .dt accessor with datetimelike values")
    

    AttributeError: Can only use .dt accessor with datetimelike values


# 23. Для какого режиссера зима – самое продуктивное время года? 


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter
from datetime import date as dt

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

winter_movie = data[data.release_date.dt.month.isin(release_date=['1', '2', '12'], na=False)].copy()
winter_movie_director = winter_movie.director.str.split('|')
winter_movie = winter_movie.explode('director')
print(winter_movie.director.value_counts().sort_values(ascending=False).head(10))
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    <ipython-input-176-921bf50a5718> in <module>
          8 data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')
          9 
    ---> 10 winter_movie = data[data.release_date.dt.month.isin(release_date=['1', '2', '12'], na=False)].copy()
         11 winter_movie_director = winter_movie.director.str.split('|')
         12 winter_movie = winter_movie.explode('director')
    

    ~\Anaconda3\lib\site-packages\pandas\core\generic.py in __getattr__(self, name)
       5133             or name in self._accessors
       5134         ):
    -> 5135             return object.__getattribute__(self, name)
       5136         else:
       5137             if self._info_axis._can_hold_identifiers_and_holds_name(name):
    

    ~\Anaconda3\lib\site-packages\pandas\core\accessor.py in __get__(self, obj, cls)
        185             # we're accessing the attribute of the class, i.e., Dataset.geo
        186             return self._accessor
    --> 187         accessor_obj = self._accessor(obj)
        188         # Replace the property with the accessor object. Inspired by:
        189         # https://www.pydanny.com/cached-property.html
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexes\accessors.py in __new__(cls, data)
        478             return PeriodProperties(data, orig)
        479 
    --> 480         raise AttributeError("Can only use .dt accessor with datetimelike values")
    

    AttributeError: Can only use .dt accessor with datetimelike values



```python

```

# 24. Какая студия дает самые длинные названия своим фильмам по количеству символов?


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data['title_length'] = data['original_title'].map(lambda x: len(x))
companies = data['production_companies'].str.split('|').explode().unique()
sum_gen = pd.Series(dtype='float', index=companies)
for comp in companies:
    sum_gen[comp] = data['title_length'][data['production_companies'].map(lambda x: True if comp in x else False)].mean()
sum_gen.sort_values(ascending=False).head()    
```




    Four By Two Productions      83.0
    Jim Henson Company, The      59.0
    Dos Corazones                47.0
    Museum Canada Productions    46.0
    Polsky Films                 46.0
    dtype: float64



# 25. Описание фильмов какой студии в среднем самые длинные по количеству слов?


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
from collections import Counter

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data['description'] = data['overview'].map(lambda x: len(x))
companies = data['production_companies'].str.split('|').explode().unique()
sum_gen = pd.Series(dtype='float', index=companies)
for comp in companies:
    sum_gen[comp] = data['description'][data['production_companies'].map(lambda x: True if comp in x else False)].mean()
sum_gen.sort_values(ascending=False).head() 
```




    Midnight Picture Show               1000.0
    Room 9 Entertainment                 964.0
    Brookwell-McNamara Entertainment     936.0
    Lions Gate Family Entertainment      909.0
    Crest Animation Productions          909.0
    dtype: float64



# 26. Какие фильмы входят в 1 процент лучших по рейтингу? 
по vote_average


```python
import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

data2 = data[data.vote_average.value_counts(bins=100, normalize=True)]
display(data2, ['original_title'])
```


    ---------------------------------------------------------------------------

    KeyError                                  Traceback (most recent call last)

    <ipython-input-174-8f7e49f5ec48> in <module>
          6 data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')
          7 
    ----> 8 data2 = data[data.vote_average.value_counts(bins=100, normalize=True)]
          9 display(data2, ['original_title'])
    

    ~\Anaconda3\lib\site-packages\pandas\core\frame.py in __getitem__(self, key)
       2906             if is_iterator(key):
       2907                 key = list(key)
    -> 2908             indexer = self.loc._get_listlike_indexer(key, axis=1, raise_missing=True)[1]
       2909 
       2910         # take() does not accept boolean indexers
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexing.py in _get_listlike_indexer(self, key, axis, raise_missing)
       1252             keyarr, indexer, new_indexer = ax._reindex_non_unique(keyarr)
       1253 
    -> 1254         self._validate_read_indexer(keyarr, indexer, axis, raise_missing=raise_missing)
       1255         return keyarr, indexer
       1256 
    

    ~\Anaconda3\lib\site-packages\pandas\core\indexing.py in _validate_read_indexer(self, key, indexer, axis, raise_missing)
       1296             if missing == len(indexer):
       1297                 axis_name = self.obj._get_axis_name(axis)
    -> 1298                 raise KeyError(f"None of [{key}] are in the [{axis_name}]")
       1299 
       1300             # We (temporarily) allow for some missing keys with .loc, except in
    

    KeyError: "None of [Float64Index([   0.0555849655902594,   0.05346744309158285,\n                0.05293806246691371,   0.05293806246691371,\n                 0.0513499205929063,   0.05082053996823716,\n                0.05029115934356802,  0.046585494970884066,\n                0.04446797247220752,   0.04446797247220752,\n               0.037586024351508734,  0.037056643726839596,\n                0.03335097935415564,    0.0328215987294865,\n               0.030174695606140816,  0.029645314981471677,\n               0.028586553732133403,  0.028586553732133403,\n               0.026998411858125994,  0.026998411858125994,\n               0.022763366860772894,  0.021175224986765485,\n                0.02011646373742721,   0.01270513499205929,\n               0.012175754367390153,  0.011646373742721016,\n                0.01111699311805188,  0.009528851244044468,\n               0.008999470619375331,  0.007411328745367919,\n               0.006881948120698782,  0.005823186871360508,\n               0.004764425622022234,  0.004764425622022234,\n               0.004764425622022234,  0.004235044997353097,\n              0.0026469031233456856, 0.0021175224986765486,\n              0.0021175224986765486, 0.0021175224986765486,\n              0.0021175224986765486, 0.0010587612493382743,\n              0.0010587612493382743, 0.0010587612493382743,\n              0.0010587612493382743, 0.0005293806246691371,\n              0.0005293806246691371,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0,\n                                0.0,                   0.0],\n             dtype='float64')] are in the [columns]"


# 27. Какие актеры чаще всего снимаются в одном фильме вместе?


ВАРИАНТ 2

# Submission


```python
# в конце можно посмотреть свои ответы к каждому вопросу

import numpy as np
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
import itertools as it

data = pd.read_csv('C:/Users/olga.QCT/.jupyter/movie_bd_v5.csv')

def stringtolist(string):
    result = string.str.split('|')
    return result
from collections import Counter
data['cast'] = stringtolist(data['cast'])
actor_pairs = []
for i in range(0, len(data)):
    for item in it.combinations(data['cast'][i], 2):
        actor_pairs.append(item)
Counter(actor_pairs).most_common(1)
```




    [(('Daniel Radcliffe', 'Rupert Grint'), 8)]




```python
# и убедиться что ни чего не пропустил)
len(answers)
```


```python

```


```python

```
