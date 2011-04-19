Force.com Toolkit for Google Analytics
======================================  

Files
-----

The toolkit contains the following elements for integrating Google Analytics data into Salesforce and Force.com applications:  

### Custom Settings

Site Metric Settings - login and table for Google Analytics

### Custom Objects

Site Metric Date - date range or single date for a Site Metric
Site Metric - a standard metric           
Site Event - a custom event        

### Classes

GoogleAnalytics - methods to login, request, and parse analytics data into temporary Entry objects  
ImportGoogleAnalytics - sample import code; requires creation of Site Metric Settings

### Triggers

SiteMetric_Time - populate human-readable time field for select metrics (ie. Average Time on Site)     

Setup
-----

# In Setup > Security Controls > Remote Site Settings, add the site https://www.google.com
# In Setup > Develop > Custom Settings, select Manage next to Site Metric Settings and enter your Google Analytics email and password   
## To find the Table Id for your site, you can use the [Google Analytics Data Feed Query Explorer](http://code.google.com/apis/analytics/docs/gdata/gdataExplorer.html)  

Run Samples
-----------

In the System Log, execute one of the following commands:  

* ImportGoogleAnalytics.importSingleMetric(name)
* ImportGoogleAnalytics.importDailyMetrics(name)
* ImportGoogleAnalytics.importEvents(name)    

where name is a string with the name of the Custom Settings you created in Setup.   

The result should be a series of Site Metric Date, Site Metric, and Site Event records.
You may need to adjust the dates in ImportGoogleAnalytics to match activity dates for your site.
