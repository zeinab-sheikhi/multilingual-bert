# How Multilingual is Multilingual BERT?

### Overview

This project investigates the multilingual capabilities of mBERT by analyzing its performance across various languages using consistent Universal POS tagging. By assessing knowledge transfer between languages, we aim to understand how well the model adapts to different linguistic structures.

### Dataset

The primary dataset used in this project is the **Universal Dependencies** (UD) dataset, specifically focusing on the Sequoia treebank. The following languages are included in our analysis:

- **Persian**
- **Arabic**
- **French**
- **English**
- **Japanese**

### Key Concepts

1. **Consistent Annotation**:
   - Using a consistent tagging scheme like Universal POS tags ensures direct comparability between training and evaluation languages. This consistency allows us to measure the model’s ability to transfer learned knowledge from one language to another.

2. **Yield Keyword**:
   - The `yield` keyword is used instead of a simple return to allow the function to return one sentence at a time. This is crucial for handling large CoNLL-U files efficiently, preventing excessive memory usage. We convert the generator output to a list to enable multiple iterations over the dataset.

3. **Label Distribution**:
   - The distribution of labels in the test set of the Sequoia treebank is analyzed to provide insights into the dataset's structure.

4. **Multiword Tokens**:
   - Multiword tokens are identified using the ID column in the Universal Dependencies CoNLL-U file, where they are represented as tuples indicating the start and end IDs of their components.

### Model Performance

The following table shows how a model trained on a specific language performs on other languages in terms of accuracy:

| Trained Language | Tested Language | Accuracy (%) |
|------------------|----------------|--------------|
| Persian          | Arabic         | 78.8         |
| Persian          | French         | 80.0         |
| Arabic           | Persian        | 74.7         |
| Arabic           | French         | 75.2         |
| French           | Persian        | 68.5         |
| French           | Arabic         | 70.0         |
| English          | Persian        | 70.2         |
| English          | Arabic         | 71.1         |
| English          | French         | 76.0         |

### Conclusion

This project demonstrates that a multilingual BERT model can effectively transfer knowledge across languages. By utilizing the Universal Dependencies dataset and consistent annotation practices, we gain valuable insights into the model's capabilities and limitations in handling diverse linguistic structures.

### Installation and Requirements

To run this project, please ensure the following libraries are installed:

```bash
pip install transformers torch pandas matplotlib
