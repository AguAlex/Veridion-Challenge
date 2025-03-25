# Company Classifier Using Sentence Embeddings 🤖

## Description

This project aims to automatically classify companies (from `ml_insurance_challenge.csv`) into a predefined set of labels (from `insurance_taxonomy.csv`) using advanced Natural Language Processing (NLP) techniques. Essentially, the model assigns the **three most relevant labels** to each company. The final result is saved in `company_list_result.csv`.

## Implementation Details 🛠️

### 1. **Parsing the Input Data** 📋
   - The information from each column of every company was combined into a single column to create a textual representation suitable for generating semantic embeddings.

### 2. **Loading the NLP Model** 🧠
   - We used **Sentence-Transformer** with the `all-MiniLM-L6-v2` model, which converts sentences into **numerical embeddings** (vectors) that represent the semantic meaning of the text in a fixed-dimensional space.

### 3. **Generating Embeddings for Companies and Labels** 🧳
   - **Sentence-Transformer** was used to generate embeddings for each company in the dataset, based on the combined textual information.
   - Similarly, embeddings were generated for each label in the taxonomy, allowing us to compare companies and labels in a meaningful way.

### 4. **Calculating Similarity Between Companies and Labels** 📈
   - We used **cosine similarity** to measure the semantic similarity between each company and all labels from the taxonomy.
   - Based on similarity scores, the top **three most relevant labels** were selected for each company.

### 5. **Classification and Exporting Results** 🏷️
   - The most relevant labels were assigned to each company based on similarity scores and stored in a new column in the dataset.
   - The final results were exported to a new CSV file (`company_list_result.csv`), containing each company along with its assigned labels.

