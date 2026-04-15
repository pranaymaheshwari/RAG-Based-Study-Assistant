# RAG-Based-Study-Assistant
CourseMate AI is an AI-powered study assistant designed to help students interact with their learning materials more efficiently. Modern students rely on multiple sources of study material such as lecture notes, textbooks, PDFs, and research papers. These documents are often long and difficult to navigate, making it time-consuming to find specific information.
CourseMate AI aims to solve this problem by allowing students to chat with their study materials. Instead of manually searching through pages of content, students can simply ask questions and receive accurate answers extracted directly from their documents.
By leveraging Retrieval-Augmented Generation (RAG), CourseMate AI combines document retrieval with large language models to provide context-aware explanations, summaries, and answers from the student's own study resources.

# 🛠️ Setup & Installation

### 1. Clone the repository
Clone or download this repository to your local machine

### 2. Install dependencies
Install all the libraries mentioned in the requirements.txt file.
```bash
pip install -r requirements.txt
```

### 3. Configure environment variables
Create a `.env` file in the root folder:
```
GROQ_API_KEY=your_groq_api_key_here
```
> Get your free API key at https://console.groq.com

### 4. Run the backend
```bash
python app.py
```
Server starts at `http://localhost:8501`

# Development Plan
#### Step 1 - User uploads study material
Students upload learning resources such as:
- PDFs
- Lecture notes
- Textbooks
- Research papers

#### Step 2 - Document Loading
The system loads documents using document loaders.
The goal is to convert raw files into document objects that can be processed.
You may clean the document as well.

#### Step 3 - Text Splitting (Chunking)
Documents are usually too large for LLM context windows. So we split them into smaller chunks.
Chunking improves retrieval accuracy.

#### Step 4 - Embedding Generation
Each chunk is converted into a vector embedding. Embedding models transform text into numerical vectors.
E.g.: "Gradient Descent Optimization" -> [0.23, -0.81, 0.44, ...]
These vectors represent semantic meaning.

#### Step 5 - Vector Database Storage
All embeddings are stored inside a vector database.The vector database stores:
- Embeddings
- Original text chunks
- Metadata

#### Step 6 - User Asks a Question
Now the student interacts with the system.

#### Step 7 - Query Embedding
The question is also converted into an embedding.

#### Step 8 - Similarity Search
The vector database performs semantic similarity search.
We need to find chunks that are most relevant to the question.

#### Step 9 - Retriever Component
The retriever selects the top-k relevant chunks.
These chunks form the context.

#### Step 10 - LLM answers
Based on the context the LLM answers.

# Architecture
![image alt](https://github.com/pranaymaheshwari/RAG-Based-Study-Assistant/blob/4340bb78de5508d65a770358c3223dde74820bf4/Screenshot%202026-04-15%20085903.png)
![image alt](https://github.com/pranaymaheshwari/RAG-Based-Study-Assistant/blob/9de1f23c13712020161fd5d5cb1c8e4fb6344129/Screenshot%202026-04-15%20085929.png)

# Demo
Here is a demo video showing the working of the study assistant.
https://github.com/user-attachments/assets/156d8fea-71d2-43fc-a443-21877677d622
