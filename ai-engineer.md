

# 🧠 Complete AI Engineer Master Roadmap

---

## 📌 Pre-requisites (One of These)
> You should have foundational knowledge in at least one:
- **Frontend Development** (HTML, CSS, JavaScript, React, etc.)
- **Backend Development** (Node.js, Python, APIs, databases, etc.)
- **Full-Stack Development** (combination of both)

---

## 1️⃣ Introduction

### What is an AI Engineer?
- A professional who builds applications and products powered by AI/ML models
- Bridges the gap between research/ML teams and end-user products
- Focuses on **integrating** AI capabilities rather than building models from scratch

### AI Engineer vs ML Engineer
| AI Engineer | ML Engineer |
|---|---|
| Builds products using pre-trained models | Builds and trains models from scratch |
| Focuses on integration & application layer | Focuses on model architecture & training |
| Uses APIs, SDKs, and frameworks | Uses TensorFlow, PyTorch, scikit-learn |
| Product-oriented | Research/data-oriented |

### Impact on Product Development
- Accelerating feature development with AI-powered capabilities
- Enabling new product categories (chatbots, copilots, content generation)
- Reducing development time through AI-assisted workflows

### Roles and Responsibilities
- Integrating LLMs and AI models into applications
- Designing prompt strategies and AI workflows
- Building RAG pipelines and AI agent systems
- Ensuring AI safety, ethics, and responsible deployment
- Optimizing cost, latency, and performance of AI features
- Evaluating and selecting appropriate models

### Common Terminology
| Term | Definition |
|---|---|
| **AI vs AGI** | AI = narrow task-specific intelligence; AGI = general human-level intelligence (theoretical) |
| **LLMs** | Large Language Models — massive neural networks trained on text data (GPT-4, Claude, Gemini) |
| **Inference** | Running a trained model to get predictions/outputs |
| **Training** | Process of teaching a model using data |
| **Embeddings** | Dense vector representations of data (text, images) that capture semantic meaning |
| **Vector Databases** | Databases optimized for storing and querying high-dimensional vectors |
| **RAG** | Retrieval-Augmented Generation — enhancing LLM outputs with external knowledge |
| **Prompt Engineering** | Crafting effective instructions/inputs for AI models |
| **AI Agents** | Autonomous systems that use LLMs to reason, plan, and take actions |

---

## 2️⃣ Using Pre-trained Models

### What are Pre-trained Models?
- Models already trained on massive datasets by organizations (OpenAI, Google, Meta, etc.)
- Ready to use out-of-the-box via APIs or local deployment

### Benefits of Pre-trained Models
- ✅ No need for expensive training infrastructure
- ✅ Instant access to state-of-the-art capabilities
- ✅ Reduced development time
- ✅ Continuously improved by providers
- ✅ Fine-tuning available for customization

### Limitations and Considerations
- ⚠️ Cost of API calls at scale
- ⚠️ Data privacy concerns (data sent to third parties)
- ⚠️ Limited control over model behavior
- ⚠️ Knowledge cut-off dates
- ⚠️ Context window limitations
- ⚠️ Vendor lock-in risks
- ⚠️ Potential for hallucinations

### Popular AI Models

#### OpenAI Models
- **GPT-4o** — flagship multimodal model
- **GPT-4o mini** — smaller, faster, cheaper
- **GPT-4 Turbo** — large context window
- **o1 / o1-mini** — reasoning-focused models
- **GPT-3.5 Turbo** — fast and cost-effective
- **DALL·E 3** — image generation
- **Whisper** — speech-to-text
- **TTS** — text-to-speech

**Key Considerations:**
- **Capabilities / Context Length** — different models support different token limits (4K to 128K+)
- **Cut-off Dates / Knowledge** — models have training data cut-off dates and may lack recent information

#### Anthropic's Claude
- Claude 3.5 Sonnet, Claude 3 Opus, Claude 3 Haiku
- Strong at analysis, coding, and instruction following
- Large context windows (up to 200K tokens)
- Constitutional AI approach to safety

#### Google's Gemini
- Gemini Ultra, Gemini Pro, Gemini Nano
- Natively multimodal (text, image, audio, video)
- Integrated with Google ecosystem

#### Cloud AI Platforms
- **Azure AI** — Microsoft's cloud AI services (hosts OpenAI models)
- **AWS SageMaker** — Amazon's ML platform for building, training, deploying

#### Other Model Providers
- **Hugging Face Models** — vast open-source model hub
- **Mistral AI** — efficient open-weight models (Mistral 7B, Mixtral)
- **Cohere** — enterprise-focused LLMs with RAG capabilities
- **Replicate** — run open-source models via API

---

## 3️⃣ OpenAI Platform (Deep Dive)

### OpenAI API
The primary interface for building with OpenAI models.

#### Chat Completions API
```python
from openai import OpenAI

client = OpenAI(api_key="your-key")

response = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Explain quantum computing simply."}
    ],
    temperature=0.7,
    max_tokens=500
)

print(response.choices[0].message.content)
```

#### Writing Prompts
- **System prompts** — set behavior, persona, constraints
- **User prompts** — the actual input/question
- **Assistant messages** — for few-shot examples
- Use clear, specific, and structured instructions
- ➡️ See the **Prompt Engineering Roadmap** for advanced techniques

#### OpenAI Playground
- Web-based interface for testing prompts
- Supports Chat, Assistants, and Completions modes
- Adjust temperature, top_p, frequency/presence penalties
- Great for prototyping before writing code

### Managing Tokens

#### What are Tokens?
- Tokens are chunks of text (~4 characters or ~¾ of a word in English)
- Both input and output consume tokens

#### Maximum Tokens
- Each model has a **context window** (max input + output tokens)
- GPT-4o: 128K context window
- GPT-3.5 Turbo: 4K–16K context window

#### Token Counting
```python
import tiktoken

encoder = tiktoken.encoding_for_model("gpt-4o")
tokens = encoder.encode("Hello, how are you?")
print(f"Token count: {len(tokens)}")  # Token count: 5
```

#### Pricing Considerations
- Charged per token (input tokens + output tokens)
- Different models have different pricing tiers
- Optimize by: reducing prompt length, caching responses, choosing appropriate models
- Monitor usage via OpenAI dashboard

### Fine-tuning
- Customize a model on your specific dataset
- Useful for: consistent style/format, domain-specific knowledge, reducing prompt length
- Process: prepare training data (JSONL) → upload → create fine-tuning job → use custom model
- Currently available for GPT-3.5 Turbo, GPT-4o, GPT-4o mini

```python
# Upload training file
file = client.files.create(file=open("training.jsonl", "rb"), purpose="fine-tune")

# Create fine-tuning job
job = client.fine_tuning.jobs.create(training_file=file.id, model="gpt-4o-mini")
```

---

## 4️⃣ Prompt Engineering Roadmap

> A critical skill for every AI Engineer. Key areas include:

- **Zero-shot prompting** — direct instructions without examples
- **Few-shot prompting** — providing examples in the prompt
- **Chain-of-thought (CoT)** — "think step by step"
- **Role prompting** — assigning personas
- **Structured output** — requesting JSON, XML, markdown
- **Prompt chaining** — breaking complex tasks into sequential prompts
- **ReAct prompting** — Reasoning + Acting framework for agents
- **Self-consistency** — sampling multiple responses and selecting the best
- **Prompt templates** — reusable parameterized prompts

---

## 5️⃣ AI Safety and Ethics

### Understanding AI Safety Issues

#### Prompt Injection Attacks
- Direct injection: user manipulates the model to ignore system instructions
- Indirect injection: malicious content in retrieved documents/data
- Jailbreaking attempts to bypass safety guardrails

#### Bias and Fairness
- Models can reflect biases present in training data
- Outputs may discriminate based on race, gender, religion, etc.
- Important to test for and mitigate bias in applications

#### Security and Privacy Concerns
- Sensitive data leakage through prompts
- Model inversion attacks
- Data retention policies of API providers
- Compliance with GDPR, HIPAA, etc.

### Safety Best Practices

| Practice | Description |
|---|---|
| **Conducting adversarial testing** | Red-team your application to find vulnerabilities |
| **OpenAI Moderation API** | Pre-screen inputs/outputs for harmful content |
| **Adding end-user IDs in prompts** | Track and identify abuse patterns |
| **Robust prompt engineering** | Design prompts resistant to injection |
| **Know your Customers/Usecases** | Understand how your AI will be used and misused |
| **Constraining outputs and inputs** | Set boundaries on acceptable content, validate inputs, limit response scope |

```python
# OpenAI Moderation API example
moderation = client.moderations.create(input="Some user input text")
flagged = moderation.results[0].flagged  # True if content violates policy
```

---

## 6️⃣ Open Source AI

### Open vs Closed Source Models

| Aspect | Open Source | Closed Source |
|---|---|---|
| Access | Free weights/code | API-only access |
| Privacy | Run locally, data stays private | Data sent to provider |
| Customization | Full fine-tuning, modification | Limited fine-tuning |
| Cost | Infrastructure costs only | Per-token API pricing |
| Quality | Catching up rapidly | Generally leading edge |
| Examples | Llama 3, Mistral, Phi-3 | GPT-4o, Claude, Gemini |

### Popular Open Source Models
- **Meta Llama 3 / 3.1** — 8B, 70B, 405B parameters
- **Mistral / Mixtral** — efficient, high-quality
- **Microsoft Phi-3** — small but powerful
- **Google Gemma** — lightweight models
- **Falcon** — by TII
- **Stable Diffusion** — image generation

### Hugging Face

#### Hugging Face Hub
- Largest repository of open-source models (500K+ models)
- Host models, datasets, and Spaces (demo apps)
- Model cards with documentation and benchmarks

#### Hugging Face Tasks
- Text Generation, Text Classification, Question Answering
- Translation, Summarization, Image Classification
- Object Detection, Speech Recognition, and many more

#### Finding Open Source Models
- Browse by task, popularity, trending
- Filter by license, language, library
- Check benchmarks (Open LLM Leaderboard)
- Read model cards and community feedback

### Using Open Source Models

#### Inference SDK (Hugging Face)
```python
from huggingface_hub import InferenceClient

client = InferenceClient(model="meta-llama/Llama-3-8b-instruct")
response = client.text_generation("Explain AI in simple terms")
print(response)
```

#### Transformers.js
- Run ML models directly in the browser or Node.js
- No server needed — fully client-side inference
- Supports many popular architectures

```javascript
import { pipeline } from '@xenova/transformers';

const classifier = await pipeline('sentiment-analysis');
const result = await classifier('I love AI engineering!');
// [{ label: 'POSITIVE', score: 0.9998 }]
```

#### Ollama
A tool for running LLMs locally on your machine.

**Ollama Models:**
- Llama 3, Mistral, Phi-3, Gemma, Code Llama, and more
- Downloaded and managed locally

**Ollama SDK:**
```bash
# Install and run a model
ollama run llama3

# API endpoint
curl http://localhost:11434/api/generate -d '{
  "model": "llama3",
  "prompt": "What is an AI Engineer?"
}'
```

```python
# Python SDK
import ollama

response = ollama.chat(model='llama3', messages=[
    {'role': 'user', 'content': 'What is RAG?'}
])
print(response['message']['content'])
```

---

## 7️⃣ Embeddings & Vector Databases

### What are Embeddings?
- Numerical representations (vectors) of data that capture semantic meaning
- Similar items have vectors that are close together in vector space
- Enable machines to understand "meaning" and "similarity"

### Use Cases for Embeddings

| Use Case | Description |
|---|---|
| **Semantic Search** | Find results by meaning, not just keywords |
| **Recommendation Systems** | Suggest similar content/products |
| **Anomaly Detection** | Identify outliers in data |
| **Data Classification** | Categorize text, images, etc. |
| **Clustering** | Group similar documents together |
| **RAG** | Retrieve relevant context for LLM generation |

### OpenAI Embeddings API

#### OpenAI Embedding Models
- `text-embedding-3-small` — faster, cheaper
- `text-embedding-3-large` — higher quality, more dimensions
- `text-embedding-ada-002` — legacy model

#### Pricing Considerations
- Charged per token embedded
- `text-embedding-3-small` is very cost-effective
- Batch processing available for bulk operations

```python
response = client.embeddings.create(
    input="The quick brown fox jumps over the lazy dog",
    model="text-embedding-3-small"
)

embedding = response.data[0].embedding  # List of floats
print(f"Dimensions: {len(embedding)}")  # 1536
```

### Open-Source Embeddings

#### Sentence Transformers
```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer('all-MiniLM-L6-v2')
embeddings = model.encode([
    "AI engineering is exciting",
    "Machine learning is fascinating"
])
```

#### Models on Hugging Face
- `all-MiniLM-L6-v2` — lightweight, good quality
- `all-mpnet-base-v2` — higher quality
- `bge-large-en-v1.5` — top performance
- `nomic-embed-text-v1.5` — open-source, high quality

### Vector Databases

#### Purpose and Functionality
- Store high-dimensional vectors efficiently
- Perform fast similarity search (nearest neighbor)
- Support filtering and metadata
- Scale to millions/billions of vectors

#### Popular Vector DBs (Pick One)

| Database | Type | Key Features |
|---|---|---|
| **Chroma** | Open-source, embedded | Simple, Python-native, great for prototyping |
| **Pinecone** | Managed cloud service | Fully managed, scalable, easy to use |
| **Weaviate** | Open-source | GraphQL API, hybrid search, multimodal |
| **FAISS** | Library (by Meta) | Extremely fast, in-memory, research-grade |
| **LanceDB** | Open-source, embedded | Serverless, multimodal, built on Lance format |
| **Qdrant** | Open-source | Rust-based, fast, rich filtering |
| **Supabase** | Postgres + pgvector | Familiar SQL interface, full-stack platform |
| **MongoDB Atlas** | Managed + vector search | Combines document DB with vector capabilities |

### Implementing Vector Search

#### Indexing Embeddings
```python
import chromadb

client = chromadb.Client()
collection = client.create_collection("my_docs")

collection.add(
    documents=["AI is transformative", "Vectors capture meaning", "LLMs generate text"],
    metadatas=[{"source": "doc1"}, {"source": "doc2"}, {"source": "doc3"}],
    ids=["id1", "id2", "id3"]
)
```

#### Performing Similarity Search
```python
results = collection.query(
    query_texts=["What is artificial intelligence?"],
    n_results=2
)
print(results['documents'])  # Most semantically similar documents
```

---

## 8️⃣ RAG (Retrieval-Augmented Generation) & Implementation

### RAG Use Cases
- 📄 Question answering over documents (PDFs, knowledge bases)
- 💬 Customer support chatbots with company-specific knowledge
- 📚 Research assistants searching academic papers
- 🏢 Enterprise search across internal documentation
- 📝 Content generation grounded in specific data

### RAG vs Fine-tuning

| Aspect | RAG | Fine-tuning |
|---|---|---|
| Knowledge updates | Easy — update the database | Requires retraining |
| Cost | Lower upfront | Higher training cost |
| Hallucination | Reduced (grounded in data) | Still possible |
| Use case | Dynamic, frequently changing data | Consistent style/behavior |
| Transparency | Can cite sources | Implicit knowledge |

### Implementing RAG — The Pipeline

```
┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│  1. CHUNKING │ ──▶ │ 2. EMBEDDING │ ──▶ │ 3. VECTOR DB │
│              │     │              │     │   (Storage)  │
│ Split docs   │     │ Convert to   │     │ Index and    │
│ into chunks  │     │ vectors      │     │ store        │
└──────────────┘     └──────────────┘     └──────────────┘

        ╔═══════════════════════════════════════╗
        ║        QUERY TIME (Runtime)           ║
        ╠═══════════════════════════════════════╣
        ║                                       ║
        ║  ┌──────────┐    ┌─────────────────┐  ║
        ║  │ 4. USER  │──▶│ 5. RETRIEVAL    │  ║
        ║  │  QUERY   │   │ Search similar  │  ║
        ║  └──────────┘   │ chunks in DB    │  ║
        ║                  └────────┬────────┘  ║
        ║                           │           ║
        ║                  ┌────────▼────────┐  ║
        ║                  │ 6. GENERATION   │  ║
        ║                  │ LLM generates   │  ║
        ║                  │ answer using     │  ║
        ║                  │ retrieved context│  ║
        ║                  └─────────────────┘  ║
        ╚═══════════════════════════════════════╝
```

#### Step 1: Chunking
- Split documents into manageable pieces
- Strategies: fixed-size, sentence-based, paragraph-based, semantic
- Typical chunk sizes: 256–1024 tokens
- Include overlap between chunks (10-20%)

#### Step 2: Embedding
- Convert each chunk into a vector using an embedding model
- Choose consistent embedding model for indexing and querying

#### Step 3: Vector Database
- Store embeddings with metadata (source, page number, etc.)
- Create appropriate indexes for fast retrieval

#### Step 4-5: Retrieval Process
- Convert user query to embedding (same model)
- Search vector database for top-K similar chunks
- Optionally re-rank results for relevance

#### Step 6: Generation
- Construct prompt with retrieved context + user question
- Send to LLM for grounded response generation

```python
# Simplified RAG implementation
def rag_query(question):
    # 1. Embed the question
    query_embedding = embed(question)
    
    # 2. Retrieve relevant chunks
    relevant_chunks = vector_db.similarity_search(query_embedding, k=5)
    
    # 3. Build prompt with context
    context = "\n".join(relevant_chunks)
    prompt = f"""Answer the question based on the context below.
    
Context: {context}

Question: {question}
Answer:"""
    
    # 4. Generate response
    response = client.chat.completions.create(
        model="gpt-4o",
        messages=[{"role": "user", "content": prompt}]
    )
    return response.choices[0].message.content
```

### Ways of Implementing RAG

#### Using SDKs Directly
- Build custom pipeline using OpenAI SDK + vector DB client
- Full control over every step
- More code, but maximum flexibility

#### LangChain
- Popular framework for building LLM applications
- Provides abstractions for loaders, splitters, embeddings, vector stores, chains
- Large ecosystem of integrations

```python
from langchain.document_loaders import PyPDFLoader
from langchain.text_splitter import RecursiveCharacterTextSplitter
from langchain.embeddings import OpenAIEmbeddings
from langchain.vectorstores import Chroma
from langchain.chains import RetrievalQA
from langchain.chat_models import ChatOpenAI

# Load & chunk
loader = PyPDFLoader("document.pdf")
docs = loader.load()
splitter = RecursiveCharacterTextSplitter(chunk_size=500, chunk_overlap=50)
chunks = splitter.split_documents(docs)

# Embed & store
vectorstore = Chroma.from_documents(chunks, OpenAIEmbeddings())

# Query
qa_chain = RetrievalQA.from_chain_type(
    llm=ChatOpenAI(model="gpt-4o"),
    retriever=vectorstore.as_retriever()
)
answer = qa_chain.run("What is the main topic?")
```

#### LlamaIndex
- Specialized for connecting LLMs to data
- Excellent for RAG with structured/unstructured data
- Built-in indexing strategies and query engines

```python
from llama_index.core import VectorStoreIndex, SimpleDirectoryReader

documents = SimpleDirectoryReader("./data").load_data()
index = VectorStoreIndex.from_documents(documents)
query_engine = index.as_query_engine()

response = query_engine.query("Summarize the key findings")
print(response)
```

#### OpenAI Assistant API
- Managed RAG solution by OpenAI
- Upload files, OpenAI handles chunking, embedding, retrieval
- Simplest implementation but less control

```python
# Create assistant with file search
assistant = client.beta.assistants.create(
    name="Research Assistant",
    instructions="Answer questions based on uploaded documents.",
    model="gpt-4o",
    tools=[{"type": "file_search"}]
)
```

---

## 9️⃣ AI Agents

### What are AI Agents?
- Systems that use LLMs to **reason**, **plan**, and **take actions**
- Can use tools (APIs, databases, code execution) to accomplish tasks
- Operate in loops: Observe → Think → Act → Observe...

### RAG Alternative
- Agents can dynamically decide **when** and **what** to retrieve
- More flexible than static RAG pipelines
- Can combine multiple data sources and tools

### Agents Use Cases
- 🔍 Research agents that search the web and synthesize findings
- 💻 Coding agents that write, test, and debug code
- 📊 Data analysis agents that query databases and create visualizations
- 🛒 Shopping/booking agents
- 📧 Email/calendar management agents
- 🔧 DevOps agents for monitoring and incident response

### Prompt Engineering for Agents

#### ReAct Prompting (Reasoning + Acting)
```
Thought: I need to find the current weather in Tokyo.
Action: search_weather(location="Tokyo")
Observation: Tokyo is currently 22°C with clear skies.
Thought: I now have the information to answer the user.
Answer: The current weather in Tokyo is 22°C with clear skies.
```

### Building AI Agents

#### Manual Implementation
- Build the agent loop yourself
- Parse LLM output for actions/tool calls
- Execute tools and feed results back

```python
def agent_loop(user_query, tools, max_iterations=5):
    messages = [{"role": "user", "content": user_query}]
    
    for _ in range(max_iterations):
        response = client.chat.completions.create(
            model="gpt-4o",
            messages=messages,
            tools=tools
        )
        
        message = response.choices[0].message
        
        if message.tool_calls:
            # Execute tool and add result
            for tool_call in message.tool_calls:
                result = execute_tool(tool_call)
                messages.append(message)
                messages.append({
                    "role": "tool",
                    "tool_call_id": tool_call.id,
                    "content": str(result)
                })
        else:
            return message.content  # Final answer
```

#### OpenAI Functions / Tools
- Define tools as JSON schemas
- Model decides when to call which tool
- Structured output for reliable tool invocation

```python
tools = [{
    "type": "function",
    "function": {
        "name": "get_weather",
        "description": "Get current weather for a location",
        "parameters": {
            "type": "object",
            "properties": {
                "location": {"type": "string", "description": "City name"},
                "unit": {"type": "string", "enum": ["celsius", "fahrenheit"]}
            },
            "required": ["location"]
        }
    }
}]
```

#### OpenAI Assistant API
- Managed agent framework
- Built-in tools: Code Interpreter, File Search, Function Calling
- Handles conversation state and threading

```python
assistant = client.beta.assistants.create(
    name="Data Analyst",
    instructions="Analyze data and create visualizations.",
    model="gpt-4o",
    tools=[
        {"type": "code_interpreter"},
        {"type": "file_search"}
    ]
)
```

---

## 🔟 Multimodal AI

### Multimodal AI Use Cases
- 🖼️ Understanding and analyzing images
- 🎨 Generating images from text descriptions
- 🎬 Analyzing and understanding video content
- 🎵 Processing and generating audio
- 📖 Combining text, image, and audio in applications

### Multimodal AI Tasks

#### Image Understanding
- Image captioning, visual Q&A, OCR
- Scene analysis, object detection
- Document/chart understanding

#### Image Generation
- Text-to-image generation
- Image editing and inpainting
- Style transfer

#### Video Understanding
- Video summarization
- Action recognition
- Scene segmentation

#### Audio Processing
- **Text-to-Speech (TTS)** — convert text to natural-sounding audio
- **Speech-to-Text (STT)** — transcribe audio to text

### Implementing Multimodal AI

#### OpenAI Vision API
```python
response = client.chat.completions.create(
    model="gpt-4o",
    messages=[{
        "role": "user",
        "content": [
            {"type": "text", "text": "What's in this image?"},
            {"type": "image_url", "image_url": {
                "url": "https://example.com/image.jpg"
            }}
        ]
    }]
)
```

#### DALL·E API
```python
response = client.images.generate(
    model="dall-e-3",
    prompt="A futuristic city with flying cars at sunset",
    size="1024x1024",
    quality="hd",
    n=1
)
image_url = response.data[0].url
```

#### Whisper API
```python
# Speech-to-Text
audio_file = open("recording.mp3", "rb")
transcription = client.audio.transcriptions.create(
    model="whisper-1",
    file=audio_file
)
print(transcription.text)

# Text-to-Speech
speech_response = client.audio.speech.create(
    model="tts-1-hd",
    voice="alloy",
    input="Hello! Welcome to AI Engineering."
)
speech_response.stream_to_file("output.mp3")
```

#### Hugging Face Models for Multimodal
- Image: Stable Diffusion, BLIP-2, LLaVA
- Audio: Whisper, Bark, MusicGen
- Video: VideoMAE, X-CLIP

#### LangChain for Multimodal Apps
- Multimodal message types
- Integration with vision models
- Audio/image processing chains

#### LlamaIndex for Multimodal Apps
- Multi-modal vector stores
- Image-text retrieval
- Multi-modal RAG pipelines

---

## 1️⃣1️⃣ Development Tools

### AI Code Editors
- **Cursor** — AI-native code editor (fork of VS Code)
- **GitHub Copilot Workspace** — AI-powered development environment
- **Windsurf** — AI-integrated editor by Codeium

### Code Completion Tools
- **GitHub Copilot** — AI pair programmer in VS Code/JetBrains
- **Codeium** — free AI code completion
- **Amazon CodeWhisperer** — AWS-integrated code assistant
- **Tabnine** — AI code completion with local models

---

## 📚 Learning Path Summary

```
Phase 1: Foundations (Weeks 1-2)
├── Understand AI/LLM basics and terminology
├── Set up OpenAI API and explore Playground
├── Learn prompt engineering fundamentals
└── Build a simple chatbot

Phase 2: Core Skills (Weeks 3-5)
├── Master the OpenAI API (Chat, Embeddings, Moderation)
├── Learn about AI safety and ethics
├── Explore open-source models (Hugging Face, Ollama)
└── Build projects with different models

Phase 3: Embeddings & RAG (Weeks 6-8)
├── Understand embeddings and vector databases
├── Set up a vector database (Chroma/Pinecone)
├── Build a complete RAG pipeline
├── Try LangChain and/or LlamaIndex
└── Build a document Q&A application

Phase 4: Agents & Advanced (Weeks 9-11)
├── Understand AI agents and tool use
├── Build agents with OpenAI Functions
├── Implement ReAct prompting
└── Build a multi-tool agent

Phase 5: Multimodal & Production (Weeks 12-14)
├── Explore vision, audio, and image generation APIs
├── Build a multimodal application
├── Learn production best practices
├── Portfolio project combining multiple concepts
└── Explore AI development tools
```


