# 🤖 StudyBot — A Smart Student Assistant

**Course:** Natural Language Processing (AI 2026)  
**Module:** 08 — Building Chatbots & Agents  
**Tools used:** Python · LangChain · LangGraph · Ollama (Llama 3.2)

---

## 📌 What is StudyBot?

StudyBot is a chatbot that can help students check their grades and calculate their scores.

It is smarter than a normal chatbot like ChatGPT because it can:
- **Look up real data** — it connects to a student database to get grades
- **Do math correctly** — it uses a calculator tool so it never makes math mistakes
- **Remember the conversation** — it remembers what you said earlier without you repeating yourself

---

## ❓ Why is this better than ChatGPT?

| | ChatGPT | StudyBot |
|---|---|---|
| Can do math correctly? | ❌ Sometimes wrong | ✅ Always correct |
| Can look up private data? | ❌ No | ✅ Yes |
| Remembers what you said? | ❌ Not always | ✅ Yes |
| Needs internet / API key? | ✅ Yes | ❌ No — runs on your computer |

---

## 🛠️ The Two Tools

StudyBot has two special tools it can use when needed:

### Tool 1 — Calculator
When the bot needs to do math, it uses this tool instead of guessing.

**Example:**
```
User asks: What is Bob's final grade if midterm = 70 and final exam = 75?
Bot uses calculator: 70 × 0.4 + 75 × 0.6
Answer: 73.0  ✅ (always correct)
```

### Tool 2 — Student Lookup
The bot connects to a student database to get real grade information.
ChatGPT does not have this data — StudyBot does.

**Example:**
```
User asks: What are Bob's Math grades?
Bot looks up the database and finds:
  Midterm: 70
  Final exam: 75
```

---

## 🔄 How Does It Work?

The bot follows a simple loop called **ReAct**:

```
1. User sends a message
2. Bot thinks: "Do I need a tool?"
3a. YES → Bot uses the tool → Gets the result → Thinks again
3b. NO  → Bot replies directly
4. Repeat until done
```

This loop is built with **LangGraph**, which controls when the bot thinks and when it uses a tool.

---

## 💬 Example Conversation

```
👤 User: What are Alice's grades in NLP?

🔧 Bot uses: student_lookup → finds Alice's NLP grades
📊 Result: Midterm = 95, Final = 98

🤖 StudyBot: Alice is doing great in NLP!
   Midterm: 95, Final exam: 98.

---

👤 User: What is her final grade? Midterm counts 40%, final counts 60%.

🔧 Bot uses: calculator → 95 × 0.4 + 98 × 0.6
📊 Result: 96.8

🤖 StudyBot: Alice's final NLP grade is 96.8. Well done Alice! 🎉

---

👤 User: Who did better — Alice in NLP or Bob in Math?

🔧 Bot remembers Alice's score from earlier (no need to look it up again)
🔧 Bot uses: student_lookup → gets Bob's Math grades
🔧 Bot uses: calculator → compares the two scores

🤖 StudyBot: Alice did better with 96.8 vs Bob's 73.0.
```

---

## 💻 How to Run It

### Step 1 — Install Ollama
Download from [ollama.com](https://ollama.com) and install it. It is free.

### Step 2 — Download the AI model
Open a terminal and run:
```bash
ollama pull llama3.2
```
This downloads the AI to your computer (about 2GB, one time only).

### Step 3 — Install Python packages
```bash
pip install langchain langgraph langchain-ollama
```

> **Windows users:** If you get an error, try this instead:
> ```bash
> pip install langchain langgraph langchain-ollama --no-deps
> pip install pydantic httpx tenacity PyYAML requests
> ```

### Step 4 — Open the notebook
Open the `.ipynb` file in **VS Code** or **Jupyter** and run all cells.

> ⚠️ This does **not** work in Google Colab — the AI runs on your computer, not online.

---

## 📁 Files in This Repo

```
📂 studybot-repo/
├── 📓 studybot_agent_V1-FM-ITAI-237.ipynb   ← The main code + results
├── 📄 README.md                              ← This file
├── 📄 AI_Usage.md                             ← This file
├── 📄 powerpoint                            ← This file
└── 📄 requirements.txt                       ← List of packages needed
```

---

## 💡 Ideas to Make It Better

💡 Want to Contribute or Build on This?
This project is a great starting point. If you want to take it further, here are some ideas:

🔍 Add a web search tool — so the bot can search Google for study tips
🗓️ Add a schedule tool — to show class timetables
💾 Connect a real database — replace the fake student data with a real one
🖥️ Build a chat interface — add a simple website so you can chat with it in a browser
🔄 Try different AI models — swap Llama for Mistral, Gemma, or any other free Ollama model

Feel free to fork this repo and make it your own!

---

*Assignment for AI 2026 — Natural Language Processing, Module 08*
