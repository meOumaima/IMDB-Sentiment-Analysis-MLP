CNN Model – Sentiment Analysis:

This model uses a 1D Convolutional Neural Network (CNN) to classify IMDB movie reviews as positive or negative. It improves over the MLP by capturing local patterns and important phrases (n-grams) in text.

Model Architecture:
  -> Embedding Layer: 20,000 vocabulary, 100-dim embeddings
  -> Convolutional Layers: Multiple 1D convolutions with kernel sizes [3, 4, 5]
  -> Filters: 100 filters per kernel size
  -> Max-Pooling: Global max pooling applied to each convolution output
  -> Dropout Layer: 0.5 (to reduce overfitting)
  -> Fully Connected Layer: 1 neuron
  -> Activation: Sigmoid
  -> Loss Function: Binary Cross-Entropy
  -> Optimizer: Adam (learning rate = 0.001)

Techniques Applied:
  -> Text preprocessing (lowercasing, HTML removal, extra space removal)
  -> Tokenization using custom vocabulary (top 20,000 words)
  -> Sequence padding to fixed length (200 tokens)
  -> Feature extraction using convolutional filters (captures local patterns like phrases)
  -> Regularization using Dropout
  -> Hyperparameter tuning:
    . Number of filters
    . Kernel sizes
    . Embedding dimension
    . Learning rate

Analysis:
  -> The CNN model achieved 84.63% test accuracy, outperforming the improved MLP (~77.78%) but slightly lower than LSTM-based models (~88%).
  -> Training accuracy reached 96.79%, indicating some degree of overfitting.
  -> Validation and test accuracy (~84.8%) show reasonable generalization.
  -> The model effectively captures important local patterns (e.g., phrases like "very good", "not bad") using convolution filters.
  -> However, it does not capture long-range dependencies as effectively as LSTM or GRU models.
  -> CNN provides a good trade-off between performance and training speed compared to recurrent models.
  -> Potential improvements include using pretrained embeddings, increasing model depth, or combining CNN with LSTM (hybrid model).
