# 📚 Lesson 1.1: The Data Landscape

## Session Overview

| | |
|---|---|
| **Duration** | 3 hours |
| **Format** | Flipped Classroom + Discussion |
| **Tools** | Google Colab (for code demo) |
| **Prerequisite** | Pre-class reading on the Data Science Hierarchy of Needs |

## Agenda

| Time | Part | Topic |
|------|------|-------|
| 0:00 – 1:00 | Part 1 | The Hierarchy of Insights — Analytics vs. Data Science vs. AI |
| 1:00 – 2:00 | Part 2 | The Data Highway — Pipelines & Data Structures |
| 2:00 – 3:00 | Part 3 | The Conscious Algorithm — Ethics & Bias |

---

## 🏃 Part 1: The Hierarchy of Insights (60 min)

### 🎯 Learning Objective
Explain the difference between Data Analytics, Data Science, and Artificial Intelligence.

### Concept Overview (10 min)

**Analogy:** Imagine a kitchen.
- **Data Analytics** is checking the fridge to see what's left and writing a report on what was eaten (Historical).
- **Data Science** is using that list to predict what ingredients you'll need for next week's dinner (Predictive).
- **AI** is a robot chef that sees the fridge is empty and orders the groceries for you (Automated Action).

### 🛠️ Workshop: "The Company Diagnostic" (40 min)

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

# Predict next month's sales (March) based on February's sales and the growth rate
predicted_sales_march = df['Sales'].iloc[1] * (1 + growth_rate)

print(f"\nPredicted sales for March: {predicted_sales_march:.2f}")
```

### 💬 Q&A & Reflection (10 min)

- Does AI replace Data Science — or depend on it?
- How does Netflix use Analytics, Data Science, and AI differently in its product?

---

## 🏃 Part 2: The Data Highway (60 min)

### 🎯 Learning Objective
Identify the 4 stages of a Data Pipeline and distinguish between Structured, Unstructured, and Semi-Structured data.

### Concept Overview (10 min)

**The Pipeline:** Collection ➔ Cleaning ➔ Analysis ➔ Visualisation

**Data Structure Analogy:**
- **Structured:** Think of an Egg Carton — everything has a specific slot/cell.
- **Unstructured:** Think of a bag of groceries — items are all mixed up; you have to sort them yourself.
- **Semi-Structured:** In-between — has some organisation but no rigid schema (e.g. JSON).

### 🛠️ Activity 1: "The Smart Watch Data Pipeline" (20 min)

**Scenario:** You are designing the data flow for a "Sleep Tracker" app.

**Task:** Fill in the blanks below with your group.

| Pipeline Stage | What happens here? (Specific to a Smart Watch) |
|:---|:---|
| **1. Collection** | *Example: Heart rate sensor records BPM every 5 seconds...* |
| **2. Cleaning** | *(What if the user takes the watch off? What if the battery dies mid-night?)* |
| **3. Analysis** | *(How do we turn raw heartbeats into a "Sleep Score"? What is the math?)* |
| **4. Visualisation** | *(What does the user actually see on their phone screen?)* |

**Discussion Question:**

If the "Cleaning" stage fails (e.g., we count the time the watch was on the nightstand as "Deep Sleep"), how does that ruin the "Visualisation"?

### 🛠️ Activity 2: "Data Binning" (20 min)

**Task 1:** Categorise each of the following hospital data items as Structured, Unstructured, or Semi-Structured:

1. Patient Name ("John Doe")
2. X-Ray Image (chest_scan_001.jpg)
3. Doctor's handwritten notes on a clipboard
4. Patient Age (34)
5. Blood Type (O+)
6. Audio recording of a patient consultation
7. JSON log from a heart monitor `{"bpm": 80, "time": "12:00"}` *(Tricky — discuss!)*

**Question:** How can you convert Unstructured text (like a doctor's note) into Structured data? Give an example.

### 💬 Q&A & Reflection (10 min)

- Is JSON structured or unstructured? Where does it sit on the spectrum?
- Why do Data Scientists reportedly spend ~80% of their time in the Cleaning stage?

---

## 🏃 Part 3: The Conscious Algorithm (60 min)

### 🎯 Learning Objective
Recognise potential sources of ethical bias in data collection and understand how "Clean Data" can still be "Biased Data".

### Concept Overview (10 min)

**Key Bias Types:**
- **Selection Bias:** The data you collected doesn't represent the whole world.
- **Historical Bias:** The data reflects past prejudices (e.g., hiring data from the 1970s).
- **Garbage In, Garbage Out:** Perfect code cannot fix broken data.

### 🛠️ Workshop: "The Hiring Bot Post-Mortem" (40 min)

**Scenario:**

You build an AI to screen resumes for a tech company. You train it on the company's "Top Performer" data from the last 10 years.

- **The Data:** 10 years of resumes from employees promoted to Manager.
- **The Result:** The AI starts rejecting all candidates from a nursing background and downgrades resumes containing the word "Women's College".

**Group Discussion:**

1. Why did the AI do this? Was the AI sexist, or was the *data* sexist?
2. Was this a "Data Collection" error or an "Analysis" error?
3. How would you fix this? *(Hint: Can you simply "delete" the gender column? Why might that not be enough?)*

**Output:** Write a one-sentence "Warning Label" that should be placed on this dataset before any Data Scientist uses it.

### 💬 Q&A & Reflection (10 min)

- Can we ever have 100% unbiased data? If not, what can we do?
- What is the cost — financial and reputational — when an AI system fails in a public-facing application?

---

## 🎯 Wrap-Up

**Key Takeaways:**
1. Analytics, Data Science, and AI are a hierarchy — most companies are still working on getting their data clean.
2. ~80% of data work is Collection and Cleaning. The analysis is the remaining 20%.
3. Clean data ≠ Unbiased data. Historical and selection biases are encoded in data that looks perfectly formatted.

**Next Steps:**
- Complete the [Assignment](./assignment.md) — group discussion questions about the data lifecycle.
- Next lesson: Lesson 1.2 covers database design — how data is structurally organised before it can be queried.
