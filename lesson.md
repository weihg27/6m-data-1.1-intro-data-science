# 🎓 Lesson 1.1: Intro to Data Science — Instructor Guide

## Session Overview

| Item | Detail |
|------|--------|
| **Duration** | 3 hours |
| **Format** | Flipped Classroom + Discussion-Based Learning |
| **Prerequisites** | Pre-class reading on the Data Science Hierarchy of Needs |
| **Tools** | No software required — whiteboard, slides, and discussion |

### Agenda

| Time | Section | Focus |
|------|---------|-------|
| 0:00 – 0:55 | Part 1: The Hierarchy of Insights | Analytics vs. Data Science vs. AI |
| 0:55 – 1:00 | Break | — |
| 1:00 – 1:55 | Part 2: The Data Highway | Data Pipeline; Structured vs. Unstructured data |
| 1:55 – 2:00 | Break | — |
| 2:00 – 2:55 | Part 3: The Conscious Algorithm | Ethics, Bias, and Garbage In, Garbage Out |
| 2:55 – 3:00 | Wrap-Up | Key Takeaways & Post-Class Assignment Briefing |

---

## 🏃 Part 1: The Hierarchy of Insights (55 min)

### 🎯 Learning Objective
Explain the difference between Data Analytics, Data Science, and Artificial Intelligence using real-world analogies.

### 📖 Theory Recap (10 min)

**Analogy:** Imagine a kitchen.
- **Data Analytics** checks the fridge and reports what was eaten *(Historical — "What happened?")*
- **Data Science** predicts what ingredients you'll need next week *(Predictive — "What will happen?")*
- **AI** automatically orders groceries when the fridge is empty *(Automated Action — "Do it without me.")*

| | Data Analytics | Data Science | Artificial Intelligence |
|--|---|---|---|
| **Goal** | Explain past events | Predict future outcomes | Automate human-like decisions |
| **Question** | "Why did sales drop?" | "How many sales next month?" | "Auto-reorder when stock is low" |
| **Analogy** | Rear-view mirror | Weather forecast | Self-driving car |

**Discussion:**

- "If a CEO says 'I want to build a GPT-4 for my company' but all their data is in paper files, where on the hierarchy are they failing?"
- "If we scanned those papers into PDFs, would that be enough to build an AI tomorrow? Or is there still a 'Cleaning' and 'Analysis' step missing?"

**Activity:**

1. **The Matrix:** Classify each of the following 5 scenarios as Data Analytics, Data Science, or AI — and explain your reasoning:
   - A bank system that automatically flags unusual transactions in real time
   - A manager building a monthly pivot table of sales figures
   - A self-driving car that brakes automatically when it detects an obstacle
   - A model that predicts which customers are likely to churn next quarter
   - A dashboard showing last year's revenue broken down by region

2. **The Python Peek (Code Demo):** Run the following code in Colab and observe the difference between reporting and modelling:

```python
# How we see data vs how the computer sees it
import pandas as pd

# A simple 'Historical' dataset (Analytics)
data = {'Month': ['Jan', 'Feb'], 'Sales': [100, 150]}
df = pd.DataFrame(data)
print("Analytics: What happened?")
print(df)

# Predicting (Data Science)
# Calculate the month-over-month growth rate
# Sales for Jan: df['Sales'].iloc[0]
# Sales for Feb: df['Sales'].iloc[1]

growth_rate = (df['Sales'].iloc[1] - df['Sales'].iloc[0]) / df['Sales'].iloc[0]
print(f"Month-over-month growth rate: {growth_rate:.2%}")

**Discussion Questions:**
- "If the CEO scans all paper files to PDFs, can they build AI tomorrow? What steps are still missing?"
- "Which of these scenarios would fail without the cleaning step?"

### 💬 Q&A & Reflection (10 min)

- **Common Misconception:** "Does AI replace Data Science?" → No. AI *applies* the discoveries that Data Science makes. You need Data Scientists to build, monitor, and improve AI systems.
- **Business Case:** Netflix uses Analytics for billing (historical), Data Science for recommendations (predictive), and AI for auto-playing the next episode (automated action). All three coexist.

---

## 🏃 Part 2: The Data Highway (55 min)

### 🎯 Learning Objective
Identify the 4 stages of a standard Data Pipeline and distinguish between Structured, Unstructured, and Semi-Structured data.

### 📖 Theory Recap (10 min)

**The Pipeline:** Collection ➔ Cleaning ➔ Analysis ➔ Visualisation

**Data Structure Analogy:**
- **Structured:** An egg carton — fixed slots, predictable format, easily queried (spreadsheets, databases)
- **Unstructured:** A bag of groceries — mixed items with no fixed schema (images, audio, free text)
- **Semi-structured:** A recipe card — has some structure but flexible (JSON, XML, logs)

### 🛠️ Hands-On Activity 1: "The Smart Watch Data Pipeline" (15 min)

**Scenario:** Design the data flow for a Sleep Tracker app.

**Task:** Complete the pipeline stages table for a wearable heart rate monitor:

| Stage | What Happens | Potential Failure |
|-------|-------------|-------------------|
| Collection | Heart rate sensor records BPM every 5 seconds | Watch removed; battery dies |
| Cleaning | Handle data gaps and watch-removal periods | Nightstand time counted as sleep |
| Analysis | Convert heartbeats into a "Sleep Score" | Algorithm miscalculates REM cycles |
| Visualisation | Display results on user's phone | Misleading chart scale |

**Discussion:** How does a Cleaning failure in stage 2 corrupt the Visualisation in stage 4?

### 🛠️ Hands-On Activity 2: "Data Binning" (20 min)

**Task:** Categorise these hospital data items as Structured, Unstructured, or Semi-Structured:

1. Patient Name ("John Doe") → *Structured*
2. Chest X-Ray image file → *Unstructured*
3. Doctor's handwritten notes → *Unstructured*
4. Patient Age (34) → *Structured*
5. Blood Type (O+) → *Structured*
6. Audio recording of consultation → *Unstructured*
7. JSON heart monitor log `{"bpm": 80, "time": "12:00"}` → *Semi-Structured*

**Bonus Discussion:** How would you convert doctor's notes (unstructured) into structured data for analysis?

### 💬 Q&A & Reflection (10 min)

- **Common Misconception:** "Is JSON structured or unstructured?" → Neither — it's **semi-structured**. It has internal organisation (key-value pairs) but no rigid, predefined schema like a relational database table.
- **Business Case:** Data Scientists spend approximately **80% of their time in the Cleaning stage**. Mastering this step is one of the highest-leverage skills in the profession.

---

## 🏃 Part 3: The Conscious Algorithm (55 min)

### 🎯 Learning Objective
Recognise sources of ethical bias in data collection and explain why technically clean data can still produce biased outcomes.

### 📖 Theory Recap (10 min)

**The Key Biases:**
- **Selection Bias:** Your collected data doesn't represent the whole population (e.g., a survey only reaching smartphone users).
- **Historical Bias:** Your data reflects past inequalities (e.g., 1970s hiring patterns where management was 95% male).
- **Confirmation Bias:** You only collect data that confirms what you already believe.

**The Rule:** Garbage In, Garbage Out — no amount of sophisticated modelling fixes fundamentally broken data. But even *clean* data can encode bias from the world it was collected in.

### 🛠️ Hands-On Activity: "The Hiring Bot Post-Mortem" (35 min)

**Scenario:** A tech company built an AI resume screener trained on 10 years of "Top Performer" data — employees who were promoted to Manager.

**The Result:** The AI automatically rejects candidates with nursing backgrounds and downgrades resumes containing "Women's College."

**Group Discussion (25 min):**
1. Why did the AI behave this way? Was the AI itself sexist, or was the data sexist?
2. Was this a Data Collection error or an Analysis error?
3. If you delete the "Gender" column from the training data, is the problem solved? Why or why not?
4. Write a one-sentence **Warning Label** for this dataset.

**Share Out (10 min):** Groups present their Warning Labels. Discuss: what would responsible deployment of this tool look like?

### 💬 Q&A & Reflection (10 min)

- **Common Misconception:** "If we just remove sensitive attributes (gender, race), the bias disappears." → Proxy variables (university name, postcode, name) encode the same information. Removing the label doesn't remove the signal.
- **Business Case:** Amazon scrapped their AI recruiting tool in 2018 after discovering it systematically downgraded female candidates — exactly this scenario. The cost: years of engineering investment and significant reputational damage.

---

## 🎯 Wrap-Up (5 min)

### Key Takeaways
1. **Analytics, Data Science, and AI** are a hierarchy — you need each layer before you can build the next. Most companies are still working on cleaning their data.
2. **80% of data work** is Collection and Cleaning. The glamorous analysis and modelling is the remaining 20%.
3. **Clean data ≠ Unbiased data.** Historical and selection biases are encoded in data that looks perfectly formatted.

### Next Steps
- **Post-Class:** Complete the [Netflix Case Study](./assignment.md) — group discussion questions about the data lifecycle (45–60 min).
- **Next Lesson:** Lesson 1.2 dives into database design — how data is structurally organised before it can be queried.
