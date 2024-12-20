# Optimizing Inventory and Sales Strategy for a Footwear Retailer

This project leverages advanced Natural Language Processing (NLP) techniques to analyze customer reviews, enabling shoe store owners to make data-driven decisions regarding inventory management, pricing strategies, and product development. By combining sentiment analysis, topic modeling, and trend detection, this project uncovers actionable insights that optimize business outcomes.

## Features

- **Sentiment Analysis**: Comprehensive analysis using VADER and RoBERTa to detect nuanced customer sentiments.
- **Trend Analysis**: Insights into yearly brand popularity and customer preferences.
- **Brand Insights**: Evaluation of brands based on comfort, durability, activity-specific suitability, and customer feedback.
- **Inventory Recommendations**: Strategies to reduce unsold stock and align inventory with customer demand.
- **Argument Mining**: Extracting key reasons for sentiment to provide actionable feedback for product improvement.

## Problem Statement

Shoe store owners encounter challenges such as:

- Managing outdated stock.
- Identifying popular and stagnant brands/models.
- Understanding brand suitability for specific activities (e.g., running, walking).
- Determining price elasticity for different brands.

This project addresses these challenges by combining sentiment and trend analysis with topic modeling to uncover hidden insights within customer reviews.

## Dataset

We utilized the [Amazon UK Shoes Product Reviews Dataset](https://data.world/crawlfeeds/amazon-uk-shoes-product-reviews-dataset), comprising:

- **Size**: 6,823 rows, 11 columns
- **Key Columns**:
  - `review_text`, `review_rating`, `verified_purchase`, `brand`, `review_date`, etc.

## Methodology

### Data Preparation

- Retained only English reviews using the `langdetect` library.
- Extracted brand names from product names for focused analysis.
- Removed irrelevant columns and rows for a streamlined dataset.
- Included only verified purchase reviews to ensure reliability.
- Normalized review dates and extracted yearly trends.

### Sentiment Analysis

- **VADER**:
  - Rule-based sentiment analysis for initial polarity detection.
  - Outputs polarity scores: Positive, Negative, Neutral, Compound.

- **RoBERTa**:
  - Transformer-based deep learning model for context-aware sentiment detection.
  - Provides higher accuracy for nuanced sentiments, outperforming VADER in precision and recall.

- **Hybrid Sentiment Analysis**:
  - Combined VADER and RoBERTa for granular sentiment classification.
  - Introduced "slightly positive" and "slightly negative" categories for detailed insights.

### Topic Modeling

- **LDA (Latent Dirichlet Allocation)**:
  - Extracted hidden topics from reviews.
  - Mapped topics to aspects like comfort, style, durability, and activity suitability.

### Argument Mining

- Extracted reasons for sentiment from "because" or "cause" phrases in reviews.
- Performed detailed analysis of slightly positive and slightly negative reviews, identifying factors contributing to these sentiments.
- Used TF-IDF to rank keywords and derive actionable insights from customer feedback.

## Key Results

- **Sentiment Analysis**:
  - RoBERTa outperformed VADER in identifying nuanced sentiments.
  - Hybrid sentiment analysis accurately classified reviews into categories, including "slightly positive" and "slightly negative."

- **Topic Insights**:
  - Identified topics such as Size/Fitting, Durability, and Comfort.
  - Mapped topics to activities (e.g., running, walking) for brand-specific analysis.

- **Argument Mining**:
  - Extracted positive and negative feedback points for detailed insights.
  - Identified root causes of customer dissatisfaction and product praise.

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. Run the Jupyter notebook for interactive analysis:
   ```bash
   jupyter lab Project.ipynb
   ```
2. Use the scripts for batch processing customer reviews:
   ```bash
   python analyze_reviews.py
   ```

## Dependencies

- Python libraries: `pandas`, `numpy`, `nltk`, `spacy`, `scikit-learn`, `transformers`, `torch`, `seaborn`, `matplotlib`, `langdetect`, etc.
- See `requirements.txt` for the full list.

## Future Plans

- Expand argument mining to extract actionable insights from neutral reviews.
- Use clustering and embeddings for more granular topic modeling.
- Integrate recommendations into a dashboard for real-time decision-making.

## License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.

