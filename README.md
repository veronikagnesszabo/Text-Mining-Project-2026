# Text-Mining-Project-2026 on Sentiment Analysis / Polarization in Ted Talks

***Group Members***
Veronika Szabo
Elijus Sinkeviciute
Ziyu Zhou
Tianrun Wang


## Abstract
In our text mining project we would like to look at the different emotional scales of Ted talks when comparing the theme groups psychology, technology, environment, business and society. The dataset that we would like to use is the kaggle dataset on 2500 different ted talks . This dataset contains tags on various themes mentioned in each dataset which will make it possible for us to identify our chosen theme groups. By looking at the emotional intensity of each theme group we would like to identify the relationship between the theme groups and the engagement in the viewership. Although Ted talks are also delivered in person we would compare the engagement of the viewerships with the amount of Youtube videos viewed per Ted talk video.  Our initial idea is to observe the sentiment of text (perform sentiment analysis) however if more complexity is required we would consider looking at polarization. 


## Research questions
- How does emotional sentiment (positive, negative, neutral) differ across various theme groups (business, pyschology , society, environment,  business, ) and which emotions ( 5 main emotions) are most dominant in these themes?
- Is there a statistically significant difference between emotional sentiment in Ted Talks and their engagement. Measured specifically by Youtube views, likes and comments?
- To what extent do Ted talk theme groups (education, pyschology , society, environment,  business) differ in polarization and which group produces the most emotionally divided content? 


## Dataset
Kaggle:  https://www.kaggle.com/datasets/rounakbanik/ted-talks
Emobank: https://github.com/julielab/emobank ( further emotion datasets to be explored in Week 1 of project)

For now we have chosen EmoBank as a training/evaluation data set for the Ted Talk dataset. However, we would like to further explore other options within the first week of the project by looking at past research and searching the web (In particular VADER,TextBlob and NRC Lexicon). The EmoBank data set has been chosen as a preliminary dataset as it contains both emotional tags of intented emotions of the writer and the perceived emotions of the readers which we though would be useful for the second and third research question. 

## A tentative list of milestones for the project
**Delegation of tasks for week 1:**

20th April — Week 1 Update

Goal: Everyone is set up, and the data is understood

----------------
| Person | Deliverables |
|------|-------|
| Tianrun | Download Kaggle TED dataset, load into pandas, document all columns and basic stats (row count, null values, transcript lengths) |
| Camellia | Set up Python environment, install all libraries (NLTK, spaCy, VADER, nrclex), confirm everything runs |
| Veronika | Research the use of the sentiment analysis datasets mentioned in the dataset category and based on past research decide on which one to use. Add the reasoning to the report file |
| Elijus | Set up shared GitHub repo, create folder structure, research 2–3 similar text mining projects for inspiration |


Per week deadlines (we create goals per week that we want done by these dates):
----------------
| Date | Goals |
|------|-------|
| 20th April | Setup complete, data explored |
| 27th April | Clean data + theme groups locked |
| 4th May | Full analysis running |
| 11th May | Results interpreted, visuals done |
| 18th May | Report done, presentation rehearsed |
| 22nd May | **Presentation** |

27th April - Update 1 - Cleaning, Preprocessing & Theme Groups Defined

Goal: Clean data and theme groups are locked in
----------------
| Person | Deliverables |
|------|-------|
| Tianrun | Parse tags column, run full tag frequency analysis, propose final theme groups (tags appearing 50+ times), remove duplicates and null transcripts |
| Camellia | Build and test full preprocessing pipeline — tokenisation, stopword removal, lemmatisation — on a sample of 50 talks |
| Veronika | Run VADER and NRC Lexicon on a small sample (one theme group) as a proof of concept, share results with group |
| Elijus | Build exploratory visualisations — top 20 tags bar chart, talk distribution across theme groups, transcript length distribution |
## Documentation

*For now empty*
