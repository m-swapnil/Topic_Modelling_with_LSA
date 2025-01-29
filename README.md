# Topic Modelling

## Latent Semantic Analysis (LSA)

This project implements **Latent Semantic Analysis (LSA)** for topic modeling using Python and Gensim. It processes and analyzes large corpora, extracting meaningful topics based on term-document relationships.

---

## Features

- Loads and preprocesses text data from **Reuters SGML files**.
- Cleans and tokenizes text while handling numbers and special characters.
- Uses **Latent Semantic Analysis (LSA)** for topic modeling.
- Computes **coherence scores** to evaluate model performance.
- Visualizes coherence scores to determine the optimal number of topics.

---

## Prerequisites

Ensure you have the following installed:

- **Python 3.7 or above**
- Required libraries:
  ```bash
  pip install gensim beautifulsoup4 matplotlib
  ```

---

## File Structure

```plaintext
.
|-- lsa_topic_modeling.py   # Main script for LSA topic modeling
|-- lsa_data/               # Folder containing Reuters SGML files
```

---

## Workflow

### 1. **Data Loading**
- Parses **Reuters SGML files** using BeautifulSoup.
- Extracts article text from `<body>` tags.

### 2. **Text Preprocessing**
- Cleans text by removing special characters and numbers.
- Tokenizes and normalizes text using `gensim.preprocessing`.

### 3. **Building the LSA Model**
- Creates a **Dictionary** from tokenized documents.
- Converts text into a **bag-of-words (BoW)** representation.
- Uses **LSA (Latent Semantic Indexing - LSI)** to generate topics.

### 4. **Coherence Evaluation**
- Computes **coherence scores** using `gensim.models.CoherenceModel`.
- Iterates over multiple topic numbers to find the optimal one.
- Plots coherence values for visualization.

---

## Configuration

1. **Specify Data Directory**
   - Place your **Reuters SGML** files inside `lsa_data/`.
   - Update the script's path if necessary:
     ```python
     articles = list(load_articles(r"C:\path\to\lsa_data"))
     ```

2. **Adjust Model Parameters**
   - Change the number of topics for LSA:
     ```python
     documents, dictionary, model = run_lsa_process(articles, number_of_topics=5)
     ```
   - Modify the **range** for coherence evaluation:
     ```python
     min_topics, max_topics = 5, 11
     ```

---

## Usage

1. **Run the Script**
   ```bash
   python lsa_topic_modeling.py
   ```

2. **Output**
   - Extracted topics with representative words.
   - Coherence scores for different topic numbers.
   - Coherence plot visualization.

---

## Example Output

```
Topic 0: 'economy', 'inflation', 'growth', 'market', 'policy'
Topic 1: 'government', 'elections', 'law', 'policy', 'rights'
...
```

Coherence Score Plot:

![Coherence Score Plot](coherence_plot.png)

---

## License

This project is licensed under the **MIT License**.

