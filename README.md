# webcrawltakehome

1,000,000 rows, 13,670 Nan values in hostnameHash. 

Followup for later, why can't these be parsed?

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


Suppose you want to understand more about these hosts and their dependent requests.  What can you derive from this data?  

Some ideas:

* what does the distribution of dependent requests across hosts look like?  What other basic statistics might be interesting to describe this data?
<img src ='./img/distributionOfDependentRequests.png' >
Heavily skewed with a very long tail. 
In fact, looking at the summary statistics below, we can see 1/4 have 1 request, half have less than 5 and 3/4 have less than 18 request, while the last quartile slowly rockets up to 1430 requests!

* can you classify hosts into reasonable "types" based on these features?  Conceivably, www.google.com will look different from www.nytimes.com, but perhaps www.google.com and www.bing.com are similar?

Yes, the types could be derived by classifying based on number of dependent and requests and the content type of the requests.

One can one-hot-encode or make dummy variables for the contentType and use those values to classify the parentPageRequests.

* are there interesting correlations between dependent requests?

There certainly seems to be likely, I was not able to distill any concretely in the time alotted.

* any other interesting question you might want to answer...

Why are there NaN values for hostnameHash and why are there NaN for contentType?

