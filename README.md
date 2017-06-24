
<center><img src="http://pandas.pydata.org/_static/pandas_logo.png" alt="pandas logo" width="500" height="125"></center>

# <font color="blue">Pandas Tutorial On Stock Price analysis</font>

*This tutorial cover how to retrieve stock price from google finance using pandas data reader. The analysis of stock is done by plotting its high, low, close, volume values in talble and a chart. Charts are of two types,*

1. Line Chart
2. Bar Chart

If you don't know what is stock then we highly recommend that you first watch **the video below** to find out what is Stock.


```python
%%HTML
<iframe width="560" height="315" src="https://www.youtube.com/embed/7EUbrFLef7M" frameborder="0" allowfullscreen></iframe>
```


<iframe width="560" height="315" src="https://www.youtube.com/embed/7EUbrFLef7M" frameborder="0" allowfullscreen></iframe>



```python
# Setting keybooard shorcut for ease.
# e.g Run : Shift + Enter
```


```python
from pandas_datareader import data as web
data_frame = web.DataReader('AAPL', 'google', '2016/1/1', '2017/1/1')
data_frame.head()
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2016-01-04</th>
      <td>102.61</td>
      <td>105.37</td>
      <td>102.00</td>
      <td>105.35</td>
      <td>67281190</td>
    </tr>
    <tr>
      <th>2016-01-05</th>
      <td>105.75</td>
      <td>105.85</td>
      <td>102.41</td>
      <td>102.71</td>
      <td>55790992</td>
    </tr>
    <tr>
      <th>2016-01-06</th>
      <td>100.56</td>
      <td>102.37</td>
      <td>99.87</td>
      <td>100.70</td>
      <td>68457388</td>
    </tr>
    <tr>
      <th>2016-01-07</th>
      <td>98.68</td>
      <td>100.13</td>
      <td>96.43</td>
      <td>96.45</td>
      <td>81094428</td>
    </tr>
    <tr>
      <th>2016-01-08</th>
      <td>98.55</td>
      <td>99.11</td>
      <td>96.76</td>
      <td>96.96</td>
      <td>70798016</td>
    </tr>
  </tbody>
</table>
</div>




```python
# % is magic command
# inline will plot the chart as soon as execution finish.
%matplotlib inline
data_frame.plot(y="Close", color="purple")
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f0e058a33c8>




![png](output_5_1.png)



```python
# Show all available line magics
%lsmagic
```




    Available line magics:
    %alias  %alias_magic  %autocall  %automagic  %autosave  %bookmark  %cat  %cd  %clear  %colors  %config  %connect_info  %cp  %debug  %dhist  %dirs  %doctest_mode  %ed  %edit  %env  %gui  %hist  %history  %killbgscripts  %ldir  %less  %lf  %lk  %ll  %load  %load_ext  %loadpy  %logoff  %logon  %logstart  %logstate  %logstop  %ls  %lsmagic  %lx  %macro  %magic  %man  %matplotlib  %mkdir  %more  %mv  %notebook  %page  %pastebin  %pdb  %pdef  %pdoc  %pfile  %pinfo  %pinfo2  %popd  %pprint  %precision  %profile  %prun  %psearch  %psource  %pushd  %pwd  %pycat  %pylab  %qtconsole  %quickref  %recall  %rehashx  %reload_ext  %rep  %rerun  %reset  %reset_selective  %rm  %rmdir  %run  %save  %sc  %set_env  %store  %sx  %system  %tb  %time  %timeit  %unalias  %unload_ext  %who  %who_ls  %whos  %xdel  %xmode
    
    Available cell magics:
    %%!  %%HTML  %%SVG  %%bash  %%capture  %%debug  %%file  %%html  %%javascript  %%js  %%latex  %%markdown  %%perl  %%prun  %%pypy  %%python  %%python2  %%python3  %%ruby  %%script  %%sh  %%svg  %%sx  %%system  %%time  %%timeit  %%writefile
    
    Automagic is ON, % prefix IS NOT needed for line magics.




```python
# '%time?' to open %time docstring
%time?
```


```python
# Check runtime of for loop
%time for i in range(100000): i*i+i
```

    CPU times: user 24 ms, sys: 0 ns, total: 24 ms
    Wall time: 23.7 ms



```python
# Run UNIX command
%system?
```


```python
# Show present working directory
%system pwd
```




    ['/home/lhuynh/Desktop/nb-ipynb']




```python
# We can run UNIX command using shorcut ! instead of %system
!pwd
```

    /home/lhuynh/Desktop/nb-ipynb



```python
# Continue with the stock plot
# We can plot a bar chart
data_frame.plot.bar(y="Volume")
```




    <matplotlib.axes._subplots.AxesSubplot at 0x7f0e0301dd30>




![png](output_12_1.png)



```python
%%python?
```

### <font color="red">Jupyter Notebook architecture:</font>
<img src="files/images/jupyternb-architect.png" alt="jupyternb architecture">

### Google "jupyter notebook gallery" for more notebook examples
<form method="get" action="http://www.google.com/search"> 
<input type="text" name="q" size="31" maxlength="255" value="jupyter notebook gallery" /> 
<input type="submit" value="Google Search" /> 
</form>


```python

```
