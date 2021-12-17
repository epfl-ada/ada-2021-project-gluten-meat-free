# This is a Man's word

### Authors: Caterina Calisti, Sofia Leonova, Mateusz Urbańczyk, Victor Amiot. 
Link to our story web page: https://tomatosoup97.github.io/epfl-ada--project-datastory/

## Abstract: 

In the 21st century gender inequality is still a global issue, which is evident in media content: women are under-represented with respect to men [1].

We aim to quantify this unbalance by analyzing the Quotebank dataset. First, we will investigate the distribution of quoted women vs men across the most common
speaker's countries of origin and then stratify them by their sociocultural and economic development, described by the Human Development Index. We intend to also compare the speaker's success on the media across genders, measured in terms of number of occurrences of the corresponding quotation, with statistical tests and graphs. Then, with visualisation methods and correlation analyses we aim to inspect the presence of any relationship between the speaker's gender and his/her occupation. Finally, we will extract keywords from the quotations, cluster them into topics and observe in which fields men's voices dominate with respect to women. All these factors could be predictors for the success of a quote on the media.

## Research questions:

-   How are the quotations distributed across the 10 most common speaker’s countries based on gender across the years?
-   Are women speakers from developing countries less represented than those from developed ones?
-   Are women-attributed quotes less successful than men-attributed quotes?
-   Are quotes attributed to women from developing countries less successful than those attributed to women from developed countries?
-   What is the evolution of the gender gap in countries with a different development level? Are we really going towards gender equality?
-   Are women less represented in high-placed occupations with respect to men?  
-	 Can we classify topics into male-oriented and female-oriented? Do men’s voices dominate in politics?
-	 Can we predict and explain the success of a quote based on features such as sex, occupation and nationality of the speaker?

## Proposed additional datasets:

The main dataset we will be using is the **Quotebank dataset** with millions of quotes and attributed speakers published in the English News between 2015 and 2020, enriched with additional **wikidata** about the speakers in the dataset, notably providing his/her nationality, religion, political party etc.

In addition to the Quotebank dataset, we will use the **Human Development Index dataset** from the 2020 report imported from United Nations website [2], which assigns to 189 countries a score from 0 to 1 based on the composite statistics of life expectancy, education and income indices. We will use this dataset to stratify the speaker’s nationality in the Quotebank dataset by the range in which their HDI falls from very high to low development.

## Methods:

### Reading and loading the dataset

- In order to tame the dataset size, we read the files by **chunks** while making sure that our process does not leak memory and does not exceede the available resources. As we read chunk by chunk, we aggregate the relevant information for further analyses and graphs. We execute the notebook on Google Colab.
- We preprocess the chunks for a given year, save them in a **pickle format file**, then free the RAM memory. Then, we concatenate the files from the same year into a unique pickle file and repeat these operations for every Quotebank data file specific for the years between 2015 and 2020. Finally we concatenate the preprocessed files from all the years into a unique file, also saved in picke format. 

### Data cleaning and preprocessing

This section involves two main tasks: 
1. Features cleaning

We discard those quotes with: 
- Missing speaker or speaker probability of quote attribution is lower than  60 %. 
- Missing speaker's gender or gender different from male and female. 
- Missing speaker's nationality. 
- Number of occurrences = 1

2. Processing of quotes

We will follow this pipeline to extract keywords from the quotations: 
- Normalize quotes: they are **lower-cased** and **punctuation marks** and **extra white** spaces are removed. 
- **Tokenize** quotes into a list of words.
- Train a model to find **bigrams** among the tokenized quotes and retain the most relevant ones.
- Apply a part-of-speech tagger (**POS-tagger**) to the extracted sequence of words to mainy retain only nouns and adjectives.
- Remove **stopwords** and a list of manually specified terms/bigrams to ignore.
- **Lemmatize** the remaining words.

### Data visualization and exploratory data analysis

We will use static and interactive plots to explore the data. 
More specifically, we will look at the distribution of quotes stratified by gender and/or occupation globally, and among countries grouped based on their development index. In order to do so, we will use **interactive histograms** to explore the evolution over the years, **pie charts** and **line plots**.

### Topic extraction and classification

We convert our keywords series into **bags of words** and use it to train a **Latent Dirichlet Allocation (LDA) model** for topic detection.
**Hyperparameter tuning** will be performed to obtain a high topic coherence score allowing to improve the quality of the learned topics.
The extracted topics will be visualized with **word clouds** graphs, their frequency with  **horizontal bar plots**, and their distribution across gender with **pie charts**.

### Statistical tests

Two **two-sample Kolmogorov-Smirnov tests** will be performed to help us compare the success of men vs women speakers, and the success of women from developed vs developing countries.

### Analyses of correlations

We will conduct a correlation analysis between the gender and occupation categorical variables with a **chi-squared test of independence** combined with **Cramer's scores**. This approach allows us to assess both the presence and the strength of the relationship.


### Linear Regression modelling

We fit a **linear regression model** and **gradient boosting regressor** to explain the number of occurrences of a quote, our outcome variable, with the previously studied features. An analysis of the coefficients is performed. 

## Internal Milestones and Timeline:

- *Dataset loading and preprocessing* (12th November)

- *Statistical tests and Correlation analyses* (19th November)

- *Extraction of topics and Model fitting* (4th December)
   
- *Story telling and presentation* (14th December)

- *Final touches and polishing* (Friday 17th December)

## Organization within the team: 

## Bibliography:

[[1](https://www.un.org/womenwatch/beijing15/Women_and_the_media_preliminary_brief.pdf)] *Women and the Media*, UN department of Public Information, 2010

[[2](http://hdr.undp.org/en/content/download-data)] United Nations HDI report download page
