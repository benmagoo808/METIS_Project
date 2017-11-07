
# METIS Intro to Data Science Project
## By: Ben McGauhey
### Seattle, WA Fall-2017


## An analysis of correlation between weather, location and crowds on crime

Data Science, as a growing field, offers incredible promise for a wide scope of applications. It can quantify and make reproducible the domain knowledge of experts. It is finding hidden effects in data sets that are beyond the human scale, while also automating processes by allowing machines to process streams of data such as only humans could a few years ago. The future seems quite bright. However, with each new solution, an unknown quantity of problems will be created. While machine learning and artificial intelligence aren't well understood by most, and this can create unfounded fears itself, there are an increasing number of savvy practitioners who are raising the alarm of possible problems as well. Some applications, particularly those in the realm of public safety have come under intense scrutiny as of late. Predictive policing is one of those most controversial applications. While lowering crime rates is a very valid and worthy goal, the potential for harm is quite high as well.

So in the spirit of exploring to better understand a subject, this project will tackle what would likely be the first steps in creating such a model. We wil be limiting the features to what should be fairly innocuous, location, weather and the occurence of special events. We will be gathering this data from a variety of sources, cleaning and merging it to create a single data set. We will then explore the data through visualization and statistical analysis to find the effect size of each feature. That knowledge will be used in our feature engineering and we will finally be utilizing some machine learning techniques to create a very simple predictive model.

### Without a question, there can be no answers
###_The question of this project will be:_

What if any is the effect of weather, location and large crowds on crime.

_We will use the following data:_

1. Seattle 911 data, Special Event Permits - Seattle City Open Data Portal.
2. Hourly weather records from SeaTac Airport - Weather Underground API.
3. Location Data - Embedded within the 911 and event data.

_What we know about the data:_

It is important to note that we are hoping to see the effects on crime, but we do not actually have that raw data. We will be using 911 calls as a proxy for crime, however this doesn't reflect crime which is not reported, has been filtered from the open data, or was responded to directly by law enforcement. Similarly, we really are interested in the effect of crowds, which is again by the proxy of permitted special events. There are many other reasons why crowds may form and there are many events which may not have been permitted. The weather data is from SeaTac airport, which may differ significantly from the local weather at the time and location of the events in our data. While every attempt has been made to find appropriate data, we can only use that which is available to us, and in this case it is not a direct record of the events we will be studying. We have limited the number of features we will be exploring even initally to keep the scope of this project within reason.

_Why this topic: _

Getting and cleaning data is often portrayed as 80% of a data scientists workflow. While I'm sure this is highly variable, for the projects I hope to work on in the near future, it will certainly be the case. For that reason, I am looking to create my own data set, from data in several different formats and from different sources. This will allow me to become more proficient at getting and cleaning data. I chose crime and weather, because it seemed an innocuous way to explore something that is getting a lot of attention lately. There are those who are saying predictive policing is great and those who say it is a great danger. This may help me better form an opinion. It is always a good idea to think skeptically of and with data.

_ Pre-conceptions:_

Before we look at the data, let's lay out some of the assumptions that we will be looking to disprove or verify.
1. Location, location, location. Certain locations are known to be home to certain demographics. Since we know that socioeconomic factors play a large part in driving crime, we can expect to see certain locations be a good predictor for certain types of crime. Affluent neighborhoods are more likely to report things such as loitering or suspicious persons. Business districts are unlikely to be the scene of domestic disturbances. We can expect location to be highly correlated with certain types of crime.
2. Crowd size and activity. The geographical concentration of a population is in constant flux. During the week, people congregate around employment centers and on evenings and weekends they are concentrated around residential areas. The effect of this movement will be reflected in crime rates if we look at individual areas in a time series. We also will see special events, which are represented in the data, positively correlate with crimes. Larger crowds are more likely to have assaults, spectator sports are more likely to have alcohol related crimes. We expect positive correlation between event size, and type and certain crimes.
3. Weather. Precipitation is likely to have a negative correlation with burglary, and freezing temperatures are likely to be positively correlated with trespassing or fire response as indigent populations seek warmth in small fires and shelter in protected entryways. We expect to see some positive and some negative correlations, the strength of which will be interesting to find.
