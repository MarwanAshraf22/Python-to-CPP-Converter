
# 🌀 Python-to-C++ Code Converter using LLMs

This project provides a simple interface for converting Python code into optimized C++ code using a Hugging Face language model (`NTQAI/Nxcode-CQ-7B-orpo`). It uses Gradio for the UI and supports CUDA-based inference with 4-bit quantized models via `bitsandbytes`.

## 🧠 Overview

The notebook does the following:

- Loads a pretrained large language model (`NTQAI/Nxcode-CQ-7B-orpo`) using Hugging Face Transformers.
- Converts Python code into C++ through prompts and LLM inference.
- Extracts and displays the generated C++ code.
- Hosts a Gradio UI to allow users to input Python code and receive C++ output.

## 📦 Dependencies

Install the required libraries with:

```bash
pip install openai google huggingface_hub google-genai gradio transformers torch bitsandbytes requests accelerate sentencepiece
```

Ensure you have a CUDA-compatible GPU for best performance.

## 🔐 Required Tokens

Set your API keys in Google Colab using:

```python
from google.colab import userdata

openai_api_key = userdata.get('OPENAI_API_KEY')
google_key = userdata.get('GOOGLE_API_KEY')
hf_token = userdata.get('HF_TOKEN')
```

## 🚀 How It Works

1. A Python sample function (estimating π) is prepared.
2. Prompts are constructed to request the LLM to translate Python to optimized C++ for an M1 Mac.
3. The `generate_code_NxCode` function sends this prompt to the LLM.
4. The LLM's output is decoded, and C++ code is extracted from markdown-style code blocks.
5. A Gradio interface lets users submit their Python code and receive the C++ version.

## 🧪 Sample Code Example

**Python Input:**
```python
def calculate(iterations, param1, param2):
    ...
```

**Expected C++ Output:**
```cpp
#include <iostream>
...
```

## 🌐 Web UI

After running the notebook, it launches a Gradio web interface where you can:

- Paste your Python code
- Click "Convert code"
- View the generated C++ in real-time

## 🛠️ Tech Stack

- Python
- Hugging Face Transformers
- BitsAndBytes for 4-bit quantization
- Gradio (UI)
- Google Colab (for secure key storage)

## 📌 Notes

- Only supports basic Python-to-C++ logic for now.
- Intended for high-performance translation for M1 Mac systems.
- Output C++ is optimized but may require manual review for production use.
