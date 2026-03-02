# HR Attrition Insight Generator

## Overview

This project explores how generative AI can support HR attrition analysis. The goal was to evaluate whether a large language model could take structured HR data and reliably generate clear summaries, retention recommendations, and audience-specific communication — and then improve consistency through fine-tuning.

The project is structured across three milestones, ending with a working interactive app inside Jupyter.

---

## Objectives

This project aimed to answer three key questions:

Can a base LLM handle HR attrition tasks well enough to be useful without fine-tuning?
Does fine-tuning on HR-specific examples improve consistency in tone, format, and structure?
Can the model be wrapped in a simple interface that a non-technical HR user could realistically use?

---

## Milestone 2 — Prompt Experiments (Anthropic API)

Before fine-tuning, five prompt types were tested against Claude using the Anthropic API to establish a performance baseline.

| Experiment | Task |
|------------|------|
| 1 | Summarize attrition data in 2–3 sentences |
| 2 | Generate 3 specific retention recommendations |
| 3 | Compare multiple departments and suggest one company-wide action |
| 4 | Create conservative, moderate, and aggressive hiring scenarios |
| 5 | Rewrite the same insight for two different audiences |

The base model performed better than expected across all five tasks. It correctly interpreted attrition rates, identified high-risk groups, and adjusted tone for different audiences without additional prompting.

The main weakness was inconsistency. The same prompt type could return different formatting or closing styles across runs.

---

## Milestone 3 — Fine-Tuning (OpenAI)

To improve consistency, a 20-example training dataset was created in OpenAI’s JSONL chat format covering all five task types.

**Model:** gpt-3.5-turbo-0125  
**Training examples:** 20  
**Training steps:** 100  
**Fine-tuned model ID:** ft:gpt-3.5-turbo-0125:personal:hr-attrition-m3

When comparing the base model and fine-tuned model on identical prompts, the difference was clear. The base model added generic closing language, while the fine-tuned model followed the structured format reinforced in training.

> **Note on quota:** The fine-tuning job ran successfully the first time. Attempting to re-run it for documentation purposes hit an account-level token quota. All training data, upload steps, job creation, and evaluation code are included in the notebook. The limitation was billing-related, not a code issue.

---

## Milestone 4 — Interactive App (ipywidgets)

The fine-tuned model was wrapped in a simple Jupyter interface using ipywidgets.

The app allows users to:

Select an analysis mode from a dropdown:
  - Summary
  - Recommendations
  - Multi-Department Analysis
  - Scenario Planning
  - Audience Adaptation
Paste structured HR input into a text area
Click **Generate** to receive a formatted response from the fine-tuned model

**Configuration:**
Output capped at 200 tokens
Temperature set to 0.2
3-second cooldown to prevent repeated API calls

---

## Key Takeaways

The base model handled HR reasoning well without fine-tuning. Prompt engineering alone produced usable outputs.
Fine-tuning is less about teaching the model new information and more about enforcing consistent structure and tone.
Quota management is a real constraint when running fine-tuning jobs.
Wrapping the model in a simple UI significantly increases perceived usability, especially for non-technical users.

---

## Files

| File | Description |
|------|------------|
| JRodriguez_DSC670_Milestone3.ipynb | Full notebook covering prompt experiments, fine-tuning pipeline, and interactive app |
| hr_attrition_presentation.pdf | Slide deck summarizing the project |

---

## Tools

Python  
Anthropic API (Claude)  
OpenAI API  
pandas  
ipywidgets  
requests
