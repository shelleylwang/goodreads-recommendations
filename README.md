# GoodReads Recommendation Systems
![ReadMe header](images/readme_header.png)

## Citations
* Mengting Wan, Julian McAuley, "Item Recommendation on Monotonic Behavior Chains", in RecSys'18. [bibtex]
* Mengting Wan, Rishabh Misra, Ndapa Nakashole, Julian McAuley, "Fine-Grained Spoiler Detection from Large-Scale Review Corpora", in ACL'19. [bibtex]
* SEMrush. "Goodreads.com - Overview." SEMrush, https://www.semrush.com/website/goodreads.com/overview/
* McLean, Kristen. "Book Sales in the U.S. Are Stronger Than Ever." Publishers Weekly, 19 Apr. 2022, https://www.publishersweekly.com/pw/by-topic/industry-news/bookselling/article/89040-book-sales-in-the-u-s-are-stronger-than-ever.html

## Background
GoodReads is a centralized location for users to research books. It contains data such as summaries, ISBN, authors, page number, all versions of that book, etc. Critically, it is also a user-driven site: it aggregates user ratings, and allows users to post written reviews. It plays a crucial role at the nexus of a user's interest in a book and their transition into a purchaser of said book. As such, it is a middle-man in the lifecycle of a potential book sale. As you can see in the image below from SEMrush, a web traffic tracking site,  42% of users go directly to GoodReads, and 40% of them come from a Google search. After using the site, 42% go back to Google, and 22% go to Amazon. That 22% of people are likely going to Amazon to consider buying the book they were looking at. For the users who go back to Google, it is also possible that they plan to make purchases in another way. 

![GoodReads Site Traffic](images/goodreads_traffic.png)

GoodReads' power should also be placed in the context of the book industry as a whole. Publishers Weekly reports that sales of print books were the highest they've ever been since the trade magazine began collecting data in 2004. They note that "led by growth in adult fiction, annual print volume in the U.S. reached 826.6 million units, rising 9% over the prior year. It’s the first time annual sales volume exceeded 800 million units" (McLean). 

## Research Question
GoodReads is a massively popular site, averaging about 230 million views per month AND the book industry is expected to continue its impressive growth (SEMrush) (McLean). As such, GoodReads' ability to provide utility to a user is important to book industry profit. My research question is: can I build an accurate recommendation system for users? I will build two recommendation systems: a content-based recommender which takes in a book title and returns books similar to that book, and a collaborative filteirng recommender which finds users who are similar to each other and recommends what the others haven't read.

## Data Understanding
My data comes from the scraped 

## Data Preparation

## Collaborative Filtering

## Content-Based

## App

## Conclusions


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

