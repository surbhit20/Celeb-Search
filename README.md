# 🎭 LangChain Learning Project

A comprehensive LangChain learning repository featuring multiple applications and tutorials that demonstrate various LangChain capabilities including prompt engineering, PDF querying, and celebrity search functionality.

## ✨ Project Components

### 1. 🎭 Celebrity Search Application (`main.py`)
- **Celebrity Information Search**: Get comprehensive information about any celebrity
- **Sequential Chain Processing**: Uses LangChain's SequentialChain to process information in multiple steps
- **Memory Management**: Implements ConversationBufferMemory to maintain context across chains
- **Historical Context**: Provides major world events that occurred around the celebrity's birth year
- **Interactive UI**: Clean and intuitive Streamlit interface with expandable sections
- **Real-time Processing**: Instant results with verbose logging for transparency

### 2. 📚 Prompt Engineering Tutorial (`PromptEngineering.ipynb`)
- **Financial Advisor Prompt**: Learn to create specialized prompts for financial advice
- **Language Translation**: Implement multi-language translation using LangChain
- **Template Management**: Master PromptTemplate usage and variable handling
- **Chain Creation**: Build and execute LLM chains for various use cases

### 3. 📄 PDF Query System (`QueryPDF.ipynb`)
- **PDF Processing**: Extract and process text from PDF documents
- **Vector Embeddings**: Use OpenAI embeddings for semantic search
- **FAISS Integration**: Implement vector similarity search for document retrieval
- **Text Splitting**: Efficiently split large documents for processing

## 🏗️ Architecture

### Celebrity Search Application
The Streamlit application uses a sophisticated chain-based architecture:

1. **First Chain**: Generates a detailed description of the celebrity
2. **Second Chain**: Determines the celebrity's birth date
3. **Third Chain**: Finds 5 major world events that occurred around their birth year

Each chain maintains its own memory buffer to preserve context and enable more accurate responses.

### Prompt Engineering Tutorial
Demonstrates fundamental LangChain concepts:
- **Prompt Templates**: Reusable prompt structures with variable substitution
- **LLM Chains**: Connecting prompts to language models
- **Model Configuration**: Temperature and model selection

### PDF Query System
Implements document processing pipeline:
- **Document Loading**: PDF text extraction using PyPDF2
- **Text Splitting**: Character-based text segmentation
- **Embedding Generation**: OpenAI embeddings for semantic search
- **Vector Storage**: FAISS for efficient similarity search

## 🚀 Quick Start

### Prerequisites

- Python 3.9 or higher
- OpenAI API key
- Virtual environment (recommended)

### Installation

1. **Clone or download the project**
   ```bash
   cd /Users/surbhit/Desktop/LangChain
   ```

2. **Create and activate the virtual environment**
   ```bash
   python -m venv lcenv
   source lcenv/bin/activate  # On Windows: lcenv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up your OpenAI API key**
   - Edit `constants.py` and replace the placeholder with your actual OpenAI API key
   - Or set the `OPENAI_API_KEY` environment variable

5. **Run the application**
   ```bash
   streamlit run main.py
   ```

6. **Open your browser**
   - The app will automatically open at `http://localhost:8501`
   - If it doesn't open automatically, navigate to the URL shown in the terminal

## 📋 Usage

### Celebrity Search Application
1. **Enter a celebrity name** in the text input field
2. **Click Enter** or wait for the processing to complete
3. **View the results** which include:
   - Detailed celebrity information
   - Birth date information
   - Major world events from their birth year
4. **Explore memory buffers** using the expandable sections to see the conversation history

### Prompt Engineering Tutorial
1. **Open `PromptEngineering.ipynb`** in Jupyter Notebook
2. **Run the cells sequentially** to understand:
   - How to create prompt templates
   - Building LLM chains
   - Financial advisor prompt example
   - Language translation implementation
3. **Experiment with different prompts** and parameters

### PDF Query System
1. **Open `QueryPDF.ipynb`** in Jupyter Notebook
2. **Place your PDF file** in the project directory
3. **Update the PDF filename** in the notebook
4. **Run the cells** to:
   - Extract text from PDF
   - Create embeddings and vector store
   - Query the document with natural language

## 🛠️ Technical Details

### Dependencies

#### Core LangChain
- **langchain**: Core LangChain framework for building LLM applications
- **langchain-openai**: OpenAI integration for LangChain
- **langchain-core**: Core LangChain components (messages, prompts)
- **langchain-community**: Community integrations and tools

#### OpenAI & AI
- **openai**: Official OpenAI Python client
- **tiktoken**: Token counting for OpenAI models

#### Web & UI
- **streamlit**: Web application framework

#### PDF Processing
- **PyPDF2**: PDF text extraction and manipulation

#### Vector Search
- **faiss-cpu**: Facebook AI Similarity Search for vector operations

### Key Components

#### LangChain Core
- **ChatOpenAI**: OpenAI GPT model integration
- **PromptTemplate**: Template-based prompt generation
- **LLMChain**: Individual processing chains
- **SequentialChain**: Orchestrates multiple chains in sequence
- **ConversationBufferMemory**: Maintains conversation context

#### PDF Processing
- **PdfReader**: PDF document text extraction
- **CharacterTextSplitter**: Text segmentation for processing
- **OpenAIEmbeddings**: Vector embeddings generation
- **FAISS**: Vector similarity search and storage

### Model Configuration

- **Model**: GPT-5 (configurable in the code)
- **Temperature**: 0.8 (for creative and varied responses)
- **Verbose**: Enabled for detailed logging

## 🔧 Configuration

### Changing the Model

To use a different OpenAI model, modify line 19 in `main.py`:

```python
llm = ChatOpenAI(model="gpt-3.5-turbo", temperature=0.8)  # Change model here
```

### Adjusting Temperature

Modify the `temperature` parameter to control response creativity:

```python
llm = ChatOpenAI(model="gpt-5", temperature=0.1)  # More focused responses
llm = ChatOpenAI(model="gpt-5", temperature=1.0)  # More creative responses
```

### Customizing Prompts

You can modify the prompt templates in `main.py` to change the type of information retrieved:

```python
first_input_prompt = PromptTemplate(
    input_variables=['name'],
    template="Provide a brief biography of {name}"  # Customize this
)
```

## 📁 Project Structure

```
LangChain/
├── main.py                    # Celebrity search Streamlit application
├── constants.py               # API key configuration
├── requirements.txt           # Python dependencies
├── PromptEngineering.ipynb    # Prompt engineering tutorial notebook
├── QueryPDF.ipynb            # PDF query system tutorial notebook
├── lcenv/                    # Virtual environment (created after setup)
└── README.md                 # This file
```

## 🐛 Troubleshooting

### Common Issues

1. **ModuleNotFoundError**: Ensure you're using the lcenv virtual environment
   ```bash
   source lcenv/bin/activate
   ```

2. **OpenAI API Error**: Check your API key in `constants.py` and ensure you have sufficient credits

3. **Model Not Found**: GPT-5 might not be available. Try changing to `gpt-3.5-turbo` or `gpt-4`

4. **Memory Issues**: The application uses conversation memory which persists during the session

### Getting Help

- Check the Streamlit logs in the terminal for detailed error messages
- Ensure all dependencies are installed correctly
- Verify your OpenAI API key is valid and has sufficient credits

## 🔒 Security Notes

- **API Key**: Never commit your actual OpenAI API key to version control
- **Environment Variables**: Consider using environment variables for production deployments
- **Rate Limiting**: Be aware of OpenAI's rate limits and usage costs

## 📚 Learning Resources

### Jupyter Notebooks
- **`PromptEngineering.ipynb`**: Learn the fundamentals of prompt engineering with LangChain
- **`QueryPDF.ipynb`**: Master document processing and vector search techniques

### Key Learning Outcomes
- Understanding LangChain's core components
- Building effective prompt templates
- Implementing memory management in chains
- Processing and querying PDF documents
- Creating vector embeddings and similarity search
- Building interactive web applications with Streamlit

## 🚀 Future Enhancements

### Celebrity Search App
- Add support for multiple celebrities comparison
- Implement image search and display
- Add more detailed historical context
- Include social media presence analysis
- Add export functionality for results

### PDF Query System
- Support for multiple document formats (DOCX, TXT)
- Advanced text preprocessing and cleaning
- Document summarization capabilities
- Multi-language document support
- Interactive query interface

### General Improvements
- Add comprehensive error handling
- Implement logging and monitoring
- Create Docker containerization
- Add unit tests and CI/CD pipeline

## 📄 License

This project is for educational and personal use. Please ensure you comply with OpenAI's usage policies and terms of service.

## 🤝 Contributing

Feel free to fork this project and submit pull requests for improvements or additional features.

---

**Happy Celebrity Searching! 🎭✨**
