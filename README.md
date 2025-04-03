
# 🧠 SalesGPT - Context-Aware AI Sales Assistant with Knowledge Base

This capstone project implements **SalesGPT**, a context-aware AI agent that mimics a human sales development representative (SDR). Built using LangChain, OpenAI, and ChromaDB, SalesGPT dynamically adapts to various stages of a sales conversation and uses a product knowledge base to enhance its relevance and accuracy.

---

## 📖 Project Description

SalesGPT is designed to simulate outbound sales conversations intelligently. It identifies the stage of the sales process and responds appropriately—just like a real human SDR. The agent can:

- Understand and follow different stages of a conversation (introduction, qualification, objection handling, etc.).
- Use a **Product Knowledge Base** to provide factual, grounded information about company offerings.
- Reduce hallucinations and increase the contextual accuracy of its answers.

---

## 🧰 Technologies Used

- Python 3.x
- [LangChain](https://github.com/langchain-ai/langchain)
- OpenAI GPT (via `openai` API)
- ChromaDB (for the vector knowledge base)
- tiktoken, pydantic, prompt templates

---

## 🔧 Setup Instructions

1. **Install required libraries**

```bash
pip install langchain==0.1.4 langchain-openai==0.0.5 langchain-community==0.0.16
pip install chromadb==0.4.22 tiktoken==0.5.2 openai==1.10.0 pydantic==1.10.14
```

2. **Add your OpenAI API key**

Edit the notebook or your environment:
```python
import os
os.environ["OPENAI_API_KEY"] = "your-api-key-here"
```

---

## 🧱 Core Components

### 🔹 StageAnalyzerChain
- Determines which stage of the sales conversation the agent should proceed to.
- Returns a number (1–7) representing stages like Introduction, Qualification, Objection Handling, Close, etc.

### 🔹 SalesConversationChain
- Generates the next utterance in the conversation.
- Uses a custom prompt based on the agent’s role, company values, purpose, and conversation stage.

### 🔹 Product Knowledge Base
- Created using ChromaDB and vector embeddings (OpenAI Embeddings).
- Allows the agent to answer technical/product questions using RetrievalQA.

---

## 🔁 Conversation Loop

1. Agent sends an initial message.
2. User response is appended to the conversation history.
3. StageAnalyzer determines the next stage.
4. SalesConversationChain generates the next AI response.
5. Loop continues until termination condition (e.g., closing the sale).

---

## 💡 Sample Prompt Logic

The model receives rich, contextual input like:

- Salesperson name and role
- Company business and values
- Purpose and type of conversation
- Full conversation history
- Current stage of interaction

---

## 📦 Project Structure

```
├── SalesGPT_Capstone.ipynb
├── data/
│   └── product_docs.txt
├── vectorstore/
│   └── chromadb_index/
└── README.md
```

---

## 🔮 Future Enhancements

- Integrate call transcription APIs for real-time deployment.
- Add support for multilingual conversations.
- Improve stage detection via classification model.
- Deploy as a Streamlit or Flask web application.

---

## 👤 Author

**Yash Vinaychandra Rana**  
Graduate Student, Concordia University  
📧 yashrana240203@gmail.com  
📞 +1-438-836-5297

---

## 📄 License

This project is open-source and available under the MIT License.
