# 🧠 Cognitive Computing Based Semantic Book Recommendation System Using NLP

A semantic book recommendation system that uses **Natural Language Processing (NLP)** and **sentence embeddings** to understand the meaning of a user's query and recommend books based on semantic similarity.

Unlike traditional keyword-based search, this system can understand related concepts and meanings in a user's query and retrieve relevant books from the dataset.

---

## 📌 Project Overview

The **Cognitive Computing Based Semantic Book Recommendation System Using NLP** is designed to provide intelligent and meaning-based book recommendations.

The system converts book information and user queries into numerical **vector embeddings** using a pre-trained Hugging Face Sentence Transformer model. These embeddings are stored and searched using **ChromaDB**, allowing the system to find books that are semantically similar to the user's query.

The application provides an interactive interface using **Streamlit**.

### Example

A user can enter:

> `books about artificial intelligence and machine learning`

The system analyzes the meaning of the query and returns books that are semantically related to the topic.

---

## 🎯 Objectives

* Build an intelligent semantic book recommendation system.
* Apply NLP techniques to understand user queries.
* Generate text embeddings using a pre-trained transformer model.
* Store and search embeddings using a vector database.
* Recommend books based on semantic similarity.
* Provide a simple and interactive web interface.
* Demonstrate the application of cognitive computing concepts in recommendation systems.

---

## ✨ Key Features

* 🔎 **Semantic Search** – Understands the meaning of a query rather than relying only on exact keywords.
* 🧠 **NLP-Based Recommendations** – Uses sentence embeddings to represent text.
* 🤗 **Hugging Face Embeddings** – Uses `all-MiniLM-L6-v2`, a pre-trained Sentence Transformer model.
* 🗄️ **ChromaDB Vector Database** – Stores and searches vector embeddings.
* 📚 **Book Recommendations** – Retrieves relevant books from the book dataset.
* 🖥️ **Streamlit Interface** – Provides an easy-to-use interactive application.
* 💻 **Free Local AI Model** – Does not require a paid OpenAI API for generating embeddings.

---

## 🏗️ System Architecture

```text
                    User Query
                        │
                        ▼
              ┌──────────────────┐
              │   Streamlit UI   │
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │   NLP / Text     │
              │   Processing     │
              └────────┬─────────┘
                       │
                       ▼
          ┌──────────────────────────┐
          │ Sentence Transformer     │
          │ all-MiniLM-L6-v2         │
          └────────────┬─────────────┘
                       │
                       ▼
                Query Embedding
                       │
                       ▼
              ┌──────────────────┐
              │    ChromaDB      │
              │ Vector Database  │
              └────────┬─────────┘
                       │
                       ▼
             Semantic Similarity
                       │
                       ▼
              Relevant Book Results
```

---

## 🧠 How the System Works

### 1. Book Dataset

The system uses a book dataset containing information about books.

The relevant text information is processed and prepared for embedding.

### 2. Text Embedding

The project uses:

**Model:** `sentence-transformers/all-MiniLM-L6-v2`

The model converts text into numerical vectors that represent the semantic meaning of the text.

### 3. Vector Database

The generated embeddings are stored in **ChromaDB**.

This allows the application to efficiently search for books that are semantically similar to a user's query.

### 4. User Query

The user enters a natural-language query through the Streamlit interface.

For example:

```text
books about artificial intelligence and machine learning
```

### 5. Semantic Search

The query is converted into an embedding using the same Sentence Transformer model.

ChromaDB compares the query embedding with stored book embeddings and identifies the most semantically similar results.

### 6. Recommendations

The application displays the most relevant books to the user.

---

## 🛠️ Technologies Used

| Technology                             | Purpose                                         |
| -------------------------------------- | ----------------------------------------------- |
| **Python**                             | Main programming language                       |
| **Natural Language Processing**        | Understanding and representing text             |
| **Hugging Face Sentence Transformers** | Generating text embeddings                      |
| **all-MiniLM-L6-v2**                   | Pre-trained embedding model                     |
| **ChromaDB**                           | Vector database and similarity search           |
| **LangChain**                          | Integration with embeddings and vector database |
| **Streamlit**                          | Interactive web application                     |
| **Pandas**                             | Dataset processing                              |
| **Git & GitHub**                       | Version control and project hosting             |

---

## 📂 Project Structure

```text
cognitive-book-recommender/
│
├── data/
│   ├── books_with_emotions.csv
│   └── ...
│
├── scripts/
│   └── rebuild_chroma.py
│
├── notebooks/
│   └── ...
│
├── streamlit_dashboard.py
├── requirements.txt
├── .gitignore
├── README.md
└── ...
```

> The generated Chroma vector index is created locally when required and is excluded from Git using `.gitignore`.

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/Nabil6786/cognitive-book-recommender.git
```

### 2. Open the project directory

```bash
cd cognitive-book-recommender
```

### 3. Create a virtual environment

```bash
python -m venv venv
```

### 4. Activate the virtual environment

**Windows:**

```bash
venv\Scripts\activate
```

### 5. Install dependencies

```bash
pip install -r requirements.txt
```

---

## 🔨 Build the Vector Index

Before running the application, generate the ChromaDB vector index:

```bash
python scripts/rebuild_chroma.py
```

The script generates embeddings for the book dataset using the Hugging Face Sentence Transformer model and stores them in ChromaDB.

---

## ▶️ Run the Application

Start the Streamlit application:

```bash
streamlit run streamlit_dashboard.py
```

The application will open in your browser.

Usually:

```text
http://localhost:8501
```

---

## 🔍 Example Queries

You can test the application with queries such as:

```text
books about artificial intelligence and machine learning
```

```text
science fiction books about robots
```

```text
books related to technology and computers
```

```text
books about human emotions and relationships
```

The system retrieves books based on **semantic similarity**.

---

## 📊 Dataset

The project uses a book dataset containing information used to generate semantic representations of books.

The dataset is processed using Python and Pandas before generating vector embeddings.

The current vector index contains approximately **5,197 book documents**.

---

## 🧩 Cognitive Computing Concept

This project demonstrates concepts related to **cognitive computing** by allowing a computer system to process natural-language input and retrieve information based on semantic meaning.

The main cognitive computing concepts demonstrated are:

* Natural Language Understanding
* Semantic Representation
* Similarity-Based Retrieval
* Machine Learning Models
* Intelligent Recommendation
* Human-like natural language interaction

---

## 💡 Advantages

* More flexible than simple keyword matching.
* Understands the semantic meaning of queries.
* Uses a pre-trained transformer model.
* Does not require a paid OpenAI API for embeddings.
* Provides an interactive user interface.
* Can be extended to larger datasets.

---

## 🚀 Future Scope

The project can be further improved by adding:

* Personalized recommendations based on user history.
* User login and profiles.
* Book ratings and reviews.
* Hybrid recommendation using collaborative filtering.
* More advanced transformer models.
* Recommendation explanations.
* Book cover images and additional metadata.
* Deployment on a cloud platform with sufficient resources.

---

## 🎓 Academic Project

**Project Title:**
**Cognitive Computing Based Semantic Book Recommendation System Using NLP**

**Student:**
**Mohammad Nabil Bagwan**

**Course:**
B.Tech Data Science

**Institution:**
MGM University / Institute of Information and Communication Technology

---

## 👨‍💻 Author

**Mohammad Nabil Bagwan**

GitHub:
https://github.com/Nabil6786

LinkedIn:
https://www.linkedin.com/in/mohammad-nabil-0086bb330

---

## 📜 License

This project is developed for **academic and educational purposes**.
