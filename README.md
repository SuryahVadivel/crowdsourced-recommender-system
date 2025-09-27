# Building a Crowd-Sourced Beer Recommendation System

## Project Overview
This project was developed as part of a group assignment to design and implement the building blocks of a crowdsourced recommender system.  

The goal was to simulate a real-world product recommender that:
1. Accepts user-specified attributes (for example: fruity, crisp, robust).  
2. Uses review data from BeerAdvocate to recommend the top three beers.  
3. Experiments with multiple natural language processing (NLP) and recommendation techniques to compare their effectiveness.  

---

## Data Collection
- **Source**: [BeerAdvocate Top 250 Beers](https://www.beeradvocate.com/beer/top-rated/)  
- **Method**:  
  - Web scraping using Selenium and BeautifulSoup  
  - Collected approximately 5000 reviews across 250 beers  
  - Automated login to scrape reviews beyond the first page  
- **Final Dataset**: `beer_reviews_final.csv` with:
  - `product_name`  
  - `product_review`  
  - `user_rating`  

---

## Methodology

### Data Extraction
- Scraped 5000 reviews.  
- Cleaned and structured into a usable dataset. 

### Attribute-Based Recommender
- Conducted word frequency analysis to identify common attributes (e.g., crisp, malty, hoppy, balanced).  
- Built a bag-of-words model with cosine similarity.  
- Incorporated sentiment analysis to refine results.  
- Produced top-3 recommendations based on user-specified attributes.  

### Word Embeddings (SpaCy)
- Used pre-trained SpaCy medium word vectors.  
- Compared results against the bag-of-words approach.  
- Evaluated whether embeddings improved attribute matching.  

### Custom Word Embeddings
- Trained embeddings from our own beer review corpus using SpaCy and Gensim.  
- Re-ran recommendations using these custom vectors.  
- Compared recommendations with the other approaches.  

### Baseline Comparison
- Ignored attribute filtering and recommended the three highest-rated beers overall.  
- Showed how popularity-based methods fail to capture user-specific needs.  

### Beer-to-Beer Similarity
- For a chosen subset of 10 beers, selected one and identified its most similar competitor.  
- Explained the logic using similarity measures and embeddings.  

---

## Results
- Bag-of-words with sentiment created a strong baseline recommender.  
- Pre-trained word vectors allowed semantic attribute matching and gave better recommendations in some cases.  
- Custom embeddings tailored to the dataset captured beer-specific vocabulary and nuances.  
- Attribute-based recommenders outperformed popularity-based rankings when the user cared about specific features.  
- All approaches are documented and compared in the notebook.  

---

## Project Structure
