

## METIS Intro to Data Science Project
### By: Ben McGauhey
#### Seattle, WA Fall-2017


## Exploring the effects of weather on Seattle 911 Call Data

I decided to begin studying data science after hearing more and more about the field being a massively disruptive technology. There are pundits out there who speak to the wonderful opportunities data science will open and those who claim it will lead to our doom, exciting stuff, either way. After demystifying data science as the intersection of several subjects I have some knowledge of, I figured, why not try it out myself? See what the fuss is all about. That was almost a year ago. Now, further into my exploration and finally getting some formal education, getting my hands dirty and practicing has proven to be the best method for making the knowledge stick. Trying things out to see how they work is a crude explanation of the scientific method come to think of it, and that stuff works. Trust me, it's science. All kidding aside, I chose this project to provide practice for skills I need to sharpen, and to quench some curiosity.

Predictive policing has been in the news a bit lately, with proponents and adversaries both laying out convincing arguments. We could explore part of what might go into one of those models. Why not look at what effect the weather plays? It does have an effect, I have seen white papers showing a positive correlation between high heat and violent crime in large cities before. That is why I have chosen to examine the effects of weather on Seattle's 911 call data, which I am using as a proxy for crime. It is a far simpler project than predictive policing would be, and will allow me to practice combining and manipulating open data sources, which should provide some unforseen challenges.
 

### Without a question, there can be no answers
###_The question of this project will be:_

What predictive power can we find in the weather and location of a 911 call?

_We will use the following data:_

1. Seattle 911 data - Seattle City Open Data Portal.
2. Hourly weather records from SeaTac Airport - Weather Underground API.
3. Location Data - Embedded within the 911 data.

_What we know about the data:_

It is important to note that we are hoping to see the effects on crime, but we do not actually have that raw data. We will be using 911 calls as a proxy for crime, however this doesn't reflect crime which is not reported, has been filtered from the open data, or was responded to directly by law enforcement. Similarly, we really are interested in the effect of crowds, which is again by the proxy of permitted special events. There are many other reasons why crowds may form and there are many events which may not have been permitted. The weather data is from SeaTac airport, which may differ significantly from the local weather at the time and location of the events in our data. While every attempt has been made to find appropriate data, we can only use that which is available to us, and in this case it is not a direct record of the events we will be studying. We have limited the number of features we will be exploring even initally to keep the scope of this project within reason.

_Why this topic:_

Getting and cleaning data is often portrayed as 80% of a data scientists workflow. While I'm sure this is highly variable, for the projects I hope to work on in the near future, it will certainly be the case. For that reason, I am looking to create my own data set, from data in several different formats and from different sources. This will allow me to become more proficient at getting and cleaning data. I chose crime and weather, because it seemed an innocuous way to explore something that is getting a lot of attention lately. There are those who are saying predictive policing is great and those who say it is a great danger. This may help me better form an opinion. It is always a good idea to think skeptically of and with data.

_Pre-conceptions:_

Before we look at the data, let's lay out some of the assumptions that we will be looking to disprove or verify.
1. Location, location, location. Certain locations are known to be home to certain demographics. Since we know that socioeconomic factors play a large part in driving crime, we can expect to see certain locations be a good predictor for certain types of crime. Affluent neighborhoods are more likely to report things such as loitering or suspicious persons. Business districts are unlikely to be the scene of domestic disturbances. We can expect location to be highly correlated with certain types of crime.
2. Crowd size and activity. The geographical concentration of a population is in constant flux. During the week, people congregate around employment centers and on evenings and weekends they are concentrated around residential areas. The effect of this movement will be reflected in crime rates if we look at individual areas in a time series. We also will see special events, which are represented in the data, positively correlate with crimes. Larger crowds are more likely to have assaults, spectator sports are more likely to have alcohol related crimes. We expect positive correlation between event size, and type and certain crimes.
3. Weather. Precipitation is likely to have a negative correlation with burglary, and freezing temperatures are likely to be positively correlated with trespassing or fire response as indigent populations seek warmth in small fires and shelter in protected entryways. We expect to see some positive and some negative correlations, the strength of which will be interesting to find.
