```python
import numpy as np 
import pandas as pd
store_df=pd.read_csv('C:/Users/Mirela/Downloads/Superstore/Superstore.csv',  encoding = "ISO-8859-1")
```


```python
# Viewing data
```


```python
store_df.head()
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
      <th>Row ID</th>
      <th>Order ID</th>
      <th>Order Date</th>
      <th>Ship Date</th>
      <th>Ship Mode</th>
      <th>Customer ID</th>
      <th>Customer Name</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
      <th>...</th>
      <th>Postal Code</th>
      <th>Region</th>
      <th>Product ID</th>
      <th>Category</th>
      <th>Sub-Category</th>
      <th>Product Name</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>CA-2016-152156</td>
      <td>11/8/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>42420</td>
      <td>South</td>
      <td>FUR-BO-10001798</td>
      <td>Furniture</td>
      <td>Bookcases</td>
      <td>Bush Somerset Collection Bookcase</td>
      <td>261.9600</td>
      <td>2</td>
      <td>0.00</td>
      <td>41.9136</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>CA-2016-152156</td>
      <td>11/8/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>42420</td>
      <td>South</td>
      <td>FUR-CH-10000454</td>
      <td>Furniture</td>
      <td>Chairs</td>
      <td>Hon Deluxe Fabric Upholstered Stacking Chairs,...</td>
      <td>731.9400</td>
      <td>3</td>
      <td>0.00</td>
      <td>219.5820</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>CA-2016-138688</td>
      <td>6/12/2016</td>
      <td>6/16/2016</td>
      <td>Second Class</td>
      <td>DV-13045</td>
      <td>Darrin Van Huff</td>
      <td>Corporate</td>
      <td>United States</td>
      <td>Los Angeles</td>
      <td>...</td>
      <td>90036</td>
      <td>West</td>
      <td>OFF-LA-10000240</td>
      <td>Office Supplies</td>
      <td>Labels</td>
      <td>Self-Adhesive Address Labels for Typewriters b...</td>
      <td>14.6200</td>
      <td>2</td>
      <td>0.00</td>
      <td>6.8714</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>US-2015-108966</td>
      <td>10/11/2015</td>
      <td>10/18/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>33311</td>
      <td>South</td>
      <td>FUR-TA-10000577</td>
      <td>Furniture</td>
      <td>Tables</td>
      <td>Bretford CR4500 Series Slim Rectangular Table</td>
      <td>957.5775</td>
      <td>5</td>
      <td>0.45</td>
      <td>-383.0310</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>US-2015-108966</td>
      <td>10/11/2015</td>
      <td>10/18/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>33311</td>
      <td>South</td>
      <td>OFF-ST-10000760</td>
      <td>Office Supplies</td>
      <td>Storage</td>
      <td>Eldon Fold 'N Roll Cart System</td>
      <td>22.3680</td>
      <td>2</td>
      <td>0.20</td>
      <td>2.5164</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 21 columns</p>
</div>




```python
store_df.info()
```

    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 9994 entries, 0 to 9993
    Data columns (total 21 columns):
     #   Column         Non-Null Count  Dtype  
    ---  ------         --------------  -----  
     0   Row ID         9994 non-null   int64  
     1   Order ID       9994 non-null   object 
     2   Order Date     9994 non-null   object 
     3   Ship Date      9994 non-null   object 
     4   Ship Mode      9994 non-null   object 
     5   Customer ID    9994 non-null   object 
     6   Customer Name  9994 non-null   object 
     7   Segment        9994 non-null   object 
     8   Country        9994 non-null   object 
     9   City           9994 non-null   object 
     10  State          9994 non-null   object 
     11  Postal Code    9994 non-null   int64  
     12  Region         9994 non-null   object 
     13  Product ID     9994 non-null   object 
     14  Category       9994 non-null   object 
     15  Sub-Category   9994 non-null   object 
     16  Product Name   9994 non-null   object 
     17  Sales          9994 non-null   float64
     18  Quantity       9994 non-null   int64  
     19  Discount       9994 non-null   float64
     20  Profit         9994 non-null   float64
    dtypes: float64(3), int64(3), object(15)
    memory usage: 1.6+ MB
    


```python
# The columns of the resulting DataFrame have different dtypes:
```


```python
store_df.tail(5)
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
      <th>Row ID</th>
      <th>Order ID</th>
      <th>Order Date</th>
      <th>Ship Date</th>
      <th>Ship Mode</th>
      <th>Customer ID</th>
      <th>Customer Name</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
      <th>...</th>
      <th>Postal Code</th>
      <th>Region</th>
      <th>Product ID</th>
      <th>Category</th>
      <th>Sub-Category</th>
      <th>Product Name</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>9989</th>
      <td>9990</td>
      <td>CA-2014-110422</td>
      <td>1/21/2014</td>
      <td>1/23/2014</td>
      <td>Second Class</td>
      <td>TB-21400</td>
      <td>Tom Boeckenhauer</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Miami</td>
      <td>...</td>
      <td>33180</td>
      <td>South</td>
      <td>FUR-FU-10001889</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Ultra Door Pull Handle</td>
      <td>25.248</td>
      <td>3</td>
      <td>0.2</td>
      <td>4.1028</td>
    </tr>
    <tr>
      <th>9990</th>
      <td>9991</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>FUR-FU-10000747</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Tenex B1-RE Series Chair Mats for Low Pile Car...</td>
      <td>91.960</td>
      <td>2</td>
      <td>0.0</td>
      <td>15.6332</td>
    </tr>
    <tr>
      <th>9991</th>
      <td>9992</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>TEC-PH-10003645</td>
      <td>Technology</td>
      <td>Phones</td>
      <td>Aastra 57i VoIP phone</td>
      <td>258.576</td>
      <td>2</td>
      <td>0.2</td>
      <td>19.3932</td>
    </tr>
    <tr>
      <th>9992</th>
      <td>9993</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>OFF-PA-10004041</td>
      <td>Office Supplies</td>
      <td>Paper</td>
      <td>It's Hot Message Books with Stickers, 2 3/4" x 5"</td>
      <td>29.600</td>
      <td>4</td>
      <td>0.0</td>
      <td>13.3200</td>
    </tr>
    <tr>
      <th>9993</th>
      <td>9994</td>
      <td>CA-2017-119914</td>
      <td>5/4/2017</td>
      <td>5/9/2017</td>
      <td>Second Class</td>
      <td>CC-12220</td>
      <td>Chris Cortes</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Westminster</td>
      <td>...</td>
      <td>92683</td>
      <td>West</td>
      <td>OFF-AP-10002684</td>
      <td>Office Supplies</td>
      <td>Appliances</td>
      <td>Acco 7-Outlet Masterpiece Power Center, Wihtou...</td>
      <td>243.160</td>
      <td>2</td>
      <td>0.0</td>
      <td>72.9480</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 21 columns</p>
</div>




```python
store_df.index
```




    RangeIndex(start=0, stop=9994, step=1)




```python
store_df.columns
```




    Index(['Row ID', 'Order ID', 'Order Date', 'Ship Date', 'Ship Mode',
           'Customer ID', 'Customer Name', 'Segment', 'Country', 'City', 'State',
           'Postal Code', 'Region', 'Product ID', 'Category', 'Sub-Category',
           'Product Name', 'Sales', 'Quantity', 'Discount', 'Profit'],
          dtype='object')




```python
store_df.describe()
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
      <th>Row ID</th>
      <th>Postal Code</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>9994.000000</td>
      <td>9994.000000</td>
      <td>9994.000000</td>
      <td>9994.000000</td>
      <td>9994.000000</td>
      <td>9994.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>4997.500000</td>
      <td>55190.379428</td>
      <td>229.858001</td>
      <td>3.789574</td>
      <td>0.156203</td>
      <td>28.656896</td>
    </tr>
    <tr>
      <th>std</th>
      <td>2885.163629</td>
      <td>32063.693350</td>
      <td>623.245101</td>
      <td>2.225110</td>
      <td>0.206452</td>
      <td>234.260108</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>1040.000000</td>
      <td>0.444000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>-6599.978000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2499.250000</td>
      <td>23223.000000</td>
      <td>17.280000</td>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>1.728750</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>4997.500000</td>
      <td>56430.500000</td>
      <td>54.490000</td>
      <td>3.000000</td>
      <td>0.200000</td>
      <td>8.666500</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>7495.750000</td>
      <td>90008.000000</td>
      <td>209.940000</td>
      <td>5.000000</td>
      <td>0.200000</td>
      <td>29.364000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>9994.000000</td>
      <td>99301.000000</td>
      <td>22638.480000</td>
      <td>14.000000</td>
      <td>0.800000</td>
      <td>8399.976000</td>
    </tr>
  </tbody>
</table>
</div>




```python
store_df.sort_values(by="Order Date")
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
      <th>Row ID</th>
      <th>Order ID</th>
      <th>Order Date</th>
      <th>Ship Date</th>
      <th>Ship Mode</th>
      <th>Customer ID</th>
      <th>Customer Name</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
      <th>...</th>
      <th>Postal Code</th>
      <th>Region</th>
      <th>Product ID</th>
      <th>Category</th>
      <th>Sub-Category</th>
      <th>Product Name</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>8074</th>
      <td>8075</td>
      <td>CA-2017-151750</td>
      <td>1/1/2017</td>
      <td>1/5/2017</td>
      <td>Standard Class</td>
      <td>JM-15250</td>
      <td>Janet Martin</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Huntsville</td>
      <td>...</td>
      <td>77340</td>
      <td>Central</td>
      <td>OFF-BI-10000343</td>
      <td>Office Supplies</td>
      <td>Binders</td>
      <td>Pressboard Covers with Storage Hooks, 9 1/2" x...</td>
      <td>13.748</td>
      <td>14</td>
      <td>0.8</td>
      <td>-22.6842</td>
    </tr>
    <tr>
      <th>848</th>
      <td>849</td>
      <td>CA-2017-107503</td>
      <td>1/1/2017</td>
      <td>1/6/2017</td>
      <td>Standard Class</td>
      <td>GA-14725</td>
      <td>Guy Armstrong</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Lorain</td>
      <td>...</td>
      <td>44052</td>
      <td>East</td>
      <td>FUR-FU-10003878</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Linden 10" Round Wall Clock, Black</td>
      <td>48.896</td>
      <td>4</td>
      <td>0.2</td>
      <td>8.5568</td>
    </tr>
    <tr>
      <th>8075</th>
      <td>8076</td>
      <td>CA-2017-151750</td>
      <td>1/1/2017</td>
      <td>1/5/2017</td>
      <td>Standard Class</td>
      <td>JM-15250</td>
      <td>Janet Martin</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Huntsville</td>
      <td>...</td>
      <td>77340</td>
      <td>Central</td>
      <td>OFF-AP-10004708</td>
      <td>Office Supplies</td>
      <td>Appliances</td>
      <td>Fellowes Superior 10 Outlet Split Surge Protector</td>
      <td>15.224</td>
      <td>2</td>
      <td>0.8</td>
      <td>-38.8212</td>
    </tr>
    <tr>
      <th>8073</th>
      <td>8074</td>
      <td>CA-2017-151750</td>
      <td>1/1/2017</td>
      <td>1/5/2017</td>
      <td>Standard Class</td>
      <td>JM-15250</td>
      <td>Janet Martin</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Huntsville</td>
      <td>...</td>
      <td>77340</td>
      <td>Central</td>
      <td>OFF-BI-10000301</td>
      <td>Office Supplies</td>
      <td>Binders</td>
      <td>GBC Instant Report Kit</td>
      <td>6.470</td>
      <td>5</td>
      <td>0.8</td>
      <td>-9.7050</td>
    </tr>
    <tr>
      <th>8071</th>
      <td>8072</td>
      <td>CA-2017-151750</td>
      <td>1/1/2017</td>
      <td>1/5/2017</td>
      <td>Standard Class</td>
      <td>JM-15250</td>
      <td>Janet Martin</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Huntsville</td>
      <td>...</td>
      <td>77340</td>
      <td>Central</td>
      <td>FUR-CH-10003199</td>
      <td>Furniture</td>
      <td>Chairs</td>
      <td>Office Star - Contemporary Task Swivel Chair</td>
      <td>310.744</td>
      <td>4</td>
      <td>0.3</td>
      <td>-26.6352</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>7875</th>
      <td>7876</td>
      <td>CA-2017-168403</td>
      <td>9/9/2017</td>
      <td>9/15/2017</td>
      <td>Standard Class</td>
      <td>DK-12835</td>
      <td>Damala Kotsonis</td>
      <td>Corporate</td>
      <td>United States</td>
      <td>Portland</td>
      <td>...</td>
      <td>97206</td>
      <td>West</td>
      <td>OFF-PA-10002036</td>
      <td>Office Supplies</td>
      <td>Paper</td>
      <td>Xerox 1930</td>
      <td>31.104</td>
      <td>6</td>
      <td>0.2</td>
      <td>11.2752</td>
    </tr>
    <tr>
      <th>5441</th>
      <td>5442</td>
      <td>CA-2017-155929</td>
      <td>9/9/2017</td>
      <td>9/13/2017</td>
      <td>Standard Class</td>
      <td>AI-10855</td>
      <td>Arianne Irving</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Glendale</td>
      <td>...</td>
      <td>85301</td>
      <td>West</td>
      <td>OFF-PA-10000859</td>
      <td>Office Supplies</td>
      <td>Paper</td>
      <td>Unpadded Memo Slips</td>
      <td>6.368</td>
      <td>2</td>
      <td>0.2</td>
      <td>2.3880</td>
    </tr>
    <tr>
      <th>6255</th>
      <td>6256</td>
      <td>CA-2017-139444</td>
      <td>9/9/2017</td>
      <td>9/15/2017</td>
      <td>Standard Class</td>
      <td>GK-14620</td>
      <td>Grace Kelly</td>
      <td>Corporate</td>
      <td>United States</td>
      <td>Plano</td>
      <td>...</td>
      <td>75023</td>
      <td>Central</td>
      <td>OFF-LA-10000134</td>
      <td>Office Supplies</td>
      <td>Labels</td>
      <td>Avery 511</td>
      <td>9.856</td>
      <td>4</td>
      <td>0.2</td>
      <td>3.4496</td>
    </tr>
    <tr>
      <th>8753</th>
      <td>8754</td>
      <td>CA-2017-152198</td>
      <td>9/9/2017</td>
      <td>9/10/2017</td>
      <td>First Class</td>
      <td>JD-16015</td>
      <td>Joy Daniels</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Toledo</td>
      <td>...</td>
      <td>43615</td>
      <td>East</td>
      <td>OFF-LA-10000443</td>
      <td>Office Supplies</td>
      <td>Labels</td>
      <td>Avery 501</td>
      <td>17.712</td>
      <td>6</td>
      <td>0.2</td>
      <td>5.9778</td>
    </tr>
    <tr>
      <th>7876</th>
      <td>7877</td>
      <td>CA-2017-168403</td>
      <td>9/9/2017</td>
      <td>9/15/2017</td>
      <td>Standard Class</td>
      <td>DK-12835</td>
      <td>Damala Kotsonis</td>
      <td>Corporate</td>
      <td>United States</td>
      <td>Portland</td>
      <td>...</td>
      <td>97206</td>
      <td>West</td>
      <td>OFF-AP-10003278</td>
      <td>Office Supplies</td>
      <td>Appliances</td>
      <td>Belkin 7-Outlet SurgeMaster Home Series</td>
      <td>11.176</td>
      <td>1</td>
      <td>0.2</td>
      <td>0.8382</td>
    </tr>
  </tbody>
</table>
<p>9994 rows × 21 columns</p>
</div>




```python
# DataFrame.sort_values() sorts by values: 
```


```python
# Selection
```


```python
# Getting
```


```python
store_df["Product Name"]
```




    0                       Bush Somerset Collection Bookcase
    1       Hon Deluxe Fabric Upholstered Stacking Chairs,...
    2       Self-Adhesive Address Labels for Typewriters b...
    3           Bretford CR4500 Series Slim Rectangular Table
    4                          Eldon Fold 'N Roll Cart System
                                  ...                        
    9989                               Ultra Door Pull Handle
    9990    Tenex B1-RE Series Chair Mats for Low Pile Car...
    9991                                Aastra 57i VoIP phone
    9992    It's Hot Message Books with Stickers, 2 3/4" x 5"
    9993    Acco 7-Outlet Masterpiece Power Center, Wihtou...
    Name: Product Name, Length: 9994, dtype: object




```python
# Selection by label
```


```python
store_df.loc[:, ["Region", "Product Name"]].sort_values(by="Region")
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
      <th>Region</th>
      <th>Product Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2594</th>
      <td>Central</td>
      <td>Tyvek Side-Opening Peel &amp; Seel Expanding Envel...</td>
    </tr>
    <tr>
      <th>8943</th>
      <td>Central</td>
      <td>Hon Comfortask Task/Swivel Chairs</td>
    </tr>
    <tr>
      <th>6665</th>
      <td>Central</td>
      <td>Xerox 1914</td>
    </tr>
    <tr>
      <th>2923</th>
      <td>Central</td>
      <td>Staples</td>
    </tr>
    <tr>
      <th>2922</th>
      <td>Central</td>
      <td>GBC Instant Report Kit</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>3225</th>
      <td>West</td>
      <td>Letter or Legal Size Expandable Poly String Ti...</td>
    </tr>
    <tr>
      <th>3224</th>
      <td>West</td>
      <td>Bose SoundLink Bluetooth Speaker</td>
    </tr>
    <tr>
      <th>7793</th>
      <td>West</td>
      <td>Xerox 1930</td>
    </tr>
    <tr>
      <th>3247</th>
      <td>West</td>
      <td>Col-Erase Pencils with Erasers</td>
    </tr>
    <tr>
      <th>9993</th>
      <td>West</td>
      <td>Acco 7-Outlet Masterpiece Power Center, Wihtou...</td>
    </tr>
  </tbody>
</table>
<p>9994 rows × 2 columns</p>
</div>




```python
# Selection by position
```


```python
store_df.iloc[:, [1,7,8,9]]
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
      <th>Order ID</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>CA-2016-152156</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
    </tr>
    <tr>
      <th>1</th>
      <td>CA-2016-152156</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
    </tr>
    <tr>
      <th>2</th>
      <td>CA-2016-138688</td>
      <td>Corporate</td>
      <td>United States</td>
      <td>Los Angeles</td>
    </tr>
    <tr>
      <th>3</th>
      <td>US-2015-108966</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
    </tr>
    <tr>
      <th>4</th>
      <td>US-2015-108966</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>9989</th>
      <td>CA-2014-110422</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Miami</td>
    </tr>
    <tr>
      <th>9990</th>
      <td>CA-2017-121258</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
    </tr>
    <tr>
      <th>9991</th>
      <td>CA-2017-121258</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
    </tr>
    <tr>
      <th>9992</th>
      <td>CA-2017-121258</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
    </tr>
    <tr>
      <th>9993</th>
      <td>CA-2017-119914</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Westminster</td>
    </tr>
  </tbody>
</table>
<p>9994 rows × 4 columns</p>
</div>




```python
# Boolean indexing
```


```python
store_df[store_df['Quantity'] > 0]
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
      <th>Row ID</th>
      <th>Order ID</th>
      <th>Order Date</th>
      <th>Ship Date</th>
      <th>Ship Mode</th>
      <th>Customer ID</th>
      <th>Customer Name</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
      <th>...</th>
      <th>Postal Code</th>
      <th>Region</th>
      <th>Product ID</th>
      <th>Category</th>
      <th>Sub-Category</th>
      <th>Product Name</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>CA-2016-152156</td>
      <td>11/8/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>42420</td>
      <td>South</td>
      <td>FUR-BO-10001798</td>
      <td>Furniture</td>
      <td>Bookcases</td>
      <td>Bush Somerset Collection Bookcase</td>
      <td>261.9600</td>
      <td>2</td>
      <td>0.00</td>
      <td>41.9136</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>CA-2016-152156</td>
      <td>11/8/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>42420</td>
      <td>South</td>
      <td>FUR-CH-10000454</td>
      <td>Furniture</td>
      <td>Chairs</td>
      <td>Hon Deluxe Fabric Upholstered Stacking Chairs,...</td>
      <td>731.9400</td>
      <td>3</td>
      <td>0.00</td>
      <td>219.5820</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>CA-2016-138688</td>
      <td>6/12/2016</td>
      <td>6/16/2016</td>
      <td>Second Class</td>
      <td>DV-13045</td>
      <td>Darrin Van Huff</td>
      <td>Corporate</td>
      <td>United States</td>
      <td>Los Angeles</td>
      <td>...</td>
      <td>90036</td>
      <td>West</td>
      <td>OFF-LA-10000240</td>
      <td>Office Supplies</td>
      <td>Labels</td>
      <td>Self-Adhesive Address Labels for Typewriters b...</td>
      <td>14.6200</td>
      <td>2</td>
      <td>0.00</td>
      <td>6.8714</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>US-2015-108966</td>
      <td>10/11/2015</td>
      <td>10/18/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>33311</td>
      <td>South</td>
      <td>FUR-TA-10000577</td>
      <td>Furniture</td>
      <td>Tables</td>
      <td>Bretford CR4500 Series Slim Rectangular Table</td>
      <td>957.5775</td>
      <td>5</td>
      <td>0.45</td>
      <td>-383.0310</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>US-2015-108966</td>
      <td>10/11/2015</td>
      <td>10/18/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>33311</td>
      <td>South</td>
      <td>OFF-ST-10000760</td>
      <td>Office Supplies</td>
      <td>Storage</td>
      <td>Eldon Fold 'N Roll Cart System</td>
      <td>22.3680</td>
      <td>2</td>
      <td>0.20</td>
      <td>2.5164</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>9989</th>
      <td>9990</td>
      <td>CA-2014-110422</td>
      <td>1/21/2014</td>
      <td>1/23/2014</td>
      <td>Second Class</td>
      <td>TB-21400</td>
      <td>Tom Boeckenhauer</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Miami</td>
      <td>...</td>
      <td>33180</td>
      <td>South</td>
      <td>FUR-FU-10001889</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Ultra Door Pull Handle</td>
      <td>25.2480</td>
      <td>3</td>
      <td>0.20</td>
      <td>4.1028</td>
    </tr>
    <tr>
      <th>9990</th>
      <td>9991</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>FUR-FU-10000747</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Tenex B1-RE Series Chair Mats for Low Pile Car...</td>
      <td>91.9600</td>
      <td>2</td>
      <td>0.00</td>
      <td>15.6332</td>
    </tr>
    <tr>
      <th>9991</th>
      <td>9992</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>TEC-PH-10003645</td>
      <td>Technology</td>
      <td>Phones</td>
      <td>Aastra 57i VoIP phone</td>
      <td>258.5760</td>
      <td>2</td>
      <td>0.20</td>
      <td>19.3932</td>
    </tr>
    <tr>
      <th>9992</th>
      <td>9993</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>OFF-PA-10004041</td>
      <td>Office Supplies</td>
      <td>Paper</td>
      <td>It's Hot Message Books with Stickers, 2 3/4" x 5"</td>
      <td>29.6000</td>
      <td>4</td>
      <td>0.00</td>
      <td>13.3200</td>
    </tr>
    <tr>
      <th>9993</th>
      <td>9994</td>
      <td>CA-2017-119914</td>
      <td>5/4/2017</td>
      <td>5/9/2017</td>
      <td>Second Class</td>
      <td>CC-12220</td>
      <td>Chris Cortes</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Westminster</td>
      <td>...</td>
      <td>92683</td>
      <td>West</td>
      <td>OFF-AP-10002684</td>
      <td>Office Supplies</td>
      <td>Appliances</td>
      <td>Acco 7-Outlet Masterpiece Power Center, Wihtou...</td>
      <td>243.1600</td>
      <td>2</td>
      <td>0.00</td>
      <td>72.9480</td>
    </tr>
  </tbody>
</table>
<p>9994 rows × 21 columns</p>
</div>




```python
store_df[store_df["City"] != 'NA']
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
      <th>Row ID</th>
      <th>Order ID</th>
      <th>Order Date</th>
      <th>Ship Date</th>
      <th>Ship Mode</th>
      <th>Customer ID</th>
      <th>Customer Name</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
      <th>...</th>
      <th>Postal Code</th>
      <th>Region</th>
      <th>Product ID</th>
      <th>Category</th>
      <th>Sub-Category</th>
      <th>Product Name</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>CA-2016-152156</td>
      <td>11/8/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>42420</td>
      <td>South</td>
      <td>FUR-BO-10001798</td>
      <td>Furniture</td>
      <td>Bookcases</td>
      <td>Bush Somerset Collection Bookcase</td>
      <td>261.9600</td>
      <td>2</td>
      <td>0.00</td>
      <td>41.9136</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>CA-2016-152156</td>
      <td>11/8/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>42420</td>
      <td>South</td>
      <td>FUR-CH-10000454</td>
      <td>Furniture</td>
      <td>Chairs</td>
      <td>Hon Deluxe Fabric Upholstered Stacking Chairs,...</td>
      <td>731.9400</td>
      <td>3</td>
      <td>0.00</td>
      <td>219.5820</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>CA-2016-138688</td>
      <td>6/12/2016</td>
      <td>6/16/2016</td>
      <td>Second Class</td>
      <td>DV-13045</td>
      <td>Darrin Van Huff</td>
      <td>Corporate</td>
      <td>United States</td>
      <td>Los Angeles</td>
      <td>...</td>
      <td>90036</td>
      <td>West</td>
      <td>OFF-LA-10000240</td>
      <td>Office Supplies</td>
      <td>Labels</td>
      <td>Self-Adhesive Address Labels for Typewriters b...</td>
      <td>14.6200</td>
      <td>2</td>
      <td>0.00</td>
      <td>6.8714</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>US-2015-108966</td>
      <td>10/11/2015</td>
      <td>10/18/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>33311</td>
      <td>South</td>
      <td>FUR-TA-10000577</td>
      <td>Furniture</td>
      <td>Tables</td>
      <td>Bretford CR4500 Series Slim Rectangular Table</td>
      <td>957.5775</td>
      <td>5</td>
      <td>0.45</td>
      <td>-383.0310</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>US-2015-108966</td>
      <td>10/11/2015</td>
      <td>10/18/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>33311</td>
      <td>South</td>
      <td>OFF-ST-10000760</td>
      <td>Office Supplies</td>
      <td>Storage</td>
      <td>Eldon Fold 'N Roll Cart System</td>
      <td>22.3680</td>
      <td>2</td>
      <td>0.20</td>
      <td>2.5164</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>9989</th>
      <td>9990</td>
      <td>CA-2014-110422</td>
      <td>1/21/2014</td>
      <td>1/23/2014</td>
      <td>Second Class</td>
      <td>TB-21400</td>
      <td>Tom Boeckenhauer</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Miami</td>
      <td>...</td>
      <td>33180</td>
      <td>South</td>
      <td>FUR-FU-10001889</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Ultra Door Pull Handle</td>
      <td>25.2480</td>
      <td>3</td>
      <td>0.20</td>
      <td>4.1028</td>
    </tr>
    <tr>
      <th>9990</th>
      <td>9991</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>FUR-FU-10000747</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Tenex B1-RE Series Chair Mats for Low Pile Car...</td>
      <td>91.9600</td>
      <td>2</td>
      <td>0.00</td>
      <td>15.6332</td>
    </tr>
    <tr>
      <th>9991</th>
      <td>9992</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>TEC-PH-10003645</td>
      <td>Technology</td>
      <td>Phones</td>
      <td>Aastra 57i VoIP phone</td>
      <td>258.5760</td>
      <td>2</td>
      <td>0.20</td>
      <td>19.3932</td>
    </tr>
    <tr>
      <th>9992</th>
      <td>9993</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>OFF-PA-10004041</td>
      <td>Office Supplies</td>
      <td>Paper</td>
      <td>It's Hot Message Books with Stickers, 2 3/4" x 5"</td>
      <td>29.6000</td>
      <td>4</td>
      <td>0.00</td>
      <td>13.3200</td>
    </tr>
    <tr>
      <th>9993</th>
      <td>9994</td>
      <td>CA-2017-119914</td>
      <td>5/4/2017</td>
      <td>5/9/2017</td>
      <td>Second Class</td>
      <td>CC-12220</td>
      <td>Chris Cortes</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Westminster</td>
      <td>...</td>
      <td>92683</td>
      <td>West</td>
      <td>OFF-AP-10002684</td>
      <td>Office Supplies</td>
      <td>Appliances</td>
      <td>Acco 7-Outlet Masterpiece Power Center, Wihtou...</td>
      <td>243.1600</td>
      <td>2</td>
      <td>0.00</td>
      <td>72.9480</td>
    </tr>
  </tbody>
</table>
<p>9994 rows × 21 columns</p>
</div>




```python
store_df[store_df["Region"].isin(["South", "West"])]
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
      <th>Row ID</th>
      <th>Order ID</th>
      <th>Order Date</th>
      <th>Ship Date</th>
      <th>Ship Mode</th>
      <th>Customer ID</th>
      <th>Customer Name</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
      <th>...</th>
      <th>Postal Code</th>
      <th>Region</th>
      <th>Product ID</th>
      <th>Category</th>
      <th>Sub-Category</th>
      <th>Product Name</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>CA-2016-152156</td>
      <td>11/8/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>42420</td>
      <td>South</td>
      <td>FUR-BO-10001798</td>
      <td>Furniture</td>
      <td>Bookcases</td>
      <td>Bush Somerset Collection Bookcase</td>
      <td>261.9600</td>
      <td>2</td>
      <td>0.00</td>
      <td>41.9136</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>CA-2016-152156</td>
      <td>11/8/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>42420</td>
      <td>South</td>
      <td>FUR-CH-10000454</td>
      <td>Furniture</td>
      <td>Chairs</td>
      <td>Hon Deluxe Fabric Upholstered Stacking Chairs,...</td>
      <td>731.9400</td>
      <td>3</td>
      <td>0.00</td>
      <td>219.5820</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>CA-2016-138688</td>
      <td>6/12/2016</td>
      <td>6/16/2016</td>
      <td>Second Class</td>
      <td>DV-13045</td>
      <td>Darrin Van Huff</td>
      <td>Corporate</td>
      <td>United States</td>
      <td>Los Angeles</td>
      <td>...</td>
      <td>90036</td>
      <td>West</td>
      <td>OFF-LA-10000240</td>
      <td>Office Supplies</td>
      <td>Labels</td>
      <td>Self-Adhesive Address Labels for Typewriters b...</td>
      <td>14.6200</td>
      <td>2</td>
      <td>0.00</td>
      <td>6.8714</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>US-2015-108966</td>
      <td>10/11/2015</td>
      <td>10/18/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>33311</td>
      <td>South</td>
      <td>FUR-TA-10000577</td>
      <td>Furniture</td>
      <td>Tables</td>
      <td>Bretford CR4500 Series Slim Rectangular Table</td>
      <td>957.5775</td>
      <td>5</td>
      <td>0.45</td>
      <td>-383.0310</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>US-2015-108966</td>
      <td>10/11/2015</td>
      <td>10/18/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>33311</td>
      <td>South</td>
      <td>OFF-ST-10000760</td>
      <td>Office Supplies</td>
      <td>Storage</td>
      <td>Eldon Fold 'N Roll Cart System</td>
      <td>22.3680</td>
      <td>2</td>
      <td>0.20</td>
      <td>2.5164</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>9989</th>
      <td>9990</td>
      <td>CA-2014-110422</td>
      <td>1/21/2014</td>
      <td>1/23/2014</td>
      <td>Second Class</td>
      <td>TB-21400</td>
      <td>Tom Boeckenhauer</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Miami</td>
      <td>...</td>
      <td>33180</td>
      <td>South</td>
      <td>FUR-FU-10001889</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Ultra Door Pull Handle</td>
      <td>25.2480</td>
      <td>3</td>
      <td>0.20</td>
      <td>4.1028</td>
    </tr>
    <tr>
      <th>9990</th>
      <td>9991</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>FUR-FU-10000747</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Tenex B1-RE Series Chair Mats for Low Pile Car...</td>
      <td>91.9600</td>
      <td>2</td>
      <td>0.00</td>
      <td>15.6332</td>
    </tr>
    <tr>
      <th>9991</th>
      <td>9992</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>TEC-PH-10003645</td>
      <td>Technology</td>
      <td>Phones</td>
      <td>Aastra 57i VoIP phone</td>
      <td>258.5760</td>
      <td>2</td>
      <td>0.20</td>
      <td>19.3932</td>
    </tr>
    <tr>
      <th>9992</th>
      <td>9993</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>OFF-PA-10004041</td>
      <td>Office Supplies</td>
      <td>Paper</td>
      <td>It's Hot Message Books with Stickers, 2 3/4" x 5"</td>
      <td>29.6000</td>
      <td>4</td>
      <td>0.00</td>
      <td>13.3200</td>
    </tr>
    <tr>
      <th>9993</th>
      <td>9994</td>
      <td>CA-2017-119914</td>
      <td>5/4/2017</td>
      <td>5/9/2017</td>
      <td>Second Class</td>
      <td>CC-12220</td>
      <td>Chris Cortes</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Westminster</td>
      <td>...</td>
      <td>92683</td>
      <td>West</td>
      <td>OFF-AP-10002684</td>
      <td>Office Supplies</td>
      <td>Appliances</td>
      <td>Acco 7-Outlet Masterpiece Power Center, Wihtou...</td>
      <td>243.1600</td>
      <td>2</td>
      <td>0.00</td>
      <td>72.9480</td>
    </tr>
  </tbody>
</table>
<p>4823 rows × 21 columns</p>
</div>




```python
# Missing data
```


```python
store_df.fillna(value=0)
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
      <th>Row ID</th>
      <th>Order ID</th>
      <th>Order Date</th>
      <th>Ship Date</th>
      <th>Ship Mode</th>
      <th>Customer ID</th>
      <th>Customer Name</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
      <th>...</th>
      <th>Postal Code</th>
      <th>Region</th>
      <th>Product ID</th>
      <th>Category</th>
      <th>Sub-Category</th>
      <th>Product Name</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>CA-2016-152156</td>
      <td>11/8/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>42420</td>
      <td>South</td>
      <td>FUR-BO-10001798</td>
      <td>Furniture</td>
      <td>Bookcases</td>
      <td>Bush Somerset Collection Bookcase</td>
      <td>261.9600</td>
      <td>2</td>
      <td>0.00</td>
      <td>41.9136</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
      <td>CA-2016-152156</td>
      <td>11/8/2016</td>
      <td>11/11/2016</td>
      <td>Second Class</td>
      <td>CG-12520</td>
      <td>Claire Gute</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Henderson</td>
      <td>...</td>
      <td>42420</td>
      <td>South</td>
      <td>FUR-CH-10000454</td>
      <td>Furniture</td>
      <td>Chairs</td>
      <td>Hon Deluxe Fabric Upholstered Stacking Chairs,...</td>
      <td>731.9400</td>
      <td>3</td>
      <td>0.00</td>
      <td>219.5820</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
      <td>CA-2016-138688</td>
      <td>6/12/2016</td>
      <td>6/16/2016</td>
      <td>Second Class</td>
      <td>DV-13045</td>
      <td>Darrin Van Huff</td>
      <td>Corporate</td>
      <td>United States</td>
      <td>Los Angeles</td>
      <td>...</td>
      <td>90036</td>
      <td>West</td>
      <td>OFF-LA-10000240</td>
      <td>Office Supplies</td>
      <td>Labels</td>
      <td>Self-Adhesive Address Labels for Typewriters b...</td>
      <td>14.6200</td>
      <td>2</td>
      <td>0.00</td>
      <td>6.8714</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
      <td>US-2015-108966</td>
      <td>10/11/2015</td>
      <td>10/18/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>33311</td>
      <td>South</td>
      <td>FUR-TA-10000577</td>
      <td>Furniture</td>
      <td>Tables</td>
      <td>Bretford CR4500 Series Slim Rectangular Table</td>
      <td>957.5775</td>
      <td>5</td>
      <td>0.45</td>
      <td>-383.0310</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
      <td>US-2015-108966</td>
      <td>10/11/2015</td>
      <td>10/18/2015</td>
      <td>Standard Class</td>
      <td>SO-20335</td>
      <td>Sean O'Donnell</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Fort Lauderdale</td>
      <td>...</td>
      <td>33311</td>
      <td>South</td>
      <td>OFF-ST-10000760</td>
      <td>Office Supplies</td>
      <td>Storage</td>
      <td>Eldon Fold 'N Roll Cart System</td>
      <td>22.3680</td>
      <td>2</td>
      <td>0.20</td>
      <td>2.5164</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>9989</th>
      <td>9990</td>
      <td>CA-2014-110422</td>
      <td>1/21/2014</td>
      <td>1/23/2014</td>
      <td>Second Class</td>
      <td>TB-21400</td>
      <td>Tom Boeckenhauer</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Miami</td>
      <td>...</td>
      <td>33180</td>
      <td>South</td>
      <td>FUR-FU-10001889</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Ultra Door Pull Handle</td>
      <td>25.2480</td>
      <td>3</td>
      <td>0.20</td>
      <td>4.1028</td>
    </tr>
    <tr>
      <th>9990</th>
      <td>9991</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>FUR-FU-10000747</td>
      <td>Furniture</td>
      <td>Furnishings</td>
      <td>Tenex B1-RE Series Chair Mats for Low Pile Car...</td>
      <td>91.9600</td>
      <td>2</td>
      <td>0.00</td>
      <td>15.6332</td>
    </tr>
    <tr>
      <th>9991</th>
      <td>9992</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>TEC-PH-10003645</td>
      <td>Technology</td>
      <td>Phones</td>
      <td>Aastra 57i VoIP phone</td>
      <td>258.5760</td>
      <td>2</td>
      <td>0.20</td>
      <td>19.3932</td>
    </tr>
    <tr>
      <th>9992</th>
      <td>9993</td>
      <td>CA-2017-121258</td>
      <td>2/26/2017</td>
      <td>3/3/2017</td>
      <td>Standard Class</td>
      <td>DB-13060</td>
      <td>Dave Brooks</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Costa Mesa</td>
      <td>...</td>
      <td>92627</td>
      <td>West</td>
      <td>OFF-PA-10004041</td>
      <td>Office Supplies</td>
      <td>Paper</td>
      <td>It's Hot Message Books with Stickers, 2 3/4" x 5"</td>
      <td>29.6000</td>
      <td>4</td>
      <td>0.00</td>
      <td>13.3200</td>
    </tr>
    <tr>
      <th>9993</th>
      <td>9994</td>
      <td>CA-2017-119914</td>
      <td>5/4/2017</td>
      <td>5/9/2017</td>
      <td>Second Class</td>
      <td>CC-12220</td>
      <td>Chris Cortes</td>
      <td>Consumer</td>
      <td>United States</td>
      <td>Westminster</td>
      <td>...</td>
      <td>92683</td>
      <td>West</td>
      <td>OFF-AP-10002684</td>
      <td>Office Supplies</td>
      <td>Appliances</td>
      <td>Acco 7-Outlet Masterpiece Power Center, Wihtou...</td>
      <td>243.1600</td>
      <td>2</td>
      <td>0.00</td>
      <td>72.9480</td>
    </tr>
  </tbody>
</table>
<p>9994 rows × 21 columns</p>
</div>




```python
# Missing data
```


```python
pd.isna(store_df)
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
      <th>Row ID</th>
      <th>Order ID</th>
      <th>Order Date</th>
      <th>Ship Date</th>
      <th>Ship Mode</th>
      <th>Customer ID</th>
      <th>Customer Name</th>
      <th>Segment</th>
      <th>Country</th>
      <th>City</th>
      <th>...</th>
      <th>Postal Code</th>
      <th>Region</th>
      <th>Product ID</th>
      <th>Category</th>
      <th>Sub-Category</th>
      <th>Product Name</th>
      <th>Sales</th>
      <th>Quantity</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>3</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>9989</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>9990</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>9991</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>9992</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
    <tr>
      <th>9993</th>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>...</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
      <td>False</td>
    </tr>
  </tbody>
</table>
<p>9994 rows × 21 columns</p>
</div>




```python
store_df.mean()
```




    Row ID          4997.500000
    Postal Code    55190.379428
    Sales            229.858001
    Quantity           3.789574
    Discount           0.156203
    Profit            28.656896
    dtype: float64




```python
# Value counts (histogramming) / mode
```


```python
store_df["Product ID"].value_counts()
```




    OFF-PA-10001970    19
    TEC-AC-10003832    18
    FUR-FU-10004270    16
    TEC-AC-10002049    15
    FUR-CH-10002647    15
                       ..
    TEC-MA-10002927     1
    OFF-EN-10001535     1
    TEC-PH-10002352     1
    TEC-MA-10003329     1
    OFF-AP-10003099     1
    Name: Product ID, Length: 1862, dtype: int64




```python
# Grouping
```


```python
store_df.groupby("Segment")[["Sales", "Quantity"]].sum()
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
      <th>Sales</th>
      <th>Quantity</th>
    </tr>
    <tr>
      <th>Segment</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Consumer</th>
      <td>1.161401e+06</td>
      <td>19521</td>
    </tr>
    <tr>
      <th>Corporate</th>
      <td>7.061464e+05</td>
      <td>11608</td>
    </tr>
    <tr>
      <th>Home Office</th>
      <td>4.296531e+05</td>
      <td>6744</td>
    </tr>
  </tbody>
</table>
</div>




```python
store_df.groupby(["Segment", "Quantity"]).sum()

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
      <th></th>
      <th>Row ID</th>
      <th>Postal Code</th>
      <th>Sales</th>
      <th>Discount</th>
      <th>Profit</th>
    </tr>
    <tr>
      <th>Segment</th>
      <th>Quantity</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="14" valign="top">Consumer</th>
      <th>1</th>
      <td>2167147</td>
      <td>24651915</td>
      <td>27060.9409</td>
      <td>72.92</td>
      <td>2604.5362</td>
    </tr>
    <tr>
      <th>2</th>
      <td>6320458</td>
      <td>68669687</td>
      <td>145326.4684</td>
      <td>202.06</td>
      <td>16144.9808</td>
    </tr>
    <tr>
      <th>3</th>
      <td>6335218</td>
      <td>72013874</td>
      <td>218331.6111</td>
      <td>197.06</td>
      <td>30417.5499</td>
    </tr>
    <tr>
      <th>4</th>
      <td>3009449</td>
      <td>34883194</td>
      <td>171472.5852</td>
      <td>99.99</td>
      <td>24817.6500</td>
    </tr>
    <tr>
      <th>5</th>
      <td>3210312</td>
      <td>36578707</td>
      <td>216480.1065</td>
      <td>103.59</td>
      <td>23168.8015</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1430513</td>
      <td>15516801</td>
      <td>92880.5820</td>
      <td>49.10</td>
      <td>2709.8232</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1449554</td>
      <td>17042046</td>
      <td>112396.1188</td>
      <td>46.82</td>
      <td>15373.8235</td>
    </tr>
    <tr>
      <th>8</th>
      <td>564020</td>
      <td>6763389</td>
      <td>60388.8560</td>
      <td>19.95</td>
      <td>2304.6960</td>
    </tr>
    <tr>
      <th>9</th>
      <td>678543</td>
      <td>7458424</td>
      <td>59129.0811</td>
      <td>16.97</td>
      <td>6713.2071</td>
    </tr>
    <tr>
      <th>10</th>
      <td>118444</td>
      <td>1461188</td>
      <td>6932.6400</td>
      <td>4.20</td>
      <td>384.7850</td>
    </tr>
    <tr>
      <th>11</th>
      <td>103191</td>
      <td>1191954</td>
      <td>6462.6100</td>
      <td>2.20</td>
      <td>1473.1739</td>
    </tr>
    <tr>
      <th>12</th>
      <td>48334</td>
      <td>826043</td>
      <td>8242.6320</td>
      <td>1.00</td>
      <td>1065.9192</td>
    </tr>
    <tr>
      <th>13</th>
      <td>69440</td>
      <td>909859</td>
      <td>28467.3610</td>
      <td>2.75</td>
      <td>5376.2501</td>
    </tr>
    <tr>
      <th>14</th>
      <td>76706</td>
      <td>911528</td>
      <td>7829.7520</td>
      <td>2.30</td>
      <td>1564.0128</td>
    </tr>
    <tr>
      <th rowspan="14" valign="top">Corporate</th>
      <th>1</th>
      <td>1300098</td>
      <td>13236139</td>
      <td>15201.8972</td>
      <td>42.12</td>
      <td>2585.7225</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3709941</td>
      <td>40956142</td>
      <td>90716.0496</td>
      <td>112.19</td>
      <td>12413.3406</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3767027</td>
      <td>38659906</td>
      <td>128120.8929</td>
      <td>113.29</td>
      <td>15628.0644</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1729865</td>
      <td>18314300</td>
      <td>80542.7476</td>
      <td>52.07</td>
      <td>6384.7292</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2033666</td>
      <td>20554319</td>
      <td>140870.4050</td>
      <td>56.30</td>
      <td>20676.0360</td>
    </tr>
    <tr>
      <th>6</th>
      <td>887101</td>
      <td>9931391</td>
      <td>57946.5834</td>
      <td>27.27</td>
      <td>5679.4860</td>
    </tr>
    <tr>
      <th>7</th>
      <td>1005769</td>
      <td>11411990</td>
      <td>93850.3321</td>
      <td>35.94</td>
      <td>14493.4454</td>
    </tr>
    <tr>
      <th>8</th>
      <td>456386</td>
      <td>4966471</td>
      <td>36893.1600</td>
      <td>16.05</td>
      <td>6216.2808</td>
    </tr>
    <tr>
      <th>9</th>
      <td>314662</td>
      <td>3830481</td>
      <td>38345.6430</td>
      <td>13.50</td>
      <td>4492.0485</td>
    </tr>
    <tr>
      <th>10</th>
      <td>134213</td>
      <td>1284185</td>
      <td>12623.2940</td>
      <td>5.12</td>
      <td>600.1700</td>
    </tr>
    <tr>
      <th>11</th>
      <td>56296</td>
      <td>422520</td>
      <td>4081.9680</td>
      <td>0.80</td>
      <td>1130.1488</td>
    </tr>
    <tr>
      <th>12</th>
      <td>36734</td>
      <td>417031</td>
      <td>681.6240</td>
      <td>0.80</td>
      <td>262.8816</td>
    </tr>
    <tr>
      <th>13</th>
      <td>52805</td>
      <td>240143</td>
      <td>3418.7660</td>
      <td>1.30</td>
      <td>872.5106</td>
    </tr>
    <tr>
      <th>14</th>
      <td>20171</td>
      <td>311312</td>
      <td>2853.0040</td>
      <td>1.10</td>
      <td>544.2696</td>
    </tr>
    <tr>
      <th rowspan="14" valign="top">Home Office</th>
      <th>1</th>
      <td>952310</td>
      <td>10424801</td>
      <td>10989.0964</td>
      <td>22.47</td>
      <td>2250.2214</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2119274</td>
      <td>22810904</td>
      <td>53048.9618</td>
      <td>57.72</td>
      <td>9890.0874</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1840142</td>
      <td>21638739</td>
      <td>75608.0967</td>
      <td>59.02</td>
      <td>10969.9107</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1166911</td>
      <td>12143722</td>
      <td>71655.6616</td>
      <td>35.77</td>
      <td>13021.0116</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1143745</td>
      <td>12601649</td>
      <td>58311.1850</td>
      <td>33.40</td>
      <td>5671.7570</td>
    </tr>
    <tr>
      <th>6</th>
      <td>554746</td>
      <td>6041441</td>
      <td>56295.1560</td>
      <td>18.90</td>
      <td>1936.1586</td>
    </tr>
    <tr>
      <th>7</th>
      <td>435429</td>
      <td>5314503</td>
      <td>33661.9150</td>
      <td>15.40</td>
      <td>4419.7041</td>
    </tr>
    <tr>
      <th>8</th>
      <td>191275</td>
      <td>2840079</td>
      <td>20478.1600</td>
      <td>8.10</td>
      <td>2335.8192</td>
    </tr>
    <tr>
      <th>9</th>
      <td>294930</td>
      <td>2833088</td>
      <td>31030.8660</td>
      <td>7.70</td>
      <td>6482.6352</td>
    </tr>
    <tr>
      <th>10</th>
      <td>53191</td>
      <td>409184</td>
      <td>4500.7300</td>
      <td>1.55</td>
      <td>1059.2020</td>
    </tr>
    <tr>
      <th>11</th>
      <td>24803</td>
      <td>264868</td>
      <td>5227.9040</td>
      <td>0.30</td>
      <td>1690.0444</td>
    </tr>
    <tr>
      <th>12</th>
      <td>21689</td>
      <td>336546</td>
      <td>5944.1520</td>
      <td>0.80</td>
      <td>-143.7348</td>
    </tr>
    <tr>
      <th>13</th>
      <td>12307</td>
      <td>32315</td>
      <td>452.0620</td>
      <td>0.20</td>
      <td>100.1403</td>
    </tr>
    <tr>
      <th>14</th>
      <td>48200</td>
      <td>465874</td>
      <td>2449.2020</td>
      <td>1.00</td>
      <td>615.7214</td>
    </tr>
  </tbody>
</table>
</div>




```python
stacked = store_df.stack()
stacked
```




    0     Row ID                                                          1
          Order ID                                           CA-2016-152156
          Order Date                                              11/8/2016
          Ship Date                                              11/11/2016
          Ship Mode                                            Second Class
                                                ...                        
    9993  Product Name    Acco 7-Outlet Masterpiece Power Center, Wihtou...
          Sales                                                      243.16
          Quantity                                                        2
          Discount                                                        0
          Profit                                                     72.948
    Length: 209874, dtype: object




```python
pd.pivot_table(store_df, values="Sales", index=["Order ID", "Product ID"], columns=["Category"])
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
      <th>Category</th>
      <th>Furniture</th>
      <th>Office Supplies</th>
      <th>Technology</th>
    </tr>
    <tr>
      <th>Order ID</th>
      <th>Product ID</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>CA-2014-100006</th>
      <th>TEC-PH-10002075</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>377.970</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">CA-2014-100090</th>
      <th>FUR-TA-10003715</th>
      <td>502.488</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>OFF-BI-10001597</th>
      <td>NaN</td>
      <td>196.704</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>CA-2014-100293</th>
      <th>OFF-PA-10000176</th>
      <td>NaN</td>
      <td>91.056</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>CA-2014-100328</th>
      <th>OFF-BI-10000343</th>
      <td>NaN</td>
      <td>3.928</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>...</th>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th rowspan="5" valign="top">US-2017-169551</th>
      <th>OFF-PA-10004100</th>
      <td>NaN</td>
      <td>15.552</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>OFF-ST-10004835</th>
      <td>NaN</td>
      <td>13.392</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>TEC-AC-10002018</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>16.776</td>
    </tr>
    <tr>
      <th>TEC-AC-10003033</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>527.920</td>
    </tr>
    <tr>
      <th>TEC-PH-10001363</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>683.988</td>
    </tr>
  </tbody>
</table>
<p>9986 rows × 3 columns</p>
</div>




```python
store_df.to_csv("foo.csv")
```
