# <a name="abstract"></a> Abstract


Climate change became a real threat in the last decades. With the Quotebank dataset, it is possible to map the relation between its impacts and public opinion. Major events are inflating this debate. Indeed, human nature leads us to be concerned either by events impacting our personal lives, or by spectacular ones. As such, we seek to study the reaction of media with respect to events. By selecting several events related to climate change in the dataset, we can study the reaction they generate and consequently their impact. As such, it will be possible to make clear distinctions between the respective types of these events and how the sentiment towards them are evolving along the years.

trouver les caractéristiques des réactions aux evenements pour étudier ces réactions et leur impact sur le débat public 

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

* What are the chosen events and what are their nature?
* What are the characteristics of the reaction with respect to each event? Does any seasonality appear and how does the volume evolve?
* What is the identity of the speakers of such quotes? Who are the most quoted between the politicians and the scientists?
* Focusing on the politicians speakers, what is the respective position towards climate change for each type of party?
* What class of events is the most impactful ??????????????????????????????

# <a name="intro"></a> The Quotebank dataset


# <a name="methods"></a> Methods

The first task we need to tackle is to extract quotes that are related to climate change. For this we established a list of words related to this subject and filtered out the quotes that did not contain any of those words. This method seems sufficient during our testing and was much more efficient than using a pre-trained classifier.

We will also expand the dataset to add information about the speakers (using Wikidata), for instance, their political party, if they are politicians (maybe focused on the USA for parties consistency). During our testing we also performed sentiment analysis, using a pre-trained model shipped with `nltk`, this might become useful to answer questions about how different people adress the climate issue.

Once we have constructed this dataset, we will want to visualize the frequency of quotes regarding the subject and see if any peaks are detectable. To detect the peaks we will implement a method to find local maxima on different scales (weeks or days). One of the main goals of this project is to create a baseline trend for the increase of climate discussions and to identify the outliers to try and link them to particular events. To be able to detect which event corresponds to a particular set of quotes, we also study the most common words cited using `nltk`, by first removing stopwords, punctuation and also words we used to identify quotes related to climate. 

We could try in the future in our datastory blog to incorporate interactiveness to the data. This would be done by allowing the viewer to "click" on peakdays, discover by themselves the most mentioned words and deduce what would be the event.


# <a name="quotebank"></a> The Quotebank dataset

Quotebank is a dataset of 178 million unique, speaker-attributed quotations that were extracted from 196 million English news articles crawled from over 377 thousand web domains between August 2008 and April 2020. The quotations were extracted and attributed using Quobert, a distantly and minimally supervised end-to-end, language-agnostic framework for quotation attribution.


# <a name="choice"></a> Which events did we choose?

The selection of the studied events is crucial for this analysis. In order to find the best samples, machine learning could have been a solution but doing a keyword based analysis will definitely do the job. Then, a variety of key workds have been selected to filter the data set and focus on climate change.

lexic_small = ['climate change', 'climate emergency', 'global warming', 'COP21', 'COP26']

Visually, events can be found thanks to the occurence of quotes related to this lexic. 

{% include Frequency.html %}

{% include Count.html %}

Looking at the next trends on the frequency of climate change related quotes, we notice that there is almost each year a higher activity towards the end of the year, especially in 2016. Why so? Each year, the emission gap report(EGR) is published by the UN to help decision makers to grasp the annual climatic situation. In other words, it is kind of like the little brother of the IPCC's report published every 6 to 7 years. However, its publication does not go unnoticed in the press as it triggers a spike in climate change related quotes. Something even more surprising is the peak of quotes in 2016 specifically. It is even more intense than the others. This reason might be related to the COP21 conference that was held 1 year prior. Indeed, many signatures were made, many political promises were said, and the first EGR after this conference was even more expected thant the others. 'One year after the confenrece of the decade, did the situation get better?' were screaming the many related articles(spoiler : not much).

{% include Frequency_by_month.html %}

{% include Frequency_by_day.html %}

Let's now talk a little bit of politics ! Here it is noticeable that as expected, republicans talk less than democrates about climate change. Indeed, it has been reported in several reports that they consider climate change less as a top priority than democrates (source : https://www.pewresearch.org/fact-tank/2020/02/28/more-americans-see-climate-change-as-a-priority-but-democrats-are-much-more-concerned-than-republicans/). Something quite surprising is the fact that the republicans even talk less and less about the climate. What do we do when we realise we are wrong about something? We tend to stay silent. In the same way Trump avoided talking about coronavirus after catching it, republicans might realise the urgency of mitigating the GHG emissions and are running out of arguments to counter argument this movement. This is a first theory, another one might be related to the election in 2017 of Trump. Being the leader of the country with a great influence over his party, his scepticism towards global warming might have convinced his fellow politicians to talk less about it.
{% include democratic_republican.html %}

{% include all_years.html %}

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
