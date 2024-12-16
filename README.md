# Chatbot with LangChain and Ollama

This project demonstrates how to build a simple chatbot using LangChain and the Ollama LLM model. The chatbot processes a user query and generates a response using a provided chat history context.

## Features
- Integration with LangChain's core components.
- Uses the `OllamaLLM` model for generating responses.
- Chat history support for dynamic prompts.

## Requirements
Make sure you have the following dependencies installed:

- Python 3.8 or later
- `langchain_ollama`
- `langchain_core`

## Installation

1. Clone this repository or download the script.
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. Set up a Python virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   .\venv\Scripts\activate    # On Windows
   source ./venv/bin/activate  # On macOS/Linux
   ```

3. Install the required Python libraries:
   ```bash
   pip install langchain_ollama langchain_core
   ```

## Usage

1. Modify the script (`main.py`) if needed, such as adding chat history or changing the question.

2. Run the script:
   ```bash
   python main.py
   ```

3. The chatbot will process the provided question and output the response.

## Script Breakdown

- **Template**: Defines the chatbot prompt with placeholders for chat history and the question.
- **Model**: Utilizes the `OllamaLLM` model (`llama3`) for generating responses.
- **Chain**: Combines the prompt and model into a pipeline for processing inputs and generating outputs.

Example snippet from the script:
```python
template = """
Answer the question below.

Here is the chat history:{context}

Question={question}

Answer:
"""

model = OllamaLLM(model='llama3')
prompt = ChatPromptTemplate.from_template(template)
chain = prompt | model

result = chain.invoke({"context":"","question":"hey how are you?"})
print(result)
```

## Example Output
Input:
```bash
Question: hey how are you?
```
Output:
```bash
[Generated response from the model]
```

## Troubleshooting

- **Dependencies not found**:
  Make sure the `langchain_ollama` and `langchain_core` packages are installed in your Python environment.

- **Model issues**:
  Verify that the `llama3` model is supported in your environment.

## Contributing
Feel free to fork this repository, create a new branch, and submit a pull request for improvements or additional features.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

