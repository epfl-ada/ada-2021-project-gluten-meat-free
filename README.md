# This is a Man's word

## Abstract: 

In the 21st century gender inequality is still a global issue, which is evident in media content: women are under-represented with respect to men [1].

We aim to quantify this unbalance by analyzing the Quotebank dataset. Our analysis will be directed towards the presence of women throughout countries and the most occuring topics. First, we will investigate the distribution of quoted women across the most common occupations, globally. Then, we will inspect the presence of any correlations between the speaker's success on the media, measured in terms of number of occurrences of the corresponding quotation, and the sociocultural and economic development of the speaker's country, described by Human Development Index. Finally, we will extract keywords from the quotations, cluster them into topics and observe in which fields men's voices dominate with respect to women. All these factors could be predictors for the success of a quote on the media.

## Research questions: 
-	Are women’s speech and opinions more valued and represented in the media in developed countries? 
-	How are the quotations distributed across countries based on the gender?
-	Are women less represented in high-placed occupations in developing countries? 
-	Can we classify topics into male-oriented and female-oriented? Do men’s voices dominate in politics?
-	Can we predict and explain the success of a quote based on features such as sex, occupation and nationality of the speaker?

## Proposed additional datasets: 
The main dataset we will be using is the Quotebank dataset with millions of quotes and attributed speakers published in the English News between 2015 and 2020, enriched the original Quotebank data with 
additional metadata about the speakers in the dataset, notably providing his/her nationality, religion, political party etc.

In addition to the Quotebank dataset, we will use the Human Development Index dataset from the 2020 report imported from United Nations website [2], which assigns to 189 countries a score from 0 to 1 based on the composite statistics 
of life expectancy, education and income indices. We will use this dataset to stratify the speaker’s nationality in the Quotebank dataset by the range in which their HDI falls 
from very high to low development.

## Methods: 
- In order to tame the dataset size, we read the files by chunks while making sure that our process does not leak memory and does not exceede the available resources. As we read chunk by chunk, we aggregate the relevant information for further analyses and graphs. So far, we have executed the notebook on Google Colab.
- For data cleaning and preprocessing part we discard quotes without attributed speakers since it crucial to obtain further metadata such as the speaker’s nationality, occupation and gender. Additional static and interactive plots to show the distribution of these features will be implemented. While it would be thrilling to embark on analysis of inequality with respect to LGBT speakers, we do not have sufficient data to draw any conclusions from it, thus we also discard it and leave only male and female speakers.
- We will perform tests for correlations to assess any relationships between the features and the success of the quote, hoping to see if gender plays a significant role here.
-	The keywords are extracted from the quotations by applying some basic functions from the natural language toolkit (nltk) library including tokenization of the sentence, exclusion of stopwords and lemmatization.
-	Natural language processing techniques for clustering (e.g Latent Dirichlet Allocation) will be assessed to identify topics groups from the quotes content. 

## Internal Milestones and Timeline:

- *Dataset acquaintance* (12th November)
    - data processing suitable to the dataset size
    - merging other resources
    - pre-processing, data cleaning
    - inspecting the most occurring keywords in quotes. 

- *Correlation analyses* (19th November)
    - assess available tools for correlation analyses
    - plot graphs and draw conclusions from results

- *Model fitting* (4th December)
    - predict the success of a quote based on selected features (gender, nationality)
    - classify the keywords into topics using NLP methods
    - derive presence of male and female across extracted topics

- *Story telling and presentation* (14th December)
    - built datastory and website
    - beautify the page, ensure graphs are readable by external audience 
    - organize and clean the code structure

-	*Final touches and polishing* (Friday 17th December)


## Questions for the TAs: 



## Bibliography:

[[1](https://www.un.org/womenwatch/beijing15/Women_and_the_media_preliminary_brief.pdf)] *Women and the Media*, UN department of Public Information, 2010

[[2](http://hdr.undp.org/en/content/download-data)] United Nations HDI report download page
