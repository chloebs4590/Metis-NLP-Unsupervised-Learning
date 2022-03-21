## Identifying topics in the New York Times' *Modern Love* column

### Abstract:

This project performs topic modeling on essays and short stories from the New York Times'[Modern Love](https://www.nytimes.com/column/modern-love) column. The objective was to identify interpretable topics that can be used to help the New York Times add topic links to their website so users can have more guided options for filtering their searches.

### Data and Design

The data for this project was acquired from the New York Times' website via its API (see code [here](https://github.com/chloebs4590/NLP-Unsupervised-Learning/blob/master/NY%20Times%20API%20data%20extraction.ipynb)) and web scraping (see code [here](https://github.com/chloebs4590/NLP-Unsupervised-Learning/blob/master/Essays%20Web%20Scraping.ipynb)).

After data acquisition, the dataset was first cleaned to remove pieces that weren't essays or short stories (i.e., they were podcast transcriptions or announcements about the column). Ultimately, there were 1458 essasy/short stories in the cleaned dataset.

The column in the dataset containing the text from the full essays/short stories (i.e., the corpus) was preprocessed to remove punctuation, numbers and stop words. Words were also converted to lowercase and lemmatized. Next, the corpus was vectorized using CountVectorizer or TF-IDF, depending on the topic modeling algorithm. Then, the corpus was fit on models from three topic modeling algorithms: LDA, NMF and CorEx. The best versions of the NMF and CorEx models were evaluated using new short stories published after the initial essays and short stories were acquired.

### Algorithms

Text preprocessing:
- Removed introductory text present in some essays that was not part of the narrative
- Removed text from links within essays
- Removed punctuation, numbers and stop words (including those from spaCy and custom ones)
- Converted all characters to lowercase
- Applied standard and customized lemmatization to words
- Vectorized text via CountVectorizer and TfidfVectorizer

Modeling:
Fit and tuned LDA, NMF and CorEx models. A tuned NMF model was chosen as the final model due to its ability to more appropriately assign topics to four new short stories compared to a tuned CorEx model.

### Tools
- New York Times API and Requests for data acquisition
- BeautifulSoup, Numpy, Pandas, SpaCy for data cleaning and preprocessing
- LDA, NMF and CorEx for topic modeling
- Seaborn/Matplotlib and Tableau for data visualizations

### Communication

The presentation for this project is saved in this project's repo. The visualization created in Tableau is saved [here](https://public.tableau.com/app/profile/chloe.bergsma.safar/viz/ChartforMetis5Project-NLPandUnsupervisedLearning/ofDocsperTopicDash?publish=yes).
