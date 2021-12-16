# <a name="abstract"></a> Abstract


It is no surprise to anyone reading this that climate change has been a topic of polarizing discussion for the last few years. Indeed, it becomes more and more apparent in the signs from nature (floods, heatwaves and so on) that something is happening and our societies are reacting. Consequently, measures are taken by decision makers about how to mitigate it. Scientists are getting interviewed, politicians give speeches and all of this is delivered by the media. Such influence can be studied through the analysis of who and what they quote in their articles. The Quotebank dataset offers such a possibility, thanks to its 50M quotes from which climate change related quotes can be filtered. In this sense, the goal of this study is to better understand how the climate change debate has been evolving with a focus on a few events that were pillars in the discussion.

# Table of Contents
1. [Abstract](#abstract)
2. [Objectives](#objectives)
3. [Introduction](#intro)
4. [Methods](#methods)
5. [The Quotebank dataset](#quotebank)
6. [The choice of the events](#choice)
7. [Event Analysis](#reaction)
8. [Identity of the speakers](#identity)
9. [Focus on the political spectrum of the speakers](#politics)
10. [What is the most impactful?](#impact)

# <a name="objectives"></a> Objectives

* How the dataset was filtered?
* What are the characteristics of the reaction with respect to each event? Does any seasonality appear and how does the volume evolve?
* What is the identity of the speakers of such quotes? Who are the most quoted between the politicians and the scientists?
* Focusing on the politicians speakers, what is the respective position towards climate change for each type of party?
* What class of events is the most impactful ??????????????????????????????

# <a name="intro"></a> From 178 million quotes to "a few" hundred thousands

Quotebank is a dataset of 178 million unique, speaker-attributed quotations that were extracted from 196 million English news articles crawled from over 377 thousand web domains between August 2008 and April 2020. The quotations were extracted and attributed using Quobert, a distantly and minimally supervised end-to-end, language-agnostic framework for quotation attribution.

To analyse the different events we have chosen, we first needed to determine which quotes were talking about climate change. To do so, we tested different methods but got the best results by just using a small lexicon of expressions linked to climate change (using only words would lead to unreliable results). The expressions we used are the following : ‘climate change’, ‘climate emergency’ and ‘global warming’. We wanted very general expressions, so as not to bias our future analysis. For example, we avoided including COP21 and COP26 in our lexicon to avoid the influence it could have on the nature of the quotes. We could have many other fancy methods to filter the dataset but at the end, it is usually enough to trust our instinct and choose the most logical words with a keyword analysis.

When looking at the count of quotes talking about climate change from 2015 to early 2020, what striked us, apart from the three distinct peaks, was the very low number of quotes during some months in 2016 and 2017. We need to take this into account when looking at frequency plots. Indeed if we plot the frequency of quotes talking about climate over all quotes from 2015 to 2020, we see some very important peaks around the low count months of 2016 and 2017. We must therefore ignore these months as a very low count skewes the frequencies way too high.



# <a name="methods"></a> Methods

A GARDER OU NON
The first task we need to tackle is to extract quotes that are related to climate change. For this we established a list of words related to this subject and filtered out the quotes that did not contain any of those words. This method seems sufficient during our testing and was much more efficient than using a pre-trained classifier.

We will also expand the dataset to add information about the speakers (using Wikidata), for instance, their political party, if they are politicians (maybe focused on the USA for parties consistency). During our testing we also performed sentiment analysis, using a pre-trained model shipped with `nltk`, this might become useful to answer questions about how different people adress the climate issue.

Once we have constructed this dataset, we will want to visualize the frequency of quotes regarding the subject and see if any peaks are detectable. To detect the peaks we will implement a method to find local maxima on different scales (weeks or days). One of the main goals of this project is to create a baseline trend for the increase of climate discussions and to identify the outliers to try and link them to particular events. To be able to detect which event corresponds to a particular set of quotes, we also study the most common words cited using `nltk`, by first removing stopwords, punctuation and also words we used to identify quotes related to climate. 

We could try in the future in our datastory blog to incorporate interactiveness to the data. This would be done by allowing the viewer to "click" on peakdays, discover by themselves the most mentioned words and deduce what would be the event.

After some investigations in the dataset Quotebank, we noticed that there were holes of data during the year 2016. As such, to prevent its nefast influence, we decided to set a threshold on the number of quotes per day because these days tend to have significantly higher frequency of climate related quotes appearances. In the next figure, this effect is visually noticeable, (FIGURE SUPERPOSITION AVEC/SANS 2016),

# <a name="choice"></a> Which events did we choose?


Visually, events can be found thanks to the occurence of quotes related to this lexic. 

{% include Frequency.html %}

{% include Count.html %}
Looking at the next trends on the frequency of climate change related quotes, we notice that there is almost each year a higher activity towards the end of the year. Why so? Each year, the emission gap report(EGR) is published by the UN to help decision makers to grasp the annual climatic situation. In other words, it is kind of like the little brother of the IPCC's report published every 6 to 7 years. However, its publication does not go unnoticed in the press as it triggers a spike in climate change related quotes. It might also be related to natural events in the south hemisphere. As we tend to associate the month of november and december with cold weather, in the south it is the opposite. This is when wildfires are the most expected in Australia. As it is an English speaking country part of the Commonwealth, it is natural to expect many quotes related to this country in the Quotebank dataset.


{% include Frequency_by_month.html %}

{% include Frequency_by_day.html %}

Let's now talk a little bit of politics ! Here it is noticeable that as expected, republicans talk less than democrates about climate change. Indeed, it has been reported in several reports that they consider climate change less as a top priority than democrates (source : https://www.pewresearch.org/fact-tank/2020/02/28/more-americans-see-climate-change-as-a-priority-but-democrats-are-much-more-concerned-than-republicans/). Something quite surprising is the fact that the republicans even talk less and less about the climate. What do we do when we realise we are wrong about something? We tend to stay silent. In the same way Trump avoided talking about coronavirus after catching it, republicans might realise the urgency of mitigating the GHG emissions and are running out of arguments to counter argument this movement. This is a first theory, another one might be related to the election in 2017 of Trump. Being the leader of the country with a great influence over his party, his scepticism towards global warming might have convinced his fellow politicians to talk less about it.
{% include democratic_republican.html %}

{% include politic_research.html %}

{% include sentiment_2015.html %}

{% include sentiment_2016.html %}

{% include sentiment_2017.html %}

{% include sentiment_2018.html %}

{% include sentiment_2019.html %}

{% include sentiment_2020.html %}

{% include sentiment_australia.html %}

{% include sentiment_cop21.html %}

{% include sentiment_sept_strikes.html %}

{% include sentiment_trump.html %}
* The withdrawal of the USA from the Paris' agreements 
* The COP21 event
* A hurricane in the USA
* The OurOcean event in Washington DC

# <a name="reaction"></a> What are the characteristics of the events?

Exploring the volume of quotes related to each event can show how the evolution of the debate look like. Do we have less quotations *right* after the day of the event? Or is there any build up of the number of quotes right **before** the event?

# <a name="identity"></a> Who is talking about climate change?

# <a name="politics"></a> When we focus on the politics related speakers, how does the political spectrum looks like?

# <a name="impact"></a> And the biggest impact is attributed to...
