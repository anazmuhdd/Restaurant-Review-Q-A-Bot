# 🍕 Restaurant Review Q\&A Bot

An AI-powered chatbot that answers questions about a pizza restaurant using real customer reviews. Built using **LangChain**, **Ollama** (LLaMA3 + Embeddings), and **ChromaDB**, the system retrieves relevant reviews and uses a local language model to generate insightful, context-aware responses.

---

## 🚀 Features

* 🤖 Uses **LLaMA3** via **Ollama** to generate answers.
* 🔍 Retrieves top 5 most relevant reviews using **semantic search**.
* 🧠 Combines retrieved content and user query for response generation.
* 📝 Works on real-world restaurant review data.
* 🛠️ Modular structure with `vector.py` for data setup and `main.py` for interaction.

---

## 📆 Tech Stack

| Tool/Library      | Purpose                        |
| ----------------- | ------------------------------ |
| LangChain         | Prompt chaining and pipeline   |
| Ollama LLM        | Local LLaMA3 model inference   |
| Ollama Embeddings | To embed the review documents  |
| Chroma            | Vector store to store/retrieve |
| Pandas            | Data handling (CSV loading)    |

---

## 📁 Project Structure

```
.
├── realistic_restaurant_reviews.csv  # Input dataset
├── vector.py                         # Embeds + stores documents
├── main.py                           # Q&A interface
├── chrome_langchain_db/              # Chroma DB files
```

---

## 🧠 How It Works

1. **Data Embedding**: Restaurant reviews are embedded using `mxbai-embed-large` and stored in Chroma vector database.
2. **User Input**: User asks a question about the restaurant.
3. **Retrieval**: Top 5 relevant reviews are retrieved using semantic similarity.
4. **Prompting**: The reviews and question are passed to the LLaMA3 model.
5. **Response**: A relevant, review-based answer is generated.

---

## 🔪 Example

```
Ask your question: What do people say about the crust?

Response:
Most customers found the crust to be crispy and delicious. A few mentioned it was a bit too chewy.
```

---

## 📊 Dataset

* **CSV**: `realistic_restaurant_reviews.csv`
* **Columns**:

  * `Title`: Short title of the review
  * `Review`: Full review text
  * `Rating`: Rating out of 5
  * `Date`: Review date

---

## 🛠️ Setup & Run

### 1. Install Dependencies

```bash
pip install langchain langchain-core langchain-ollama langchain-chroma chromadb pandas
```

Make sure Ollama is installed and the LLaMA3 and mxbai-embed-large models are available.

### 2. Build Vector Store

```bash
python vector.py
```

### 3. Start Q\&A Bot

```bash
python main.py
```

---

## 📊 Use Cases

* Analyze customer sentiment about food or service.
* Understand frequent complaints or praise.
* Build similar bots for e-commerce reviews, support FAQs, and more.

---

## 📌 Future Ideas

* Integrate OpenAI/Gemini/GPT-4/Anthropic models.
* Turn into a full web dashboard using Streamlit or Flask.
* Add sentiment analysis for each review.

---

## 🧑‍💻 Author

Made with ❤️ using local models and open-source tools. Contributions welcome!
