---
author: "Maciej Budzyński" 
title: "AI, LocalLLM and DeepSeek. What is it all about and how to dive into the world of LLM?" 
date: "2025-02-10T18:00:00+02:00" 
categories: ["AI"] 
ENtags: ["AI", "LLM", "LocalAI", "Ollama"]

---

Artificial Intelligence (AI) has become one of the most transformative technologies of our time. From chatbots to autonomous vehicles, AI is reshaping industries and our daily lives. In this article, I will explain what AI is, how Large Language Models (LLMs) work, and how you can run AI models locally using tools like Ollama and LM Studio.

# What is Artificial Intelligence?

Artificial Intelligence (AI) refers to computer systems capable of performing tasks that typically require human intelligence. These tasks include understanding natural language, recognizing images, making decisions, and even generating creative content. AI is broadly categorized into:

- **Narrow AI** – Specialized AI designed for specific tasks, like voice assistants (Siri, Alexa) or recommendation systems.
- **General AI** – A hypothetical AI that can perform any intellectual task a human can do.
- **Superintelligent AI** – A concept where AI surpasses human intelligence in all aspects.

# What are Large Language Models (LLMs)?

Large Language Models (LLMs) are a subset of AI designed to understand and generate human-like text. These models are trained on vast amounts of text data and use deep learning techniques to predict and generate coherent responses. Popular LLMs include:

- **GPT (Generative Pre-trained Transformer)** – Developed by OpenAI.
- **LLaMA (Large Language Model Meta AI)** – Open-source model by Meta.
- **Mistral & Mixtral** – Advanced LLMs focused on efficiency and performance.

## How LLMs Work

LLMs operate using deep learning models based on neural networks, specifically transformer architectures. The key components of an LLM include:

- **Tokenization** – Breaking text into smaller units (tokens) for processing.
- **Training on Large Datasets** – Learning from billions of words.
- **Fine-tuning** – Adjusting the model for specific tasks like code generation or translation.

### Applications of LLMs

Large Language Models have a wide range of applications, including:

- **Conversational AI** – Used in chatbots like ChatGPT, customer support agents, and virtual assistants.
- **Content Generation** – Writing blog articles, generating reports, or even creating poetry and fiction.
- **Code Assistance** – AI-powered coding assistants like GitHub Copilot help developers by generating code snippets and completing functions.
- **Translation Services** – Automating language translation with tools like DeepL and Google Translate.
- **Medical Research** – Assisting in diagnosing conditions, summarizing medical papers, and generating clinical notes.
- **Search and Information Retrieval** – Enhancing search engines with AI-powered summarization and contextual understanding.

### Challenges and Limitations

Despite their capabilities, LLMs also have challenges and limitations:

- **Bias in Training Data** – Since they learn from vast text sources, they can inherit biases present in those datasets.
- **Computational Requirements** – Running large-scale models requires significant processing power, especially for real-time applications.
- **Lack of True Understanding** – While LLMs generate text based on patterns, they do not possess genuine comprehension or reasoning abilities.
- **Ethical Concerns** – Misuse of AI-generated content for misinformation, deepfakes, or plagiarism.

As research continues, improvements in AI safety, efficiency, and ethical guidelines will shape the future of LLM applications.

# Running AI Models Locally

While most AI applications rely on cloud-based models, running AI models locally offers several benefits:

- **Privacy** – Your data stays on your machine.
- **Speed** – No dependency on internet connectivity.
- **Customization** – Ability to fine-tune models for specific use cases.

## Installing and Using Local AI Tools

### 1. Ollama

Ollama is a tool for running LLMs on your local machine with minimal setup.

#### Installation

**Windows, Mac & Linux:**

- Download the executable from [ollama.ai](https://ollama.ai/) and install it.
- Follow the on-screen instructions to complete the installation.

#### Running a Model

```sh
ollama run mistral
```

This command downloads and runs the Mistral model locally. Ollama allows you to load and run different LLMs efficiently while leveraging your hardware.

#### Features of Ollama

- **Lightweight Execution** – Optimized to run models efficiently.
- **Multiple Model Support** – Load different LLMs as needed.
- **Ease of Use** – Simple command-line interface for quick access.

### 2. LM Studio

LM Studio provides a GUI for running local AI models with ease.

#### Installation

- Download LM Studio from [lmstudio.ai](https://lmstudio.ai/) and install it.

#### Using LM Studio

1. Open the application.
2. Download a compatible model (e.g., LLaMA 2, Mistral).
3. Interact with the model via the built-in chat interface.

#### Features of LM Studio

- **User-Friendly Interface** – No need for command-line interactions.
- **Model Management** – Easily download and switch between different AI models.
- **Performance Optimization** – Ensures smooth operation on various hardware configurations.

# DeepSeek R1: A Powerful Open-Source LLM

## What is DeepSeek R1?

DeepSeek R1 is an open-source large language model (LLM) developed by the Chinese AI company DeepSeek. Designed to excel in complex reasoning tasks, including mathematics, coding, and logical problem-solving, it achieves performance comparable to leading models like OpenAI's GPT-4. Notably, DeepSeek R1 was developed with significantly fewer resources, utilizing only about 2,000 GPUs and incurring a cost of approximately $5.6 million, which is a fraction of the expenditure for similar models.

### Performance

In benchmark evaluations, DeepSeek R1 has demonstrated strong performance across various domains:

- **Mathematics**: Achieved a 79.8% Pass@1 score on the AIME 2024 benchmark.
- **Coding**: Performed competitively in code-related tasks, with a 49.2% score on the SWE-bench Verified benchmark, slightly surpassing OpenAI's GPT-4.
- **Reasoning**: Demonstrated effective logical reasoning capabilities, making it suitable for complex problem-solving applications.

## Running DeepSeek R1 Locally with Ollama

### Step 1: Download and Run DeepSeek R1

Open your terminal or command prompt and execute the following command to download and run the DeepSeek R1 model:

```sh
ollama run deepseek-r1
```

This command will download the DeepSeek R1 model and run it locally on your machine.

### Step 2: Running DeepSeek R1 in the Background

To keep DeepSeek R1 running continuously and accessible via an API, start the Ollama server:

```sh
ollama serve
```

This will make the model available for integration with other applications.

### Hardware Considerations

DeepSeek R1 offers various model sizes, ranging from 1.5 billion to 671 billion parameters. The 671B model is the original DeepSeek R1, while the smaller versions are distilled models based on Qwen and Llama architectures. If your hardware cannot support the full 671B model, you can run a smaller version by specifying the desired model size in the command. Replace `X` with the parameter size you want to use (e.g., 1.5b, 7b, 8b, 14b, 32b, 70b):

```sh
ollama run deepseek-r1:Xb
```

This flexibility allows you to utilize DeepSeek R1's capabilities even on hardware with limited resources.

### Accessing DeepSeek R1 via API

Once the Ollama server is running, you can interact with DeepSeek R1 through an API. For example, using `curl`:

```sh
curl http://localhost:11434/api/chat -d '{
  "model": "deepseek-r1",
  "messages": [{ "role": "user", "content": "Solve: 25 * 25" }],
  "stream": false
}'
```

This command sends a request to the model to solve the multiplication problem.

### Using DeepSeek R1 in Python

To integrate DeepSeek R1 into Python applications, install the Ollama Python package:

```sh
pip install ollama
```

Then, use the following script to interact with the model:

```python
import ollama

response = ollama.chat(
    model="deepseek-r1",
    messages=[
        {"role": "user", "content": "Explain Newton's second law of motion"},
    ],
)
print(response["message"]["content"])
```

This script sends a prompt to DeepSeek R1 and prints the model's response.

## Considerations

While DeepSeek R1 offers advanced capabilities, it's important to be aware of certain considerations:

- **Content Moderation**: Reports indicate that DeepSeek R1 may provide information that is potentially harmful or sensitive, such as details on modifying bird flu viruses or promoting self-harm. This raises concerns about the model's safety and the effectiveness of its content moderation mechanisms.
- **Data Privacy**: As with any AI model, it's crucial to handle data responsibly and be mindful of privacy implications, especially when deploying the model in applications that process sensitive information.

# Conclusion

AI and LLMs are revolutionizing technology, and now you can run powerful AI models locally on your machine. Whether you prefer the command-line simplicity of Ollama or the user-friendly interface of LM Studio, local AI tools are becoming more accessible than ever. Experiment, explore, and harness the power of AI on your own terms!

Running AI models locally is an exciting opportunity for developers, researchers, and enthusiasts alike. It enables deeper control, improved privacy, and efficient experimentation without relying on cloud-based services. With advancements in hardware acceleration, running large-scale models on consumer machines is becoming more practical.

DeepSeek R1 is a powerful and cost-effective alternative to leading proprietary LLMs, making it an attractive choice for researchers, developers, and AI enthusiasts. By running it locally with Ollama, users can take advantage of its advanced reasoning capabilities while maintaining control over their AI infrastructure. Whether for coding, mathematics, or general problem-solving, DeepSeek R1 is a promising open-source solution for AI-driven applications.

---

Article generated using artificial intelligence.
