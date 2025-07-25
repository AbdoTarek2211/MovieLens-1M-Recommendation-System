# 🎬 Movie Recommendation System

A comprehensive movie recommendation system implementing multiple recommendation algorithms including collaborative filtering, content-based filtering, matrix factorization, and hybrid approaches.

## 📋 Overview

This project implements a complete movie recommendation system using the MovieLens 1M dataset. The system combines multiple recommendation techniques to provide personalized movie suggestions and handles cold start problems for new users.

## 🚀 Features

- **Multiple Recommendation Approaches:**
  - User-Based Collaborative Filtering
  - Item-Based Collaborative Filtering
  - Content-Based Filtering
  - Matrix Factorization (SVD, SVD++, NMF)
  - Hybrid Recommendations

- **Advanced Evaluation:**
  - RMSE and MAE metrics
  - Precision@K, Recall@K, and NDCG@K
  - Comprehensive model comparison

- **Cold Start Handling:**
  - Popular movie recommendations for new users
  - Content-based suggestions for new movies

- **Production-Ready:**
  - Model persistence and serialization
  - Memory-efficient sparse matrix operations
  - Scalable architecture

## 📊 Dataset

- **Source:** MovieLens 1M Dataset
- **Statistics:**
  - 1,000,209 ratings
  - 6,040 users
  - 3,706 movies
  - Sparsity: 95.53%

## 🛠️ Technology Stack

- **Python 3.x**
- **Libraries:**
  - `pandas`, `numpy` - Data manipulation
  - `scikit-learn` - Machine learning algorithms
  - `surprise` - Recommendation system library
  - `scipy` - Sparse matrix operations
  - `matplotlib`, `seaborn` - Visualization

## 📈 Model Performance

| Model | RMSE | MAE |
|-------|------|-----|
| SVD++ | 0.8630 | 0.6733 |
| SVD | 0.8730 | 0.6849 |
| NMF | 0.9169 | 0.7239 |

**Best Performing Model:** SVD++ with RMSE of 0.8630

### Precision@K Results (SVD++)
- **K=5:** Precision: 0.7939, Recall: 0.4397, NDCG: 0.8065
- **K=10:** Precision: 0.6860, Recall: 0.6378, NDCG: 0.8356
- **K=20:** Precision: 0.5337, Recall: 0.8061, NDCG: 0.8678

## 🏗️ Architecture

```
├── Data Preprocessing
│   ├── Data loading and cleaning
│   ├── User-item matrix construction
│   └── Sparse matrix optimization
│
├── Recommendation Algorithms
│   ├── Collaborative Filtering
│   │   ├── User-based
│   │   └── Item-based
│   ├── Content-Based Filtering
│   └── Matrix Factorization
│       ├── SVD
│       ├── SVD++
│       └── NMF
│
├── Hybrid System
│   ├── Multi-algorithm combination
│   ├── Weighted scoring
│   └── Duplicate handling
│
├── Evaluation Framework
│   ├── Cross-validation
│   ├── Multiple metrics
│   └── Performance comparison
│
└── Model Persistence
    ├── Model serialization
    ├── Matrix storage
    └── Metadata preservation
```

### Usage

#### Basic Recommendations
```python
# User-based collaborative filtering
user_recs = get_user_based_recommendations(user_id=1, n=10)

# Item-based collaborative filtering
item_recs = get_item_based_recommendations(user_id=1, n=10)

# Content-based filtering
content_recs = get_content_recommendations('Toy Story (1995)', n=10)

# Hybrid recommendations
hybrid_recs = hybrid_recommendations(user_id=1, movie_title='Toy Story (1995)', n=10)
```

#### Cold Start Handling
```python
# For new users
popular_movies = handle_cold_start_user(n=10)

# For new movies
similar_movies = handle_cold_start_movie('New Movie Title', n=10)
```

## 📊 Key Functions

- `get_user_based_recommendations(user_id, n=10)` - User-based collaborative filtering
- `get_item_based_recommendations(user_id, n=10)` - Item-based collaborative filtering
- `get_content_recommendations(title, n=10)` - Content-based recommendations
- `hybrid_recommendations(user_id, movie_title=None, n=10)` - Combined approach
- `handle_cold_start_user(n=10)` - Popular movies for new users

## 🔍 Evaluation Metrics

The system uses comprehensive evaluation metrics:

- **RMSE/MAE:** Prediction accuracy
- **Precision@K:** Relevant recommendations in top-K
- **Recall@K:** Coverage of relevant items
- **NDCG@K:** Ranking quality with relevance weights

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 🙏 Acknowledgments

- MovieLens dataset provided by GroupLens Research
- Surprise library for collaborative filtering algorithms
- Scikit-learn for machine learning utilities

---

**Built with ❤️ during internship at Elevvo Pathways**
