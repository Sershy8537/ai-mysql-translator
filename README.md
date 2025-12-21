# ai-mysql-translator
[![PyPI version](https://badge.fury.io/py/ai-mysql-translator.svg)](https://badge.fury.io/py/ai-mysql-translator)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![Downloads](https://static.pepy.tech/badge/ai-mysql-translator)](https://pepy.tech/project/ai-mysql-translator)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue)](https://www.linkedin.com/in/eugene-evstafev-716669181/)

## Overview
A package enables AI systems to securely interact with MySQL databases by translating natural language queries into structured SQL commands. It processes user text input to generate safe, validated database operations, ensuring responses are consistent and free from injection risks. This allows AI assistants to perform data retrieval and manipulation without exposing sensitive database structures or requiring manual query writing.

## Installation
```bash
pip install ai_mysql_translator
```

## Usage
```python
from ai_mysql_translator import ai_mysql_translator
user_input: str
api_key: Optional[str] = None
llm: Optional[BaseChatModel] = None

response = ai_mysql_translator(
    user_input, 
    api_key=api_key, 
    llm=llm 
)
```
You can safely pass your own `llm` instance (based on https://docs.langchain.com/) if you prefer to use a different LLM. For example, to use the OpenAI LLM, you can use:
```python
from langchain_openai import ChatOpenAI
import ai_mysql_translator

llm = ChatOpenAI()
response = ai_mysql_translator(
    user_input,
    llm=llm
)
```
Or to use the Anthropic LLM, you can use:
```python
from langchain_anthropic import ChatAnthropic
import ai_mysql_translator

llm = ChatAnthropic()
response = ai_mysql_translator(
    user_input,
    llm=llm
)
```
Or Google Generative AI LLM, use:
```python
from langchain_google_genai import ChatGoogleGenerativeAI
import ai_mysql_translator

llm = ChatGoogleGenerativeAI()
response = ai_mysql_translator(
    user_input,
    llm=llm
)
```
The package uses the `ChatLLM7` from `langchain_llm7` (https://pypi.org/project/langchain-llm7/) by default.

If you need higher rate limits for `LLM7`, you can pass your own API key via environment variable `LLM7_API_KEY` or directly via `api_key`. You can obtain a free API key by registering at https://token.llm7.io/.

## GitHub
* **Project Repository:** https://github.com/chigwell/ai-mysql-translator
* **Issues:** https://github.com/chigwell/ai-mysql-translator/issues

## Author
* Eugene Evstafev - hi@eugevev.plus