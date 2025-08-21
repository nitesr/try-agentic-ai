# LangChain Development Environment

This directory contains a complete setup for working with LangChain framework and Jupyter notebooks.

## Environment Setup

### Prerequisites
- Conda installed on your system

### Installation Steps

1. **Navigate to the langchain directory:**
   ```bash
   cd langchain
   ```

2. **Activate the conda environment:**
   ```bash
   conda activate langchain
   ```

3. **Install additional packages (if needed):**
   ```bash
   pip install -r requirements.txt
   ```

## Starting Jupyter Notebook

To start working with Jupyter notebooks:

```bash
# Make sure the environment is activated
conda activate langchain

# Start Jupyter Notebook
jupyter notebook
```

This will open Jupyter Notebook in your browser, typically at `http://localhost:8888`.

## Environment Details

- **Python Version:** 3.11
- **Environment Name:** langchain
- **Location:** `/Users/n0c09jf/miniconda3/envs/langchain`

## Installed Packages

### Core LangChain
- `langchain` - Main LangChain framework
- `langchain-core` - Core functionality
- `langchain-community` - Community integrations
- `langchain-openai` - OpenAI integration
- `langchain-text-splitters` - Text processing utilities

### Jupyter Environment
- `jupyter` - Jupyter notebook interface
- `notebook` - Notebook server
- `ipykernel` - IPython kernel for Jupyter
- `ipython` - Enhanced interactive Python shell

### AI/ML Libraries
- `openai` - OpenAI API client
- `tiktoken` - Tokenization for OpenAI models
- `numpy` - Numerical computing
- `pandas` - Data manipulation (available for installation)
- `matplotlib` - Plotting library (available for installation)

### Utilities
- `python-dotenv` - Environment variable management
- `pydantic` - Data validation
- `SQLAlchemy` - Database toolkit
- `requests` - HTTP library
- `aiohttp` - Async HTTP client

## Getting Started with LangChain

Here's a simple example to get you started in a Jupyter notebook:

```python
from langchain.llms import OpenAI
from langchain.chains import LLMChain
from langchain.prompts import PromptTemplate
import os
from dotenv import load_dotenv

# Load environment variables
load_dotenv()

# Initialize the language model
llm = OpenAI(api_key=os.getenv("OPENAI_API_KEY"))

# Create a prompt template
prompt = PromptTemplate(
    input_variables=["topic"],
    template="Write a brief explanation about {topic}"
)

# Create a chain
chain = LLMChain(llm=llm, prompt=prompt)

# Use the chain
result = chain.run("machine learning")
print(result)
```

## Environment Variables

A `.env` file has been created in this directory for storing your API keys and configuration. You can also use the `environment-template.txt` file as a reference.

**Required Environment Variables:**
```bash
OPENAI_API_KEY=your_openai_api_key_here
```

**Optional Environment Variables:**
```bash
# OpenAI Organization (if applicable)
OPENAI_ORG_ID=your_organization_id_here

# LangSmith Tracing (for debugging and monitoring)
LANGCHAIN_TRACING_V2=true
LANGCHAIN_ENDPOINT=https://api.smith.langchain.com
LANGCHAIN_API_KEY=your_langchain_api_key_here
LANGCHAIN_PROJECT=your_project_name

# Other AI Services
ANTHROPIC_API_KEY=your_anthropic_api_key_here
GOOGLE_API_KEY=your_google_api_key_here
HUGGINGFACE_API_KEY=your_huggingface_api_key_here
```

**Important:** The `.env` file is automatically ignored by git to protect your API keys from being committed to version control.

## Deactivating the Environment

When you're done working:

```bash
conda deactivate
```

## Troubleshooting

If you encounter any issues:

1. **Environment not found**: Make sure conda is properly installed and the environment was created successfully
2. **Import errors**: Ensure all packages are installed by running `pip install -r requirements.txt`
3. **Jupyter not starting**: Try `jupyter lab` instead of `jupyter notebook`

## Next Steps

- Explore LangChain documentation: https://docs.langchain.com/
- Try the example notebooks in the LangChain repository
- Experiment with different LangChain components and chains
