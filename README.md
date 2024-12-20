# Optimizing Inventory and Sales Strategy for a Footwear Retailer

This project leverages advanced Natural Language Processing techniques to analyze customer reviews for providing meaningful insights to shoe store owners about inventory management, pricing strategy, and product development. This project uses the combination of sentiment analysis, topic modeling, and trend detection to reveal actionable insights that drive business outcomes.

## Features

Sentiment Analysis: An in-depth evaluation using VADER and RoBERTa to interpret customer emotions with precision, focusing on nuanced feedback across sentiment categories.
Trend Analysis: A systematic review of brand popularity and customer preferences over time, highlighting shifts in consumer behavior.
Brand Insights: A detailed assessment of brands, emphasizing attributes such as comfort, durability, purpose-specific suitability, and overall customer satisfaction.
Inventory Recommendations: Tailored strategies for optimizing inventory, minimizing unsold items, and aligning stock with real-time customer demand patterns.
Argument Mining: Identification and analysis of core customer feedback points to deliver actionable insights for enhancing product features and addressing areas of concern.

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

Filtered reviews to retain only those written in English using the langdetect library.
Isolated brand names from product titles for a targeted and detailed analysis.
Streamlined the dataset by removing unnecessary columns and irrelevant rows.
Focused on verified purchase reviews to ensure the accuracy and reliability of insights.
Standardized review dates and analyzed yearly trends to uncover evolving patterns.

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

Identified sentiment drivers by extracting phrases containing "because" or "cause" from customer reviews.
Conducted an in-depth analysis of mildly positive and mildly negative reviews to uncover factors influencing these sentiments.
Applied TF-IDF to prioritize keywords and extract actionable insights from customer feedback for meaningful improvements.

## Key Results

Sentiment Analysis:
RoBERTa demonstrated superior performance over VADER in capturing subtle and nuanced sentiments.
The hybrid approach effectively categorized reviews, including borderline sentiments like "slightly positive" and "slightly negative."

Topic Insights:
Key topics such as Size/Fitting, Durability, and Comfort were identified from customer reviews.
These topics were linked to specific activities (e.g., running, walking) for a more tailored brand performance evaluation.

Argument Mining:
Extracted core positive and negative feedback to provide actionable insights.
Analyzed underlying causes of customer dissatisfaction and reasons for product appreciation to inform improvements.

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

