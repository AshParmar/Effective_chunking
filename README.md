# Effective Chunking Strategies for Better Text Splitting in RAG

This repository demonstrates various text chunking techniques for Retrieval-Augmented Generation (RAG) systems, comparing traditional methods with modern agentic approaches.

## 📚 Overview

Text chunking is a critical component in RAG systems that determines how well your AI can understand and retrieve relevant information. This project explores different chunking strategies from basic character-based splitting to intelligent agentic chunking.

## 🗂️ Repository Structure

```
Chunking_In_RAG/
├── README.md                           # This file
├── content.txt                         # Sample text for chunking experiments
├── chunking_old_techniques.ipynb       # Traditional chunking methods
├── chunking_EFFICIENT.IPYNB            # Modern agentic chunking approach
└── .env                               # Environment variables (create this)
```

## 📖 Notebooks Description

### 1. `chunking_old_techniques.ipynb` - Traditional Chunking Methods
Explores conventional text splitting approaches including:
- **Character Text Splitter**: Basic fixed-size chunking
- **Recursive Character Text Splitter**: Smart splitting with separators
- **Markdown Text Splitter**: Structure-aware markdown chunking
- **Python Code Text Splitter**: Language-specific code chunking
- **Semantic Chunker**: Embedding-based similarity chunking

### 2. `chunking_EFFICIENT.IPYNB` - Agentic Chunking (Recommended)
Implements an intelligent, AI-driven chunking system that:
- **Dynamically groups related content** using LLM reasoning
- **Generates meaningful chunk summaries and titles**
- **Adapts to content context** rather than fixed rules
- **Uses free Groq API** for cost-effective processing

## 🚀 Getting Started

### Prerequisites
- Python 3.8+
- Jupyter Notebook or VS Code with notebook support

### Installation

1. **Clone or download this repository**
2. **Install required packages:**
   ```bash
   pip install langchain-groq python-dotenv rich pydantic langchain-core langchain
   ```

### Setup for Agentic Chunking

1. **Get a free Groq API key:**
   - Visit [Groq Console](https://console.groq.com/)
   - Sign up for a free account
   - Create an API key from the dashboard

2. **Set up environment variables:**
   Create a `.env` file in the project root:
   ```env
   GROQ_API_KEY=your_groq_api_key_here
   ```

3. **Run the notebooks:**
   - Start with `chunking_old_techniques.ipynb` to understand traditional methods
   - Then explore `chunking_EFFICIENT.IPYNB` for the agentic approach

## 🔧 Usage Examples

### Traditional Chunking
```python
from langchain.text_splitter import RecursiveCharacterTextSplitter

text_splitter = RecursiveCharacterTextSplitter(
    chunk_size=1000,
    chunk_overlap=200
)
chunks = text_splitter.split_text(your_text)
```

### Agentic Chunking
```python
from chunking_EFFICIENT import AgenticChunker

ac = AgenticChunker()
propositions = [
    "Your first statement or fact",
    "Another related piece of information",
    "A different topic entirely"
]

ac.add_propositions(propositions)
ac.pretty_print_chunks()
```

## 📊 Chunking Methods Comparison

| Method | Pros | Cons | Best For |
|--------|------|------|----------|
| **Character Splitter** | Simple, fast | No context awareness | Basic text processing |
| **Recursive Splitter** | Respects structure | Fixed rules | General documents |
| **Semantic Chunker** | Content-based | Requires embeddings | Similar content grouping |
| **Agentic Chunker** | Intelligent, adaptive | Requires API calls | Complex, varied content |

## 🎯 Key Features of Agentic Chunking

- **Intelligent Grouping**: Uses LLM to determine if content belongs together
- **Dynamic Summaries**: Generates and updates chunk summaries as content grows
- **Contextual Titles**: Creates meaningful titles for each chunk
- **Adaptive Structure**: No fixed size limits - chunks grow based on semantic similarity
- **Cost-Effective**: Uses free Groq API instead of expensive OpenAI calls

## 🔍 Example Results

### Traditional Chunking Output:
```
Chunk 1: "The month is October. The year is 2023. One of the most..."
Chunk 2: "...important things that I didn't understand about the world..."
```

### Agentic Chunking Output:
```
Chunk #0
Chunk ID: a7b3c
Summary: This chunk contains temporal information about dates and times.
Propositions:
    - The month is October.
    - The year is 2023.

Chunk #1  
Chunk ID: d4e9f
Summary: This chunk discusses performance returns and learning concepts.
Propositions:
    - One of the most important things that I didn't understand...
    - Teachers and coaches implicitly told us that returns were linear.
```

## 🛠️ Troubleshooting

### Common Issues:

1. **API Key Errors**: Ensure your `.env` file is in the project root and contains the correct Groq API key
2. **Import Errors**: Run the installation cell to install all required packages
3. **Rate Limits**: Groq has generous free limits, but if exceeded, wait or upgrade your plan

### For Traditional Methods:
- **Memory Issues**: Reduce chunk size for large documents
- **Poor Chunking**: Adjust chunk_overlap and separators

## 🤝 Contributing

Feel free to experiment with different chunking strategies and share your findings! Some ideas for enhancement:
- Hybrid chunking approaches
- Domain-specific chunking rules
- Performance benchmarking
- Integration with different LLM providers

## 📝 License

This project is for educational purposes. Feel free to use and modify for your learning and projects.

## 🔗 Useful Resources

- [LangChain Text Splitters Documentation](https://python.langchain.com/docs/modules/data_connection/document_transformers/)
- [Groq API Documentation](https://console.groq.com/docs)
- [RAG Best Practices](https://python.langchain.com/docs/use_cases/question_answering/)
- [Chunking Strategies Guide](https://www.pinecone.io/learn/chunking-strategies/)

## 📞 Support

If you encounter issues or have questions:
1. Check the troubleshooting section above
2. Review the notebook comments and documentation
3. Ensure all dependencies are properly installed
4. Verify your API keys are correctly configured

---

**Happy Chunking! 🎯**

> *Remember: The best chunking strategy depends on your specific use case, data type, and downstream application needs.*