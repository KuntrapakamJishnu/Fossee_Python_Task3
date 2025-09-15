# Python Screening Task 3: Evaluating Open Source Models for Student Competence Analysis

This repository contains the submission for the Python Screening Task focused on proposing a research plan for evaluating open-source AI models for student competence analysis.

## Setup Instructions

This submission is composed of a research plan and detailed reasoning, both contained within this `README.md` file. No special setup or installation is required to view the content.

---

## Research Plan

My approach to evaluating open-source models for student competence analysis begins with establishing clear criteria: **code comprehension** (ability to parse syntax, logic, and intent), **pedagogical value of generated prompts** (capacity to foster critical thinking without revealing solutions), and **technical feasibility** (model size, inference speed, and ease of fine-tuning). The initial search will focus on models hosted on platforms like Hugging Face, prioritizing those with strong foundations in code, such as Meta's **`CodeLlama`** or Google's **`Gemma`**, as well as generalist models known for strong reasoning like **`Mistral-7B`**. I will select one primary candidate, likely `CodeLlama`, due to its specialized training on code, which is highly relevant to this use case.

Validation will be conducted by creating a small, curated dataset of Python code snippets from beginner students, categorized by common misconceptions (e.g., mutable default arguments, variable scope confusion, incorrect loop logic). I will then use this dataset to perform a qualitative benchmark on the chosen model. The test will involve prompting the model with the student's code and a meta-prompt such as, *"This Python code is incorrect. Identify the student's conceptual misunderstanding and ask them a single, guiding question to help them find the error themselves."* The generated prompts will be evaluated against a rubric measuring their clarity, relevance, and effectiveness in stimulating self-correction, which will determine the model's out-of-the-box suitability and inform the potential need for fine-tuning.

---

## Reasoning

#### 1. What makes a model suitable for high-level competence analysis?

A model is suitable for high-level competence analysis if it moves beyond simple syntax checking to achieve **semantic and conceptual understanding**. This means the model must:
* **Infer Intent:** It should be able to understand what the student was *trying* to accomplish, not just what the code *does*. This is key to identifying logical flaws versus simple typos.
* **Model Misconceptions:** It needs to recognize common patterns of error that point to a deeper misunderstanding of a core concept (e.g., confusing class variables with instance variables).
* **Generate Socratic Prompts:** Instead of providing a direct correction, the model must be capable of generating open-ended, guiding questions that encourage the student to re-evaluate their own logic. This requires strong instruction-following and nuanced language generation abilities.

#### 2. How would you test whether a model generates meaningful prompts?

I would test the meaningfulness of generated prompts through a multi-faceted evaluation:
* **Expert Review:** A panel of experienced Python educators would score the prompts based on a pedagogical rubric. Criteria would include: Does the prompt accurately target the misconception? Does it encourage critical thinking? Is the language clear and encouraging?
* **Comparative Analysis:** I would compare the model-generated prompts against "gold standard" prompts written by human instructors for the same code snippets.
* **Student Interaction Testing:** In a controlled setting, I would present the AI-generated feedback to a small group of students to measure its practical effectiveness. Qualitative feedback would be gathered on whether the prompts were helpful, confusing, or frustrating, providing direct insight into their real-world value.

#### 3. What trade-offs might exist between accuracy, interpretability, and cost?

Significant trade-offs exist between these three factors:
* **Accuracy vs. Cost:** Larger, more powerful models (e.g., 70B parameter models) generally provide more accurate and nuanced analysis but come with high computational costs (requiring expensive GPUs and more energy). Smaller models are cheaper to run but may oversimplify problems or make more frequent errors.
* **Accuracy vs. Interpretability:** The most accurate models are often complex "black boxes," making it difficult to understand *why* they generated a specific prompt. For an educational tool, this is a major drawback, as educators may need to trust and understand the AI's reasoning. A simpler, more interpretable model might be preferred even if it's slightly less accurate.

#### 4. Why did you choose the model you evaluated, and what are its strengths or limitations?

For this plan, I chose **`CodeLlama`** as the primary model for evaluation.

* **Reasoning for Choice:** `CodeLlama` is built upon Llama 2 and specifically pre-trained on a vast corpus of code. This domain-specific training makes it an exceptionally strong candidate for a task centered on analyzing student-written Python code. It is also open source and available in various sizes, allowing for scalability.

* **Strengths:**
    * **Code-Specific Knowledge:** It has a built-in, deep understanding of programming syntax, idioms, and common patterns across multiple languages, including Python.
    * **Instruction-Tuned Variants:** The `CodeLlama-Instruct` models are fine-tuned to follow user commands, which is crucial for the task of generating very specific types of guiding questions.
    * **Accessibility:** The smaller 7B parameter version can be run on consumer-grade hardware, making it highly accessible for research, prototyping, and even deployment in resource-constrained environments.

* **Limitations:**
    * **Lack of Pedagogical Context:** `CodeLlama` understands code, but it doesn't inherently understand *how students learn*. Without specific fine-tuning on educational dialogues, its prompts might be technically correct but pedagogically ineffective or even confusing.
    * **Risk of "Over-Helping":** The model might default to providing solutions or overly explicit hints rather than genuinely Socratic questions, defeating the purpose of fostering deeper learning. This requires careful and sophisticated prompt engineering to mitigate.
