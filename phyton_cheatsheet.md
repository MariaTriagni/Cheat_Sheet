
### Merge 2 dataframe by FK
df_TorontoPostalCodeGeospatial = pd.merge( df_postalcode, df_geospatial,  on='Postcode')

### Rename column
df_geospatial.rename(columns={"Postal Code": "Postcode"}, inplace = True )

### Looping for rows in dataframe
for index, row in df_postalcode.iterrows():
   df_postalcode.at[index,'latitude'] = location.latitude
   df_postalcode.at[index,'longitude'] = location.longitude 
   print (row['Borough'], row['Neighbourhood'])

### Add empty column 
df_postalcode['latitude']=0.0
df_postalcode['longitude']=0.0

### Read csv file from github
import pandas as pd 
url = "https://raw.githubusercontent.com/MariaTriagni/Data/master/" + torontoNeighbourghoodCoordFile
print(url)
data = pd.read_csv(url) 
data.head()

### Write csv file to Google Colab (we are not able to write csv file to github)
from google.colab import drive
  drive.mount('drive')
  data.to_csv("test.csv")
  !cp test.csv "drive/My Drive/Colab Notebooks"

### Add data asset to IBM Watson
https://developer.ibm.com/answers/questions/439006/how-can-i-add-a-file-to-data-asset-by-notebook/