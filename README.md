# GoodReads Recommendation Systems
![ReadMe header](images/readme_header.png)

## Citations
* Mengting Wan, Julian McAuley, "Item Recommendation on Monotonic Behavior Chains", in RecSys'18. [bibtex]
* Mengting Wan, Rishabh Misra, Ndapa Nakashole, Julian McAuley, "Fine-Grained Spoiler Detection from Large-Scale Review Corpora", in ACL'19. [bibtex]
* SEMrush. "Goodreads.com - Overview." SEMrush, https://www.semrush.com/website/goodreads.com/overview/

## Background
![ReadMe header](images/goodreads_traffic.png)
GoodReads is a centralized location for researching almost all books in publication. It contains crucial data such as summaries, ISBN, authors, page number, all versions of that book, etc. Critically, it is also a user-driven site: it aggregates user ratings, and allows users to post written reviews. 

## Research Question
In order to optimize 

## Data Understanding

## Data Preparation

## Modelling

## Results


## Impact


## Next Steps
GoodReads has so many other metrics that could be added to these recommendation systems in order to make them more accurate and informative. 

For example, a popular feature of the site is the ability to add certain titles to custom 'lists' like a "Want to Read" list. Users can add books that they're interested in to a compiled location that keeps track of which books are next on deck. This action has the potential to represent a datapoint of interest in a collaborative filtering recommendation system. Users who have added the same books to their "Want to Read" list would be considered more similar, and thus could be used to recommend each other further books. 

For the content-based recommendation system, the GoodReads site could be scraped for additional information like book format: Audio, eBook, or print. This would add another feature to the model that would focus in on exactly what kinds of books would be most similar to what a user inputs.  

Obviously recommendation systems like this are overall applicable to any site and numerous other types of products. 
  
## Repo Structure
```
├── data
│   ├── cleaned_data.csv
│   ├── COVID-19_Vaccinations_in_the_United_States_Jurisdiction_20240103
│   ├── cc-est2022-agesex-all.csv
│   ├── cc-est2022-all
│   ├── Education.xlsx
│   ├── PovertyEstimates.xlsx
│   ├── COVID-19_Vaccinations_by_County.csv
│   ├── 2020_US_County_Level_Presidential_Results.csv
├── Images
│   ├── readme_header.png
│   ├── goodreads_traffic.png
├── data_prep.ipynb
├── data_cleaning_scratch.ipynb
├── Content_Based.ipynb
├── Collaborative_Filtering.ipynb
├── presentation.pdf
├── .gitignore
├── LICENSE
├── README.md
```

