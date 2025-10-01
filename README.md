# PROJECT: Collaborative Movie Recommendation using KNN

## DESCRIPTION:
This project implements an **Item-Based Collaborative Filtering** system to recommend movies based on user ratings. 
It uses K-Nearest Neighbors (KNN) on the MovieLens dataset to find movies similar to a given movie based on past user ratings.

## DATASET COLUMNS:
- **userId**: Unique ID for each user
- **movieId**: Unique ID for each movie
- **rating**: Rating given by a user to a movie
- **title**: Movie title (from movies dataset)
- **genres**: Movie genres (not used in this filtering approach)

## STEPS:
1. Import dataset and inspect columns
2. Transform ratings dataset to a **movie-user matrix**:
   - Movies as rows, users as columns
   - Fill missing ratings with 0
3. Reduce noise by filtering:
   - Keep movies rated by **at least 10 users**
   - Keep users who rated **at least 50 movies**
4. Convert dataset to **CSR (Compressed Sparse Row) matrix** to handle sparsity efficiently
5. Fit a **KNN model** using cosine similarity to find nearest neighbors:
   - `NearestNeighbors(metric='cosine', algorithm='brute')`
6. Define a **recommendation function**:
   - Input: Movie name
   - Output: Top 10 recommended movies based on similarity
7. Test recommendations for sample movies (e.g., "Iron Man", "Memento")

## RESULTS:
- Model successfully recommends movies that are similar in user ratings
- Reduces noise from users or movies with very few ratings
- Efficiently handles sparse datasets using CSR matrix
- Recommendations reflect user behavior and preferences

## KEY LEARNINGS:
- How to implement **Item-Based Collaborative Filtering**
- How to handle **sparse matrices** for large datasets
- Using **KNN with cosine similarity** for recommendations
- Filtering noisy users/movies to improve prediction quality

  ---

## 🔧 Setup & Installation  

1. **Clone the repository**  
```bash
git clone https://github.com/GhadeerZahwe/Collaborative-Recommendation-Movies.git
cd Collaborative-Recommendation-Movies
```
2. **Create & activate a virtual environment**  
```bash
# On Linux/Mac
python -m venv venv
source venv/bin/activate

# On Windows (PowerShell)
python -m venv venv
.\venv\Scripts\activate
```
3. **Install dependencies**  
```bash
pip install -r requirements.txt
```
