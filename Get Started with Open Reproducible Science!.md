---

1. answer
2. answer
3. answer

I can write clean code by:
  * `YOUR ANSWER HERE`
answer

Advantages of clean code include:
  * `YOUR ANSWER HERE` answer woo


```python
#can't get this to work :(
import pandas as pd
```

The test cell below will tell you if you completed the task successfully when you run it. **Do not try to modify any test cells as our software we use to give you feedback, nbgrader, will be grumpy about that.** If a test cell isn't working, check that you ran your code **immediately before** running the test.


```python
points = 0
try:
    pd.DataFrame()
    points += 5
    print('\u2705 Great work! You correctly imported the pandas library.')
except:
    print('\u274C Oops - pandas was not imported correctly.')
print('You earned {} of 5 points for importing pandas'.format(points))
```

    ✅ Great work! You correctly imported the pandas library.
    You earned 5 of 5 points for importing pandas


**YOUR DATA DESCRIPTION AND CITATION HERE** answer


```python

ncieclimatedata_url = (
    'https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/'
    'time-series/USW00024090/tmax/ann/1/1940-2023.csv')

ncieclimatedata_url    

```




    'https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/time-series/USW00024090/tmax/ann/1/1940-2023.csv'




```python
# List all current variables
%whos
```

    Variable              Type         Data/Info
    --------------------------------------------
    dataframe             DataFrame        Date  Max_Annual_Temp<...>\n\n[74 rows x 2 columns]
    max_temp_df           DataFrame        Date  Max_Annual_Temp<...>\n\n[74 rows x 2 columns]
    ncieclimatedata_url   str          https://www.ncei.noaa.gov<...>/tmax/ann/1/1940-2023.csv
    pd                    module       <module 'pandas' from '/o<...>ages/pandas/__init__.py'>
    points                int          5
    summary               list         n=2
    tmax_df_resp          DataFrame        Date  Max_Annual_Temp<...>\n\n[74 rows x 2 columns]



```python
#download
max_temp_df = pd.read_csv(ncieclimatedata_url, header=3, names=['Date', 'Max_Annual_Temp'])
max_temp_df

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
      <th>Date</th>
      <th>Max_Annual_Temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>194912</td>
      <td>58.1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>195012</td>
      <td>55.3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>195112</td>
      <td>54.4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>195212</td>
      <td>59.2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>195312</td>
      <td>59.6</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>201812</td>
      <td>57.2</td>
    </tr>
    <tr>
      <th>70</th>
      <td>201912</td>
      <td>54.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>202012</td>
      <td>61.8</td>
    </tr>
    <tr>
      <th>72</th>
      <td>202112</td>
      <td>62.1</td>
    </tr>
    <tr>
      <th>73</th>
      <td>202212</td>
      <td>60.9</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [198562.0, 58.89]:
    points += 4
    print('\u2705 Great work! You correctly downloaded data.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for downloading data'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ✅ Great work! You correctly downloaded data.
    You earned 5 of 5 points for downloading data


Cleaning up your DataFrame

Take a look at your data. Do you want to use it as is, or does it need to be modified? The original author of this code thought it needed some modification, but didn't document their work very well.

Playing with code: your task

    Replace dataframe with the name of your dataframe whenever it appears.
    Run the code below.

Want an EXTRA CHALLENGE? Modify the code to be more expressive.

Rewrite the code below to select columns by name instead of by index. You might find the pandas User Guide section on slicing and dicing to be useful. However - don't worry if you can't figure this out yet! We're going to talk a lot about how to use pandas DataFrames.


```python
# Check that the data was imported into a pandas DataFrame
type(max_temp_df)
```




    pandas.core.frame.DataFrame




```python
# ncei has wacky years
max_temp_df.iloc[:,0] = max_temp_df.iloc[:,0] // 100
max_temp_df
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
      <th>Date</th>
      <th>Max_Annual_Temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>58.1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>55.3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>54.4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>59.2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>59.6</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>57.2</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>54.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>61.8</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>62.1</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>60.9</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>



<img src="https://static.thenounproject.com/png/5640527-200.png" width=20 style="float: left; padding: 3px" /> **What just happened?**
 1. `+`, `-`, `*` and `/` are known as **operators** in Python, and are used for arithmetic (add, subtract, multiply, and divide, respectively). What do you think the `//` **operator** does?
 
   `YOUR ANSWER HERE`
 2. `iloc`is an **attribute** of `DataFrame`s, meaning that it is available for all `DataFrame`s by attaching `.iloc` to its name. What do you think the `iloc` is?
 
   `YOUR ANSWER HERE`

    
  > HINT: It's ok if you can't figure out questions 3 and 4 yet. You can also list an experiment you tried. For example, you could run `4 // 2` and `4 // 3` and record the answers to help you figure out what `//` does. Or, you could change the `0` in `.iloc[:,0]` to `1` to see what happens. Play around with the code! It doesn't cost you anything to try things when you're coding.

Uh-oh, we have a variable problem

Try running the cell above a second time. And a third time. What do you notice?

YOUR ANSWER HERE

You don't have to do anything about this now - you can go Run all above (this is in the Cell menu in Jupyter Notebook) to reset. In the future, there are two approaches we recommend to address this sort of problem:

    Do not modify a DataFrame after it has been created - perform any changes you need in the same cell where you create the DataFrame using pd.read_csv().
    Save a copy of the DataFrame using the .copy() method of DataFrames and modify the copy (in the same cell)


```python
#convert to celcius
max_temp_df.iloc[:,1] = (max_temp_df.iloc[:,1] - 32) * 5 / 9
max_temp_df

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
      <th>Date</th>
      <th>Max_Annual_Temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>14.500000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>12.944444</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>12.444444</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>15.111111</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>15.333333</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>14.000000</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>12.611111</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>16.555556</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>16.722222</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>16.055556</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
max_temp_df.plot(x='Date', y='Max_Annual_Temp', title= "Maximum Annnual Temperature", ylabel="Degrees Celcius", xlabel="Date")

```




    <AxesSubplot:title={'center':'Maximum Annnual Temperature'}, xlabel='Date', ylabel='Degrees Celcius'>




    
![png](Get%20Started%20with%20Open%20Reproducible%20Science%21_files/Get%20Started%20with%20Open%20Reproducible%20Science%21_17_1.png)
    


## YOUR RAPID CITY PLOT HEADLINE HERE
Describe your plot in this cell in 2-3 sentences

## Your turn: pick a new location and/or measurement to plot
Below, recreate the workflow you just did in a place that interests you OR with a different measurement. You will need to make your own new Markdown and Code cells.
