# webcrawltakehome

1,000,000 rows, 13,670 Nan values in hostnameHash. Followup for later, why can't these be parsed?
For now we will drop the NaN hostnameHash leaving us with 986,330 rows.
<class 'pandas.core.frame.DataFrame'>
Int64Index: 986330 entries, 0 to 999998
Data columns (total 8 columns):
hostnameHash              986330 non-null object
parentPageGuid            967521 non-null object
pageGuid                  986330 non-null object
httpResponseCode          986330 non-null int64
responseBodyMD5           985057 non-null object
responseBodySize          806484 non-null float64
contentType               939102 non-null object
contentType_list_lower    939102 non-null object
dtypes: float64(1), int64(1), object(6)
memory usage: 67.7+ MB

