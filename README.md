# Product Review Summarization

## Introduction
We have developed an application to summarize product reviews from e-commerce websites like Amazon and eBay. This tool provides a concise summary of the overall sentiment from numerous reviews, saving users the effort of reading each one.

## Project Overview
### Why It's Interesting
Our application uses Natural Language Processing (NLP) to summarize and extract key aspects ("tags") from product reviews. These tags reflect crucial factors considered by customers, such as taste, quantity, or texture for food products.

### Technologies Used
- **NLP Methods & Models**: We focused on summarization techniques and context retention.
- **Main Model**: Sequence to Sequence (Seq2Seq) model.
- **Other Techniques**: Clustering (DBSCAN, k-means), pre-trained summarizers (BERT/TextRank).

## Implementation
### Data & Preprocessing
- **Dataset**: Amazon Fine Foods dataset, containing around 500,000 food reviews.
- **Preprocessing Steps**: Text lowercasing, stopwords removal, tokenization, punctuation removal.
- **Dataset Subsetting**: Used for specific models to meet criteria like minimum token count.

### Seq2Seq Model
- **Architecture**: Encoder-decoder setup with LSTM layers, dropout techniques, and attention mechanisms.
- **Encoder**: Processes input text, maintaining context.
- **Decoder**: Generates output text with attention to specific parts of the input.
- **Inference**: Uses `decode_sequence` function for generating coherent summaries.

### End-to-End Flow
1. Gather food product reviews from Amazon.
2. Feed reviews into the Seq2Seq model for initial phrase extraction.
3. Cluster phrases using DBSCAN.
4. Summarize each cluster with the Seq2Seq model.
5. Compare results with actual Amazon review summaries using a sentence similarity metric.

## Results & Evaluation
- **Outputs**: Short summaries and positive/negative tags.
- **Evaluation Method**: Word embedding similarity, comparing outputs to Amazon's summaries and tags.
- **Performance**: Tags scored a mean of 0.681, and sentence summaries scored 0.534 in similarity.

## Future Work
- **Model Improvement**: Train Seq2Seq with sentence-based labels; consider using GPT-4 for label generation.
- **Expanded Dataset**: Include more products and reviews for broader testing.
- **Application Expansion**: Adapt tool for service, restaurant, or location reviews.

## Explanation of each file in this repository and how they contributed to the overall project
- 
