# Goodreads Book Recommendation System

## Overview
This project develops a book recommendation system using the Goodreads dataset. It leverages exploratory data analysis (EDA), data preprocessing, and content-based filtering to recommend books based on user preferences, genres, and review sentiments. The system identifies hidden gems, analyzes user reading patterns, and generates personalized book recommendations using TF-IDF and cosine similarity.

## Features
- **Exploratory Data Analysis (EDA)**: Analyzes book ratings, publication years, page counts, and user review distributions.
- **Data Preprocessing**: Handles missing values by filling `similar_books` with empty lists, `num_pages` and `original_publication_year` with medians, and `description` with "No description." Unnecessary columns like `isbn` and `isbn13` are dropped.
- **Hidden Gems Identification**: Finds high-rated books (average rating ≥ 4.3) with low ratings count (≤ 1000).
- **Personalized Recommendations**: Recommends books based on a user's favorite genres and high-rated books using TF-IDF and cosine similarity.
- **Sentiment Analysis**: Uses TextBlob to calculate sentiment polarity of reviews, identifying positive reviews (sentiment > 0.2).
- **Keyword Extraction**: Extracts top keywords from positive reviews using CountVectorizer to identify book themes.
- **Visualization**: Includes histograms, bar plots, and a word cloud to visualize rating distributions, publication years, page counts, and user-preferred themes/genres.

## Dataset
The project uses the following datasets:
- `goodreads_data_dictionary.csv`: Metadata about the dataset.
- `goodreads_reviews.csv`: User reviews with ratings and text (limited to 10,000 rows for this analysis).
- `goodreads_works.csv`: Book details including titles, authors, ratings, and genres (limited to 10,000 rows).

## Requirements
To run the project, install the required Python libraries:
```bash
pip install pandas numpy matplotlib seaborn sklearn textblob wordcloud
```

## Usage
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/goodreads-recommendation-system.git
   cd goodreads-recommendation-system
   ```

2. **Prepare the Data**:
   - Place `goodreads_data_dictionary.csv`, `goodreads_reviews.csv`, and `goodreads_works.csv` in the project directory.
   - The code limits the dataset to 10,000 rows for performance. Adjust `nrows` in the code if needed.

3. **Run the Analysis**:
   - Open the Python script or Jupyter notebook containing the code.
   - Execute the script to perform EDA, preprocess data, and generate recommendations.
   - Visualizations (e.g., histograms, word clouds) will be displayed, and recommendations will be printed.

4. **Customize Recommendations**:
   - Modify the `favorite_genre` variable (e.g., "Fantasy") to filter books by genre.
   - Adjust `min_rating` and `max_ratings_count` to redefine hidden gems.
   - Update the `user_id` to generate recommendations for a specific user.

## Methodology
- **Data Cleaning**: Missing values are handled by filling with medians or placeholders. Non-critical columns are dropped.
- **EDA**: Visualizes distributions of ratings, publication years, and page counts. Identifies top-rated and most-rated books.
- **Content-Based Filtering**:
  - Combines review texts by book and transforms them into TF-IDF vectors.
  - Computes cosine similarity between books to find similar ones.
  - Builds a user profile from their high-rated books and recommends similar books.
- **Sentiment Analysis**: Uses TextBlob to identify positive reviews and extract top keywords for book themes.
- **Visualization**: Generates plots for rating distributions, publication trends, page counts, and user-preferred genres/themes.

## Example Outputs
- **Top 10 Most Popular Books**: Sorted by `ratings_count`.
- **Hidden Gems**: High-rated books with low ratings count.
- **Personalized Recommendations**: Books matching the user's favorite genre and high-rated books.
- **Word Cloud**: Visualizes top themes from a user's liked books.
- **Genre Bar Plot**: Shows the user's most frequent genres.

## Future Improvements
- Incorporate collaborative filtering for hybrid recommendations.
- Expand the dataset to include more rows for broader coverage.
- Add advanced NLP techniques (e.g., BERT) for better review analysis.
- Implement a web interface for user interaction.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
- Dataset provided by Goodreads.
- Libraries: Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, TextBlob, WordCloud.