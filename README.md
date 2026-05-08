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

## Project Structure
The repository is organized to separate raw data, processed data, notebooks, reusable code, outputs, and final reporting materials.

```text
TEXT-MINING-PROJECT-2026/
├── data/
│   ├── raw/           # Original input data
│   ├── external/      # External supporting datasets and 
│   └── processed/     # Cleaned and transformed data ready for analysis or interim files
├── notebooks/
├── src/               # Reusable scripts and helper modules
├── outputs/           # Generated charts, tables, and intermediate outputs
├── results/           # Final results, metrics, and model outputs
├── report/            # Written report, notes, and presentation material
├── result/            # Interim files or finding yet to have been discussed
├── .gitignore         # Makes sure that /processed files arent uploaded
└── README.md
```

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

## Update 1
**27th April - Update 1 - Cleaning, Preprocessing & Theme Groups Defined**

Goal: Clean data and theme groups are locked in

| Person | Deliverables |
|------|-------|
| Tianrun | Parse tags column, run full tag frequency analysis, propose final theme groups (tags appearing 50+ times), remove duplicates and null transcripts |
| Camellia | Build and test full preprocessing pipeline — tokenisation, stopword removal, lemmatisation — on a sample of 50 talks |
| Veronika | Run VADER and NRC Lexicon on a small sample as a proof of concept, share results with group |
| Elijus | Build exploratory visualisations — top 20 tags bar chart, talk distribution across theme groups, transcript length distribution |
## Notes on Progress 
All the notebooks related to the progress can be found in the folder 'notebooks'. 

So far we have been able to create a full set-up, which included exploration of the data and decision on sentiment analysis methodology. These include the use of Roberta, VADER and NRC Lexicon. These tasks were completed in the first week. In the second week we begun cleaning the data and sorting the theme groups, the preprocessing and parsing notebooks can also be found in the 'notebooks' folder. The jupyter notebook running a test run was had some issues with being uploaded which I (Veronika) haven't found a solution for.

Decisions for sentiment analysis: I (Veronika) lookinitially looked at only NRC Lexicon and VADER only however, looking into research and set up of the methodology I found that neither score highly on being able to identify neutral sentences. I therefore found Roberta as an alternative solution. In particular while looking at our research questions. 

RQ1a: Classification of emotional sentiment (positive, negative and neutral) -> roberta base sentiment latest

RQ1b: Classification into main emotion groups: NRC Lexicon (In our research question we wanted the main 5 emotions but since NRC Lexicon has 8 I decided to alter the RQ). Additionaly NRC Lexicon has been used in previous literature to categorise Ted talks in specific sentiments. 

RQ3: VADER for polarization and Roberta 

Originally, we planned for Eljuis to do the exploratory visualizations, but Tianrun had already done them, so insted he went over and cleaned up Tianrun's notebook because it didn’t execute fully. He also updated the README to elaborate on project layout and requirements.

For the preprocessing part, I（camellia） built and tested a full pipeline on a sample of 50 talks. This included tokenisation, stopword removal and lemmatisation using spaCy. The pipeline ran without issues and the output has been saved to results/preprocessed_sample.csv. The notebook can be found in the notebooks folder.

## Update 2
**4th May — Full Analysis Running**

Goal: Sentiment and emotion scores computed for all theme groups
 This week we aimed to run the first full set of sentiment analysis on the whole sample. However, due to various issues that we came across with coding, our wish for this deadline was not reached.

## Notes on Progress 
 Instead at the beginning of the reading week Veronika and Tianrun discussed and decided on an issue that we discovered during the data examination. Namely, that almost all ted talks were assigned more than one theme group. This is an issue and counteracts our research question, so we looked for a solution to fix the overlap. When looking at the initial grouping of the data we saw that the 'society' group was highly overrepresented compared to the other theme groups. 

 We explored the options:
1. Splitting the 'society' theme group to 2-3 themes. (Drawbacks: Analyzing 7 themes might be overextensive)
2. Each talk gets assigned to only one theme. The rarest tag wins. for instance, if a talk is tagged with both business and parenting, it would be categorized under education because parenting is rarer and more specific. (Drawback: loose information but we could use ANOVA later to compensate)
3. Combine the two options
 
Ultimately we chose to combine both options with 6 themes and 2. rule working if a talk is assigned more than one theme. 

Another issue that is currently being fixed is that Camilla accidently preprocessed the 'description' of the talks instead of the actual transcript. This lead to a bit of buffer in Veronika's ability to preform an (initial) sentiment analysis. Instead she preformed a further test on the preprocessed descriptions of the data. 

At this point the transcripts have also been processed (see preprocessed_full.csv), however this has yet to be joined with Tianrun's cleaned and grouped CSV file. 

Elijus had started working on the Introduction and Discussion part of the report. 





