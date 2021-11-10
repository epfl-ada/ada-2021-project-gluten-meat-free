# IPSE DIXIT or This is a Man's word (go check out the song This is a Man's world)

## Abstract: 

In the 21st century gender inequality is still a global issue, which is evident in media content: women are under-represented with respect to men [1].

[[1](https://www.un.org/womenwatch/beijing15/Women_and_the_media_preliminary_brief.pdf)] *Women and the Media*, UN department of Public Information, 2010

We aim to quantify this unbalance by analyzing the Quotebank dataset. First, we will investigate the distribution of women across the most common occupations, globally. 
Then, we will inspect the presence of any correlations between the speaker's success on the media, measured in terms of number of occurrences of the corresponding quotation, 
and the  sociocultural and economic development of the speaker's original country, described by the Human Development Index (HDI). 
Finally, we plan to extract keywords from the quotations of the dataset, cluster them into topics and observe in what fields 
men's voices dominate with respect to women. Ideally, all these factors could be predictors for the success of a quote on the media.


## Research questions: 
-	Are women’s speech and opinions more valued and represented in the media in developed countries? 
-	How are the quotations distributed across countries based on the gender?
-	Are women less represented in high-placed occupations in developing countries? 
-	Do men’s voices dominate in “hard” quotes with topics about politics etc?
-	Can we predict and explain the success of a quote based on some features such as the sex, occupation and nationality of the speaker?

## Proposed additional datasets: 
The main dataset we will be using is the Quotebank dataset with millions of quotes and attributed speakers published in the English News between 2015 and 2020, enriched the original Quotebank data with 
additional metadata about the speakers in the dataset, notably providing his/her nationality, religion, political party etc.

In addition to the Quotebank dataset we will use the Human Development Index dataset from the 2020 report imported from Wikipedia [2], which assigns to 189 countries a score from 0 to 1 based on composite statistics 
of life expectancy, education and income indices. We will use this dataset to stratify the speaker’s nationality countries in the Quotebank dataset  by the range in which their HDI falls 
from very high to low development.
[[2] (https://en.wikipedia.org/wiki/Human_Development_Index)]

## Methods: 
-	In order to work on such huge data, we decided to read the files by chunks, to save the relevant information for further analyses and graphs locally and to clear the chunk 
from the memory after terminating the processing on it. So far, we have executed the notebook on Google Cholab.
-	Some data cleaning and data preprocessing is applied to each chunk: those quotes without attributed speaker were dropped since for the further analyses we will need as 
features the speaker’s nationality, occupation and gender. Additional static and interactive plots to show the distribution of these features will be implemented.
- Tests for correlations will be performed to assess any relationships between the features and the success of the quote.
-	The keywords are extracted from the quotations by applying some basic functions from the natural language toolkit (nltk) library including tokenization of the sentence, exclusion of stopwords and lemmatization.
-	Machine learning techniques for clustering (e.g Latent Dirichlet Allocation) will be tested to identify topics from the quotes content. 

## Proposed timeline: 

-	12th November: complete data loading, merging, pre-processing and writing of functions for the extractions of most occurring keywords in quotes. 

-	19th November: create additional graphs, and start the correlation analyses. 

-	26th November - 4th December : model fitting for prediction of number of occurrences, clustering of keywords in topics per male/female 

-	4th December – 16th December: built datastory and website, beautify the page and clean the code 

-	Friday 17th December: Milestone 3 deadline 

## Organization within the team: 

- Caterina: 

- Mateusz: 

- Sofia: 

- Victor: 

## Questions for the TAs: 




