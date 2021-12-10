# <a name="abstract"></a> Abstract


Climate change became a real threat in the last decades. With the Quotebank dataset, it is possible to map the relation between its impacts and public opinion. Major events are inflating this debate. Indeed, human nature leads us to be concerned either by events impacting our personal lives, or by spectacular ones. As such, we seek to study the reaction of media with respect to events. By selecting several events related to climate change in the dataset, we can study the reaction they generate and consequently their impact. As such, it will be possible to make clear distinctions between the respective types of these events and how the sentiment towards them are evolving along the years.

trouver les caractéristiques des réactions aux evenements pour étudier ces réactions et leur impact sur le débat public 

# Table of Contents
1. [Abstract](#abstract)
2. [Objectives](#objectives)
3. [Methods](#methods)
4. [The choice of the events](#choice)
5. [The nature of the reaction](#reaction)
6. [What is the most impactful?](#impact)
7. [Fourth Example](#fourth-examplehttpwwwfourthexamplecom)


# <a name="objectives"></a> Objectives

* What are the chosen events and what are their nature?
* What are the characteristics of the reaction with respect to each event (volume, sentiment,etc.)?
* What kind of event is the most impactful ?
* Does the location of the event matter and do different countries uniformly report the news ?
* PEUT ETRE : Can we elaborate the sentiment analysis with a pronoun analysis?


# <a name="methods"></a> Methods

The first task we need to tackle is to extract quotes that are related to climate change. For this we established a list of words related to this subject and filtered out the quotes that did not contain any of those words. This method seems sufficient during our testing and was much more efficient than using a pre-trained classifier.

We will also expand the dataset to add information about the speakers (using Wikidata), for instance, their political party, if they are politicians (maybe focused on the USA for parties consistency). During our testing we also performed sentiment analysis, using a pre-trained model shipped with `nltk`, this might become useful to answer questions about how different people adress the climate issue.

Once we have constructed this dataset, we will want to visualize the frequency of quotes regarding the subject and see if any peaks are detectable. To detect the peaks we will implement a method to find local maxima on different scales (weeks or days). One of the main goals of this project is to create a baseline trend for the increase of climate discussions and to identify the outliers to try and link them to particular events. To be able to detect which event corresponds to a particular set of quotes, we also study the most common words cited using `nltk`, by first removing stopwords, punctuation and also words we used to identify quotes related to climate. 

We could try in the future in our datastory blog to incorporate interactiveness to the data. This would be done by allowing the viewer to "click" on peakdays, discover by themselves the most mentioned words and deduce what would be the event.

# <a name="choice"></a> Which events did we choose?

The selection of the studied events is crucial for this analysis. In order to find the best samples, machine learning could have been a solution but doing a keyword based analysis will definitely do the job. Then, a variety of key workds have been selected to filter the data set and focus on climate change.

lexic_small = ['climate change', 'climate emergency', 'global warming', 'COP21', 'COP26']

Visually, events can be found thanks to the occurence of quotes related to this lexic. 

GRAPH GRAPH GRAPH

* The withdrawal of the USA from the Paris' agreements 
* The COP21 event
* A hurricane in the USA
* The OurOcean event in Washington DC

# <a name="reaction"></a> What is the nature of the event reactions?

# <a name="impact"></a> And the biggest impact is attributed to...



You can use the [editor on GitHub](https://github.com/Cyrilvallez/ADA/edit/gh-pages/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.








# Some Helpers

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/Cyrilvallez/ADA/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
