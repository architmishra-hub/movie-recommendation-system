# Movie Recommender System

A content-based movie recommendation engine that suggests similar movies based on genres, keywords, cast, crew, and plot overview. The system uses natural language processing techniques to analyze movie features and find similarities between films.

## Overview

This project builds a movie recommender system using the TMDB 5000 dataset. It creates movie "tags" by combining multiple features and uses cosine similarity to find and recommend movies that are most similar to a user's input movie.

## Features

- Content-Based Filtering: Recommends movies based on content similarity rather than user ratings
- Multi-Feature Analysis: Combines movie overview, genres, keywords, cast, and crew information
- Text Processing: Implements stemming and vectorization for better text analysis
- Similarity Scoring: Uses cosine similarity to find the most relevant movie matches

## Technologies Used

- Python 3.x
- Pandas for data manipulation
- NumPy for numerical operations
- Scikit-learn for CountVectorizer and cosine similarity
- NLTK for PorterStemmer text stemming
- Ast for literal evaluation of JSON parsing

## Dataset

The project uses two TMDB datasets:
- tmdb_5000_movies.csv - Contains movie metadata including budget, genres, homepage, id, keywords
- tmdb_5000_credits.csv - Contains cast and crew information

## Installation

1. Clone the repository:
git clone https://github.com/architmishra-hub/movie-recommender-system.git
cd movie-recommender-system

2. Install required packages:
pip install pandas numpy scikit-learn nltk

3. Download the NLTK data if not already installed:
import nltk
nltk.download('punkt')

## Usage

1. Ensure the dataset files are in the same directory as the notebook
2. Run the Jupyter notebook cells sequentially
3. Use the recommendation function:
recommend("batman begins")

The system will output the top 5 most similar movies.

## How It Works

### Data Preprocessing
1. Merges movies and credits datasets on the title column
2. Selects relevant columns: movie_id, title, overview, genres, keywords, cast, crew
3. Handles missing values by dropping null entries

### Feature Extraction
- Parses JSON-like strings to extract meaningful text
- Extracts top 3 cast members
- Extracts director names from crew data
- Removes spaces from multi-word entities (e.g., "James Cameron" becomes "JamesCameron")

### Text Processing
- Converts overview text into word lists
- Combines all features into a single tags column
- Applies stemming to reduce words to their root form
- Uses CountVectorizer to create feature vectors limited to 5000 features

### Similarity Calculation
- Computes cosine similarity between movie vectors
- Recommends top 5 movies with highest similarity scores

## Example

Input:
recommend("batman begins")

Output:
the dark knight, batman, batman, the dark knight rises, 10th & wolf

## Future Improvements

- Add collaborative filtering based on user ratings
- Implement a web interface using Flask or Streamlit
- Include more sophisticated NLP techniques such as TF-IDF or word embeddings
- Add support for filtering by genre or year
- Optimize for larger datasets

## License

This project is open source and available under the MIT License.

## Acknowledgments

Dataset provided by TMDB (The Movie Database)
Inspired by various content-based recommendation system tutorials

## Contact

For any queries or suggestions, please open an issue in the GitHub repository.
