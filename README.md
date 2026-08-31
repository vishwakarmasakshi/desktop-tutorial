# 🛒 E-Commerce RAG Assistant

An AI-powered e-commerce customer support chatbot built using **Retrieval-Augmented Generation (RAG)**. The application retrieves relevant information from an FAQ knowledge base using **FAISS** and uses **Google Gemini** to generate concise answers.

## 🚀 Features

* 🤖 AI-powered customer support chatbot
* 🔎 Semantic search using Gemini embeddings
* 🗄️ FAISS vector database for document retrieval
* 🧠 Google Gemini for answer generation
* 📄 FAQ knowledge base with 100+ questions
* 🌐 Interactive Streamlit web interface
* 🔐 API key stored securely using environment variables

## 🏗️ System Architecture

```text
                    FAQ CSV
                       ↓
                create_index.py
                       ↓
              Gemini Embeddings
                       ↓
                FAISS Vector DB
                       ↓
                 rag.py
                       ↓
               Similarity Search
                       ↓
             Relevant FAQ Documents
                       ↓
                Google Gemini
                       ↓
                Generated Answer
                       ↓
                 Streamlit UI
```

## 🛠️ Technologies Used

| Technology    | Purpose                         |
| ------------- | ------------------------------- |
| Python        | Programming language            |
| LangChain     | RAG application framework       |
| Google Gemini | Embeddings and LLM              |
| FAISS         | Vector similarity search        |
| Streamlit     | Web interface                   |
| Pandas        | CSV data processing             |
| python-dotenv | Environment variable management |

## 📁 Project Structure

```text
ecommerce-rag-assistant/
│
├── app.py                  # Streamlit frontend
├── rag.py                  # RAG pipeline and question answering
├── create_index.py         # Creates the FAISS vector database
├── requirements.txt        # Python dependencies
│
├── data/
│   └── faqs.csv            # FAQ knowledge base
│
├── faiss_index/
│   ├── index.faiss         # FAISS vector index
│   └── index.pkl           # Document metadata
│
├── .gitignore
└── README.md
```

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/vishwakarmasakshi/ecommerce-rag-assistant.git
cd ecommerce-rag-assistant
```

### 2. Create a virtual environment

```bash
python3 -m venv .venv
```

Activate the environment:

```bash
source .venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

## 🔑 Configure Gemini API

Create a `.env` file in the project root:

```text
GEMINI_API_KEY=your_api_key_here
```

**Important:** Never upload your `.env` file or API key to GitHub.

## ▶️ Run the Project

### Step 1 — Create the FAISS index

```bash
python create_index.py
```

This reads the FAQ data, generates embeddings, and creates the FAISS vector database.

### Step 2 — Test the RAG pipeline

```bash
python rag.py
```

### Step 3 — Start the Streamlit application

```bash
streamlit run app.py
```

The application will open in your browser.

## 💬 Example

### User Question

```text
Can I return a product?
```

### Retrieved Information

```text
Question: What is the return policy?
Answer: You can return eligible products within 30 days of delivery.
```

### Generated Answer

```text
Yes, you can return eligible products within 30 days of delivery.
```

## 🔍 How RAG Works

The application follows these steps:

1. FAQ data is loaded from a CSV file.
2. Each FAQ is converted into a document.
3. Gemini generates an embedding for each document.
4. Embeddings are stored in FAISS.
5. When the user asks a question, the question is converted into an embedding.
6. FAISS searches for the most relevant FAQ documents.
7. The retrieved documents are provided as context to Gemini.
8. Gemini generates the final answer using the retrieved information.

## 📊 Current Limitations

The current version uses a static FAQ knowledge base.

It does **not yet** connect to a real e-commerce database, so it cannot check real-time:

* Product inventory
* Customer orders
* Order status
* Delivery status
* Return status
* Customer-specific information

## 🔮 Future Improvements

The project can be extended into a complete e-commerce AI customer-support system.

### Database Integration

* Product database
* Customer database
* Order database
* Inventory management
* Order tracking

### AI Features

* Personalized customer support
* Tool calling
* AI agents
* Conversation memory
* Multi-turn conversations
* Product recommendations

### Customer Support

* Return and refund processing
* Order cancellation
* Human-agent escalation
* Support ticket creation

### Production

* User authentication
* API backend
* Logging and monitoring
* RAG evaluation
* Cloud deployment
* Docker containerization

## 🎯 Project Goal

The goal of this project is to demonstrate a practical **Retrieval-Augmented Generation (RAG)** system for e-commerce customer support by combining a knowledge base, semantic retrieval, vector search, and a large language model.

## 👩‍💻 Author

**Sakshi Vishwakarma**

GitHub:
https://github.com/vishwakarmasakshi
