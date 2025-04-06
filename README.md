
# Web Search Agent with Groq and DuckDuckGo

This repository contains a **Web Search Agent** built using the **Agno** framework, **Groq**'s AI model, and **DuckDuckGo**'s search tool. The agent is designed to answer real-time queries by combining Groq’s AI model with live web search results, enabling dynamic responses that pull information from the internet.

## Features
- **Groq AI Model**: Utilizes Groq's powerful language model for intelligent responses.
- **DuckDuckGo Integration**: Uses DuckDuckGo to search the web for up-to-date information.
- **Real-time Responses**: Answers queries based on live data from the web.
- **Structured Markdown Output**: Displays responses in a clean and readable markdown format.
- **Multi-modal Agent**: Explores how to build agents that can combine reasoning and live data retrieval.

## Installation

To use this Web Search Agent, you need Python 3.8+ and the required dependencies.

### 1. Clone the repository:
```bash
git clone https://github.com/yourusername/web-search-agent.git
cd web-search-agent
```

### 2. Create a virtual environment:
```bash
python -m venv .venv
```

### 3. Activate the virtual environment:
- **Windows**:
  ```bash
  .venv\Scripts\activate
  ```
- **Mac/Linux**:
  ```bash
  source .venv/bin/activate
  ```

### 4. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

1. **Set your Groq API Key**:
   Ensure you have a valid **Groq API key** and set it as an environment variable before running the script.

   ```bash
   export GROQ_API_KEY="your_api_key_here"  # For Mac/Linux
   set GROQ_API_KEY="your_api_key_here"  # For Windows
   ```

2. **Run the agent**:
   The agent fetches real-time information from DuckDuckGo and processes it using Groq’s AI model to respond to your queries.

   ```bash
   python python_web_search_agent.py
   ```

3. **Ask a question**:
   Modify the question in the script or pass your own query to fetch live data. Example:
   
   ```python
   agent.print_response("What are the latest trends in AI development for 2025?", stream=True)
   ```

## Example

```python
from agno.agent import Agent
from agno.models.groq import Groq
from agno.tools.duckduckgo import DuckDuckGoTools

import os

# Set the Groq API Key
os.environ["GROQ_API_KEY"] = "your_api_key_here"

# Initialize the agent with Groq and DuckDuckGo
agent = Agent(
    model=Groq(id="llama-3.3-70b-versatile"),
    description="An AI-powered web search agent!",
    tools=[DuckDuckGoTools()],
    show_tool_calls=True,
    markdown=True
)

# Query the agent
agent.print_response("What are the latest trends in AI development for 2025?", stream=True)
```

## Contribution

Feel free to fork this repository and create pull requests to improve it. Issues and suggestions are also welcome!

### To Contribute:
1. Fork the repository
2. Create a new branch (`git checkout -b feature-branch`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature-branch`)
5. Create a new Pull Request

---

### This repository demonstrates how AI agents can integrate live web data for real-time answers, making it an ideal starting point for anyone looking to build intelligent, dynamic, and multi-modal agents.

--- 
