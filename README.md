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
My data can be found [here](https://mengtingwan.github.io/data/goodreads.html). It was scraped in 2017 by researches Wan and McAuley. 

I use 4 datasets from them. 
1. The dataset 'meta_gr.csv' contains over 2.3 million rows. Each is an individual book, and it has columns with metadata such as isbn, description, links, authors, etc.
2. The dataset 'goodreads_book_genres_initial.json' contains a list of the genres assigned to each book
3. The dataset 'goodreads_book_authors.json' contains a list of all the author names assigned to each book
4. The dataset 'goodreads_reviews_spoiler.json.gz' contains over 1.3 million individual rows. Each row is one user's text review and rating out of 5 for one specific book

## Data Preparation
From my four datasets I was able to clean 3 datasets of interest for my two recommendation systems
1. First I used dataset (1) 

## Collaborative Filtering

## Content-Based
A content-based recommendation system uses various features of the products to calculate similarity scores that can be used to return the top most similar products to an inputted product. In this case, a user will be prompted to enter a book title and how many recommendations they would like, then my recommender system will return that number of similar books as recommendations. 

In my model the following features were used:
1. Concatenated text data consisting of the summary of a book and all of the text reviews of said book. I NLP processed that text data by lemmatizing it using WordNetLemmatizer (bringing the words down to their semantic stems, so that words like charged and charging become charg), removing stop words (non-semantic words), grabbing only words that are 3+ letters long, and tokenizing using RegExpTokenizer. Text data is invaluable in providing detail about a book: for example, if many users mention the word 'horse' in their reviews, we know that that book has something to do with animals. Then, the recommender system might find other books that mention 'horse'.

   This text data was then vectorized using TfidfVectorizer. This type of vectorizer is very powerful for content-based classification because adds importance weight to certain tokens using a tf-idf score. The higher the tf-idf score, the more important that word is in that document compared to how important it is in all the documents.
   
3. The book's average rating out of 5. Some users may be interested only in what others consider high-quality writing. 
4. The total count of ratings - i.e., how many users had rated that book. This feature was essentially a proxy for book popularity. More ratings = a more read book. Obviously, some users may prefer to read/be recommended more mainstream books, and some may prefer indie books.
5. The number of pages that that book had. Presumably, some users prefer longer vs. shorter books
6. The genre of the books were one-hot encoded out. 10 different genres were found.


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

