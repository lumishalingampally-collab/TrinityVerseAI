# TrinityVerseAI
TrinityVerseAI is a multilingual spiritual conversational AI integrating the Bhagavad Gita, Quran, and Bible with semantic search, LLM-based guidance, emotion detection, multilingual translation, text-to-speech, and contextual audio for personalized spiritual guidance.

# 🙏 TrinityVerseAI
## A Multilingual Spiritual Conversational Intelligence System

TrinityVerseAI is a multilingual spiritual conversational intelligence system that integrates the **Bhagavad Gita, Quran, and Bible** with Artificial Intelligence, semantic search, emotion detection, multilingual translation, and voice guidance.

The system allows users to ask questions related to life, emotions, ethics, personal struggles, and spirituality. It retrieves relevant scripture verses using semantic similarity and uses an AI language model to generate contextual spiritual explanations.

---

## 🌟 Project Overview

TrinityVerseAI combines **Natural Language Processing, Semantic Search, Retrieval-Augmented Generation, Emotion Detection, Generative AI, Multilingual Translation, and Text-to-Speech** into a single interactive application.

The system works by taking a user's question and identifying relevant passages from the selected scripture or from all available scriptures.

The retrieved passages are then provided as context to an AI language model, which generates a spiritual explanation in English. The explanation can subsequently be translated into the user's selected language and converted into speech.

The system also analyzes the emotional context of the user's question and provides contextual background music based on the detected emotion.

---

## 🎯 Objectives

The main objectives of TrinityVerseAI are:

- To develop an AI-powered spiritual conversational system.
- To integrate multiple scripture sources into a unified knowledge base.
- To retrieve relevant scripture passages using semantic search.
- To generate contextual explanations using Large Language Models.
- To provide multilingual spiritual guidance.
- To detect emotions expressed in user queries.
- To provide multilingual text-to-speech guidance.
- To provide contextual audio based on detected emotions.
- To create an interactive and user-friendly AI application.

---

# 📖 Scripture Knowledge Base

TrinityVerseAI integrates three major scripture sources.

## 🕉️ Bhagavad Gita

The Bhagavad Gita component contains:

- Sanskrit verses
- English translations
- Hindi translations
- Transliteration
- Chapter information
- Verse information

The system contains **701 Bhagavad Gita verses**.

---

## 🕌 Quran

The Quran component contains:

- Arabic verses
- English translations
- Multiple language translations
- Transliteration
- Surah information
- Verse information

The system contains **6,236 Quran verses**.

Supported Quran translation languages include:

- English
- Turkish
- French
- Spanish
- Indonesian
- Urdu
- Russian
- Swedish
- Chinese
- Bengali

---

## ✝️ Bible

The Bible component contains Bible verses with reference information and English text.

The Bible content can be searched semantically together with the Bhagavad Gita and Quran.

---

# 🔎 Semantic Search

TrinityVerseAI uses **Sentence Transformers** to convert scripture passages and user questions into numerical vector representations.

The project uses:

```text
all-MiniLM-L6-v2
````

for generating sentence embeddings.

The generated embeddings are stored and searched using **FAISS**.

### Semantic Search Pipeline

```text
User Question
      ↓
Sentence Transformer
      ↓
Query Embedding
      ↓
FAISS Vector Search
      ↓
Most Relevant Scripture Verses
```

The system retrieves the most relevant verses based on semantic similarity rather than simple keyword matching.

Users can search:

* All Scriptures
* Bhagavad Gita
* Quran
* Bible

---

# 🤖 Generative AI

After retrieving the relevant scripture passages, TrinityVerseAI uses the **Groq API** to generate a contextual spiritual explanation.

The project uses:

```text
Llama 3.3 70B Versatile
```

The retrieved scripture verses are provided to the model as context.

### AI Generation Pipeline

```text
User Question
      ↓
Semantic Search
      ↓
Relevant Scripture Verses
      ↓
Context Construction
      ↓
Groq API
      ↓
Llama 3.3 70B
      ↓
English Spiritual Explanation
```

The generated explanation is then used for multilingual translation and audio generation.

---

# 🌍 Multilingual Support

TrinityVerseAI supports multiple output languages.

Currently supported languages include:

* English
* Hindi
* Telugu
* Tamil
* Urdu
* Kannada
* Malayalam
* Gujarati
* Marathi
* Bengali
* Arabic
* French
* Spanish

The system first generates the main explanation in English and then translates the explanation into the language selected by the user.

---

# 🧠 Emotion Detection

TrinityVerseAI includes an emotion detection component.

A custom emotion classification model is trained using the **GoEmotions dataset**.

The system focuses on emotions including:

```text
anger
annoyance
caring
confusion
disappointment
fear
grief
joy
love
nervousness
sadness
optimism
```

The custom model uses:

```text
TF-IDF
+
N-grams
+
Random Forest Classifier
```

---

# 🔬 Hybrid Emotion Detection

The project also includes a pretrained **DistilBERT emotion classification model** as a secondary validation mechanism.

The system first uses the custom Random Forest classifier.

If the prediction confidence is low, the pretrained model is used to provide an additional emotion prediction.

### Emotion Detection Pipeline

```text
User Question
      ↓
TF-IDF Vectorization
      ↓
Custom Random Forest Classifier
      ↓
Confidence Check
      ↓
High Confidence
      ↓
Custom Emotion

Low Confidence
      ↓
DistilBERT Validation
      ↓
Refined Emotion
```

---

# 🎵 Emotion-Based Contextual Music

The detected emotional state is used to select contextual background music.

For example, emotions such as:

```text
Sadness
Grief
Fear
Anger
Nervousness
```

can trigger calming or soothing audio.

More positive emotional states can trigger uplifting background music.

The music selection also considers the selected scripture source.

---

# 🔊 Multilingual Text-to-Speech

The project uses **gTTS (Google Text-to-Speech)** to generate audio.

Two types of audio are produced:

### 1. Verse Recitation

The original scripture verse or transliteration is converted into speech.

### 2. Explanation Audio

The AI-generated explanation is translated into the selected language and converted into speech.

### Audio Pipeline

```text
Scripture Verse
      ↓
Text-to-Speech
      ↓
Verse Recitation

AI Explanation
      ↓
Translation
      ↓
Text-to-Speech
      ↓
Explanation Audio
```

---

# 🖥️ Interactive User Interface

The application uses **Gradio** to provide an interactive user interface.

Users can enter a question and select:

### Scripture Source

```text
All
Bhagavad Gita
Quran
Bible
```

### Output Language

The user can select their preferred language.

The system then provides:

* Relevant scripture verses
* Original scripture text
* Transliteration where available
* Translation
* AI-generated explanation
* Translated explanation
* Verse recitation
* Explanation audio
* Detected emotion
* Contextual background music

---

# 🏗️ System Architecture

```text
                         USER
                           │
                           ▼
                  ┌─────────────────┐
                  │   Gradio UI     │
                  └────────┬────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │ User Question   │
                  └────────┬────────┘
                           │
             ┌─────────────┴─────────────┐
             │                           │
             ▼                           ▼
    ┌──────────────────┐       ┌──────────────────┐
    │ Semantic Search  │       │ Emotion Detection│
    └────────┬─────────┘       └────────┬─────────┘
             │                          │
             ▼                          ▼
    ┌──────────────────┐       ┌──────────────────┐
    │ Sentence         │       │ Random Forest +  │
    │ Transformer      │       │ DistilBERT       │
    └────────┬─────────┘       └────────┬─────────┘
             │                          │
             ▼                          ▼
    ┌──────────────────┐       ┌──────────────────┐
    │ FAISS Vector     │       │ Emotion Result   │
    │ Search           │       └────────┬─────────┘
    └────────┬─────────┘                │
             │                          ▼
             ▼                   ┌──────────────────┐
    ┌──────────────────┐         │ Music Selection  │
    │ Relevant Verses  │         └──────────────────┘
    └────────┬─────────┘
             │
             ▼
    ┌─────────────────────────┐
    │ Groq API                │
    │ Llama 3.3 70B           │
    └───────────┬─────────────┘
                │
                ▼
       English Explanation
                │
                ▼
       ┌──────────────────┐
       │ Multilingual     │
       │ Translation      │
       └────────┬─────────┘
                │
                ▼
       ┌──────────────────┐
       │ gTTS             │
       │ Text-to-Speech   │
       └────────┬─────────┘
                │
                ▼
          FINAL RESPONSE
```

---

# 🛠️ Technologies Used

| Technology            | Purpose                                |
| --------------------- | -------------------------------------- |
| Python                | Core programming language              |
| Google Colab          | Development environment                |
| Sentence Transformers | Text embeddings                        |
| all-MiniLM-L6-v2      | Semantic embeddings                    |
| FAISS                 | Vector similarity search               |
| Groq API              | LLM inference                          |
| Llama 3.3 70B         | Explanation generation and translation |
| Scikit-learn          | Machine learning                       |
| TF-IDF                | Text feature extraction                |
| Random Forest         | Emotion classification                 |
| DistilBERT            | Emotion validation                     |
| gTTS                  | Text-to-speech                         |
| Gradio                | Interactive user interface             |
| NumPy                 | Numerical computation                  |
| Pandas                | Dataset processing                     |
| Joblib                | Model serialization                    |

---

# 📂 Project Structure

```text
TrinityVerseAI/
│
├── TrinityVerseAI.ipynb
├── README.md
│
├── gitadata/
│   ├── verse.json
│   ├── translation.json
│   └── corrected_translation_gpt3.json
│
├── qurandata/
│   ├── quran_en.json
│   ├── quran_tr.json
│   ├── quran_fr.json
│   ├── quran_es.json
│   ├── quran_id.json
│   ├── quran_ur.json
│   ├── quran_ru.json
│   ├── quran_sv.json
│   ├── quran_zh.json
│   ├── quran_bn.json
│   └── quran_transliteration.json
│
├── bibledata/
│   └── verses-1769.json
│
├── screenshots/
│   ├── interface.png
│   ├── result.png
│   └── audio.png
│
└── requirements.txt
```

---

# ⚙️ Installation

Install the required dependencies:

```bash
pip install sentence-transformers faiss-cpu gTTS gradio groq
```

For emotion detection:

```bash
pip install pandas scikit-learn joblib transformers torch
```

---

# 🔑 API Configuration

TrinityVerseAI uses the Groq API for AI-generated spiritual explanations and multilingual translation.

For security, API keys should **never be hard-coded or uploaded to GitHub**.

Use an environment variable:

```python
import os
from groq import Groq

groq_client = Groq(
    api_key=os.environ.get("GROQ_API_KEY")
)
```

Set the API key in the environment before running the project.

---

# ▶️ How to Run

The project was developed and tested using Google Colab.

### Step 1

Open the notebook:

```text
TrinityVerseAI.ipynb
```

### Step 2

Install the required dependencies.

### Step 3

Mount Google Drive if the datasets are stored there.

### Step 4

Load the Bhagavad Gita, Quran, and Bible datasets.

### Step 5

Generate sentence embeddings.

### Step 6

Build the FAISS vector index.

### Step 7

Load/train the emotion detection model.

### Step 8

Launch the Gradio interface.

### Step 9

Enter a question.

### Step 10

Select:

* Scripture source
* Output language

### Step 11

Generate the spiritual response.

---

# 💬 Example Questions

Users can ask questions such as:

```text
How can I control my anger?

How can I overcome fear?

How can I deal with sadness?

How can I find hope during difficult times?

How can I become more compassionate?

How should I deal with failure?

How can I find inner peace?

How can I control negative thoughts?
```

The system searches for relevant scripture passages and generates contextual guidance.

---



# 🔬 Technical Methodology

The project combines multiple AI techniques.

## Natural Language Processing

NLP is used for:

* Query processing
* Text embeddings
* Semantic similarity
* Translation
* Emotion classification

## Semantic Retrieval

Sentence Transformers convert scripture passages into embeddings.

FAISS performs efficient vector similarity search to identify relevant verses.

## Retrieval-Augmented Generation

The system follows a retrieval-first approach:

```text
Question
   ↓
Retrieve Relevant Verses
   ↓
Provide Verses as Context
   ↓
LLM Generation
   ↓
Grounded Spiritual Explanation
```

This allows the generated response to be based on retrieved scripture passages.

## Machine Learning

A Random Forest classifier is trained using TF-IDF and n-gram features for emotion detection.

## Deep Learning

A pretrained DistilBERT model is used for additional emotion validation.

## Generative AI

Llama 3.3 70B is used to generate spiritual explanations and perform multilingual translation.

---

# 🎓 Academic Information

**Project Title:**

### TrinityVerseAI: A Multilingual Spiritual Conversational Intelligence System

**Project Type:**

B.Tech Major Project

**Domain:**

Artificial Intelligence and Machine Learning

**Major Technologies:**

```text
Artificial Intelligence
Machine Learning
Natural Language Processing
Generative AI
Large Language Models
Semantic Search
Vector Databases
Emotion Detection
Multilingual AI
Text-to-Speech
```

---

# 🚀 Future Enhancements

Future versions of TrinityVerseAI can include:

* Voice input
* Speech-to-text interaction
* Real-time voice conversations
* Additional scripture and philosophical sources
* Improved multilingual embeddings
* Advanced multilingual RAG
* Improved emotion classification
* Personalized conversation history
* User accounts and preferences
* Mobile application
* Cloud deployment
* Improved verse verification
* Better contextual audio recommendations
* Offline AI inference

---

# ⚠️ Limitations

* AI-generated explanations may not represent authoritative religious interpretations.
* Semantic search depends on the quality of the underlying datasets.
* Machine-learning-based emotion detection may not always correctly identify complex or mixed emotions.
* Translation quality can vary between languages.
* Text-to-speech quality depends on language and TTS support.
* The system is designed for educational and spiritual reflection purposes and should not replace professional medical, psychological, legal, or religious guidance.

---

# 🔐 Security

Never commit API keys, authentication tokens, passwords, or other secrets to GitHub.

Use environment variables or secret-management solutions for sensitive credentials.

Large datasets and model files that exceed GitHub's file-size limits should be stored separately or managed using appropriate large-file storage solutions.

---

# 📌 Project Highlights

```text
🕉️ Bhagavad Gita Integration
🕌 Quran Integration
✝️ Bible Integration
🔎 Semantic Search
📚 FAISS Vector Search
🤖 Llama 3.3 70B
🔗 Groq API
🧠 Emotion Detection
🌍 Multilingual Translation
🔊 Text-to-Speech
🎵 Emotion-Based Music
🖥️ Gradio Interface
```

---

# 📜 Disclaimer

TrinityVerseAI is an academic and experimental AI project developed for educational and research purposes.

The responses generated by the system are AI-generated and should not be considered definitive interpretations of religious scripture.

Users should refer to authentic religious texts and qualified religious scholars or spiritual leaders for authoritative interpretation.

---

# 👩‍💻 Author

Developed as a B.Tech Major Project.


#  Output
<img width="976" height="630" alt="image" src="https://github.com/user-attachments/assets/65389fae-ed8d-4d8d-8918-3e7f0a040976" />

<img width="976" height="840" alt="image" src="https://github.com/user-attachments/assets/054e5fd5-9a55-4198-9b4d-698fa539c1c3" />

