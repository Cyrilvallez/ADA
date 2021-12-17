<!-- # <a name="Title"></a> Is the climate debate unequal? -->


# <a name="abstract"></a> Abstract


It is no surprise to anyone reading this that climate change has been a topic of polarizing discussion for the last few years. Indeed, it becomes more and more apparent in the signs from nature (floods, heatwaves and so on) that something is happening and our societies are reacting. Consequently, measures are taken by decision makers about how to mitigate it. Scientists are getting interviewed, politicians give speeches and all of this is delivered by the media. Such influence can be studied through the analysis of who and what they quote in their articles. The Quotebank dataset offers such a possibility, thanks to its 178M quotes from which climate change related quotes can be filtered. In this sense, the goal of this study is to better understand how the climate change debate has been evolving with a focus on a few events that were pillars in the discussion.

# TODO LIST
* Who is talking about climate change (Nico)
    * ~~Carte des nationnalités (Cyril)~~
    * Occupation plot (Cyril)
* Natural events analysis (Nico)
* There is a disturbance in the media (Nico)
* Extra : male-female (Nico)
* Better plots
    * Volume plots (Adrien)
    * ~~Averages on sentiment plots (Charles)~~
    * ~~Superposition on gender plot (Charles)~~
* Events qui eclipsent le climat (Charles) 

# Table of Contents
1. [Abstract](#abstract)
2. [From 178 million quotes to "a few" hundred thousands](#intro)
3. [Who is talking about climate change?](#who)
4. [A timeline of climate debate](#timeline)
5. [Do we observe any seasonality?](#annualtrend)
6. [The eternal rivalry between republicans and democrats](#rep)
7. [A science issue for science people](#science)
8. [Trump here, Trump there, Trump everywhere...](#trump)
9. [Okay for politics, and what about natural events?](#nature)
10. [There is a disturbance in the debate...](#covid)
11. [Extra : And women in all of this?](#extra)
12. [Conclusion](#conclusion)



# <a name="intro"></a> From 178 million quotes to "a few" hundred thousands

Quotebank is a dataset of 178 million unique, speaker-attributed quotations that were extracted from 196 million English news articles crawled from over 377 thousand web domains between August 2008 and April 2020. The quotations were extracted and attributed using Quobert, a distantly and minimally supervised end-to-end, language-agnostic framework for quotation attribution.

To analyse the different events we have chosen, we first needed to determine which quotes were talking about climate change. To do so, we tested different methods but got the best results by just using a small lexicon of expressions linked to climate change (using only words would lead to unreliable results). The expressions we used are the following : ‘climate change’, ‘climate emergency’ and ‘global warming’. We wanted very general expressions, so as not to bias our future analysis. For example, we avoided including COP21 and COP26 in our lexicon to avoid the influence it could have on the nature of the quotes. We could have many other fancy methods to filter the dataset but at the end, it is usually enough to trust our instinct and choose the most logical words with a keyword analysis.

After some investigations in the dataset Quotebank, we noticed that there were holes of data during the year 2016. As such, to prevent its nefast influence, we decided to set a threshold on the number of quotes per day because these days tend to have significantly higher frequency of climate related quotes appearances. In the next figure, this effect is visually noticeable, (FIGURE SUPERPOSITION AVEC/SANS 2016),

# <a name="who"></a> Who is talking about climate change?


The identity of the speakers of the chosen quotes has to be properly defined to be able to understand possible inequalities. 

{% include beautiful_map.html %}

# <a name="timeline"></a> A timeline of climate debate


When looking at the count of quotes talking about climate change from 2015 to early 2020, what striked us, apart from the three distinct peaks, was the very low number of quotes during some months in 2016 and 2017. We need to take this into account when looking at frequency plots. Indeed if we plot the frequency of quotes talking about climate over all quotes from 2015 to 2020, we see some very important peaks around the low count months of 2016 and 2017. We must therefore ignore these months as a very low count skewes the frequencies way too high. The next graph represents the timeline of the quotes related to climate change in frequency in ‰ (defined by the number of climate quotes in a day divided by the total amount of quotes the same day). A linear regression has also been performed on the frequency of the said quotes. The slope of this regression is slightly positive and we notice that from 2018 until beginning of 2020, the trend is clearly increasing, juste before falling due to the Covid crisis, which shook (a bit) the world.

{% include Frequency.html %}


# <a name="annualtrend"></a> Do we observe any seasonality?
The next part is also interesting. We decided to put on the same graph the annual distribution of climate quotes from January to December. In those distribution, two seasonal patterns are noticeable. Unfortunately, due to the small amount of years in this dataset, it is difficult to extract any other pattern. Indeed, we would need more years to observe more precise trends. However, the mentioned patterns are due maybe due to the extreme events occuring usually more in the summer seasons. In june, there is a peak, related to the catastrophic events occuring in the US (for example the wildfires in the West coast and the hurricanes in the East coast). Also, in the "North hemisphere winter" months, an increasing trend is noticeable and it might also be related to natural events in the south hemisphere. As we tend to associate the month of november and december with cold weather, in the south it is the opposite. This is when wildfires are the most expected in Australia. As it is an English speaking country part of the Commonwealth, it is natural to expect many quotes related to this country in the Quotebank dataset. Moreover, we excluded the year 2020 because it was an incomplete annual dataset and the covid crisis has such a big influence from mid February that the trend would not be very speaking.


What else can cause these late increases? Each year, the emission gap report(EGR) is published by the UN to help decision makers to grasp the annual climatic situation. In other words, it is kind of like the little brother of the IPCC's report published every 6 to 7 years. However, its publication does not go unnoticed in the press as it triggers a spike in climate change related quotes. 

A weird behavior should still be mentioned : in 2018, the trend is almost only increasing the whole year. Did nothing happen this year ? Or people are juste becoming slowly and steadily more interested in climate change?

{% include Frequency_by_month.html %}

{% include Frequency_by_day.html %}

# <a name="rep"></a> The eternal rivalry between republicans and democrats

Let's now talk a little bit of politics ! Here it is noticeable that as expected, republicans talk less than democrates about climate change. Indeed, it has been reported in several reports that they consider climate change less as a top priority than democrats <sup>[1](#myfootnote1)</sup>. Republicans have historically been pretty skeptical about climate change, they tend to favor the development of their industries over the wellbeing of the atmosphere. Something quite surprising is the fact that the republicans even talk less and less about the climate. What do we do when we realise we are wrong about something? We tend to stay silent. In the same way Trump avoided talking about coronavirus after catching it, republicans might realise the urgency of mitigating the GHG emissions and are running out of arguments to counter argument this movement.


{% include imagetextright.html figname="prop_demo_rep_good.html" title="Another theory" description="> Another reason for this decrease might be related to the election in 2017 of Trump. Being the leader of the country with a great influence over his party, his scepticism towards global warming might have convinced his fellow politicians to talk less about it.  All the while, the trend for democrats remains very steady. It would be interesting to analyse this for previous years as well, it would show if this is a long term trend or not." %}


# <a name="science"></a> A science issue for science people

Let's now take a bigger perspective on the speakers and study the differences between the allocated quotes between researches and politicians. We should give more time of speech to scientists, right? They are the one knowing what they talk about, isn't it? Hell no! From the graph here below, it is clearly observable that scientists are not given that many opportunities to express their knowledge compared to politicians which are twice as many times quoted more than scientists. Even though it is not necessarily dramatic, as politicians are mainly the spokepersons of the people, giving more weight to the voices of the climatologists, anthropologists and so on would help to push the debate further. Indeed, as studies show it, people tend to trusting less and less their leaders<sup>[2](#myfootnote2)</sup>. 


{% include imagetextleft.html figname="politic_research.html" title="Vote for me !" description=">While the frequency of scientists quotes increases slowly over the period we’re studying, the frequency of politicians quotes go up significantly (31% vs 55% increase). This indicates that politicians are more and more involved in the climate debate possibly because of the growing public interest around the subject and therefore the proponent space it is starting to take in the public debate, to win an election now, you can’t ignore the climate debate. Is it related to actual concern on climate change or just as a political lever to get elected?" %}

# <a name="trump"></a> Trump here, Trump there, Trump everywhere...

Yes, it is him again ! From the timeline, it is clearly noticeable that the event causing the highest volume of quotes in the decision of Trump to leave the Paris' Agreements. As such, a sentimental analysis could be performed around this event. Here below, we observe that around the said date, 1st of June 2017, the sentiment is pretty negative. The horizontal plot is the sentiment mean, the red bars the negative ones and the blue ones the positive ones. Before and after the event, the distribution of sentiment ins pretty balanced, but Trump shifted this trend with his announcement that lead to a very negative sentiment. The million dollar question now is to determine if people were very concerned by the USA leaving the Agreements, or more about another event putting Trump in the spotlight?

{% include 2017-06-02_good_over.html %}

# <a name="nature"></a> Okay for politics, and what about natural events?

In this study, we look in details one of the major events of the previous years : the massive wildfires in Australia that lasted weeks and killed billions (yes yes, billions<sup>[3](#myfootnote3)</sup>!) of animals. When looking at the volume around these events, in january 2020, we observe that there is no massive peak, at least compared to the political/diplomatic events such as Trump's announcement or the COP21. We chose this event because it was happening in a country of the Commonwealth which usually have a significant amount of quotes. Nonetheless, this had no influence on the volume of quotes, or at least not enough. Do people care about these catastrophes?

<p float="left">
  <img src="_includes/VOLUME_TRUMP_scaled.png" width="100" />
  <img src="_includes/VOLUME_AUSTRALIA_scaled.png" width="100" /> 
</p>

# <a name="covid"></a> There is a disturbance in the debate...

From the volume study and as mentionned above, we have a significant drop of quote volume during the Covid crisis. This seems logical but has a deep significance. Climate change, in our developed country, is more a distant danger than an immediate threat. As the quotes are mainly coming from English speaking country such as the UK or North America, which are less subject to the environmental consequences of climate change, they heavily influenced by the actuality of those countries. Because global warming is a constant but mild threat in these regions of the world, news related to climate are expected to be easily replaced by more immediate information. Let's come back to the covid crisis. When every country had to close its borders, shops and schools, there were no more discussion on "oh let's talk about regulations to avoid elevation of the sea level in 20 years" when thousands of people were dying right now. Also, the quotes are heavily location-dependent. Island countries are at the frontline of the climate consequences.

{% include covid.html %}

# <a name="extra"></a> Extra : And women in all of this?

On top of climate change, gender inequalities is one of the most critical issues of our modern societies. It could be interesting to see, as a bonus to this study, how women are considered in the climate debate. Fortunately, we come (finally) with good news! When looking at the overall trend of speakers categorized by thy gender, we see that the climate debate is opened more and more for women. Even though it is still far from perfect parity in a context where it should, it looks like there is a convergence to the mean. Indeed, male speakers still have more quotations than non male speakers but the latter have an increasing trend, better than the overall trend when taking the entirety of the dataset(not just climate quotes). It is the same behavior for men : they have a decreasing overall fraction of quotes, and even more so when focusing in climate quotes. Maybe climate is a more open-minded topic than the average? Finally a positive touch!

{% include male_female_good.html %}

# <a name="conclusion"></a> Conclusion


# <a name="refs"></a> References

<a name="myfootnote1">[1]</a>: [Study on how different democrats and republicans are concerned about climate change](https://www.pewresearch.org/fact-tank/2020/02/28/more-americans-see-climate-change-as-a-priority-but-democrats-are-much-more-concerned-than-republicans/)

<a name="myfootnote2">[2]</a> : [Research done on the trust in the government by the US citizens](https://www.pewresearch.org/politics/2021/05/17/public-trust-in-government-1958-2021/)

<a name="myfootnote3">[3]</a> : [Australia's fires 'killed or harmed three billion animals'](https://www.bbc.com/news/world-australia-53549936)
