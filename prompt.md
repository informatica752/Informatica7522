---
layout: default
title: 🤖 LLM Prompts
---

# 🤖 LLM Querying & Prompt Engineering

To retrieve the missing data for the points of interest in **Arco**, we queried Large Language Models (LLMs) using different Prompt Engineering strategies. 

## 🛠️ Models Utilized
* **ChatGPT (OpenAI):** Utilized for its high precision in structured formatting and complex reasoning tasks.
* **Gemini (Google):** Employed for its strong contextual understanding and fluid textual generation.

The choice of the prompting technique was carefully selected and adapted for both models based on the nature of the data to be extracted (e.g., free-form text, strict formats, or data requiring logical reasoning).

Below is the methodological overview of the three techniques applied across ChatGPT and Gemini: **Zero-Shot**, **Few-Shot**, and **Chain-of-Thought**.

## 🔬 The Three Prompting Techniques Used

### 1. 🎯 Zero-Shot Prompting
This technique involves making a direct request to the models **without providing any examples**. The models rely exclusively on the knowledge pre-trained within their parameters.
* **Best for:** Simple linguistic tasks, summarization, or straightforward factual data retrieval.

### 2. 📋 Few-Shot Prompting
This consists of providing the models with **one or more concrete examples** (input/output pairs) before asking the final question. This conditions the LLMs to strictly follow a specific style, length, or syntactic structure.
* **Best for:** Output standardization, style matching and extracting structured media links.

### 3. 🧠 Chain-of-Thought (CoT)
This technique forces the models to **break down a complex problem and "think aloud"**, displaying intermediate logical steps before delivering the final answer.
* **Best for:** Complex reasoning or analyzing multi-variable rules and pricing sheets.
* 
---

## 📊 Prompt Strategy Overview

The table below summarizes the exact prompting strategy used for each missing data point across our LLM workflows:

| Missing Data | Chosen Technique | Rationale & Objective |
| :--- | :--- | :--- |
| **1. 📝 Description** | `Few-Shot` | Guides the models to generate descriptions matching a specific length, tone, and editorial style. |
| **2. 🔗 Wikidata link** | `Zero-Shot` | Direct extraction of the unique knowledge-graph URL from the models' database. |
| **3. 📍 Coordinates** | `Zero-Shot` | Straightforward retrieval of numerical values (Lat, Lon) for the locations. |
| **4. 📷 Official image** | `Few-Shot` | Ensures the model follows the exact syntax and domain pattern required for media assets. |
| **5. 🎟️ Entrance ticket**| `Chain-of-Thought` | Step-by-step analysis of standard rates, concessions, and free entry criteria. |
| **7. 📞 Contact** | `Zero-Shot` | Quick and direct extraction of available telephone numbers and email addresses. |

> ⚠️ **Methodological Note:** Although ChatGPT and Gemini proved highly capable of retrieving information, all data extracted through these techniques underwent a manual validation process to eliminate hallucinations, especially regarding URLs and coordinates.










## 🎟️ 5. Entrance Ticket

Finding out the price of admission tickets can be tricky because prices often change based on age groups, student discounts, or free entry rules. To make sure ChatGPT and Gemini didn't make mistakes, we used a **Chain-of-Thought (CoT)** prompt. This forced the models to reason step-by-step and look at all the different ticket options before giving us the final price.

### Prompt Used 

### LLM Outputs & Validation

Below are the visual results obtained from the models showing their logical breakdown before compiling the required data layout:

#### ChatGPT Response
![ChatGPT Entrance Ticket Screen](path-to-your-image/chatgpt-ticket.png)

#### Gemini Response
![Gemini Entrance Ticket Screen](path-to-your-image/gemini-ticket.png)

---

## 📞 7. Contacts

To retrieve official contact information such as telephone numbers, email addresses, and official websites, we implemented a **Zero-Shot** approach. Since we needed a strict structural separation between phone contacts and email lists to facilitate seamless database integration, the prompt embedded formatting constraints directly into the natural language instructions.

### The Prompt Used
> Please find the official contact information for the following point of interest in Arco (Trentino, Italy).
> 
> Search for phone numbers, email addresses, and the official website. You must separate the phone numbers section from the email section so they are distinct and easy to copy. If there are multiple phone numbers or emails (for example, for both the ticket office and the cultural office), please list them all.
> 
> If a specific piece of information is missing, just write N/D.

### LLM Outputs & Validation

Both models successfully processed the request, cleanly partitioning the operational telephone channels from the digital mailing endpoints as shown below:

#### ChatGPT Response
![ChatGPT Contacts Screen](path-to-your-image/chatgpt-contacts.png)

#### Gemini Response
![Gemini Contacts Screen](path-to-your-image/gemini-contacts.png)









