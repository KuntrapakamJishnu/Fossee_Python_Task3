# Task 3: Research Plan — Evaluating Open Source Models for Student Competence Analysis

## Research Plan (2 Paragraphs)

**Paragraph 1 — Approach to identifying & evaluating relevant models**  
I will begin by surveying openly available large language models (LLMs) and code-specialized models that can analyze Python programs. Priority will be given to models with permissive licenses (e.g., Apache 2.0, MIT), proven code-understanding benchmarks, and availability on Hugging Face or other open repositories. Candidate models include **StarCoder (BigCode)**, **Code Llama (Meta)**, and **Falcon**. The evaluation criteria will include: (1) ability to parse and reason about student Python code, (2) strengths in generating non-revealing prompts, and (3) practicality of deployment in an educational setting (cost, resources, licensing).  

**Paragraph 2 — Testing & validation of applicability**  
To validate applicability, I will create a small test set of Python student submissions representing common mistakes (off-by-one errors, uninitialized variables, misuse of loops, conceptual gaps in recursion, etc.). For each model, I will prompt it to: (a) analyze the student’s code and highlight likely misconceptions, (b) generate one or two probing questions that assess conceptual understanding, and (c) encourage exploration without providing direct solutions. Model outputs will be evaluated along dimensions of *clarity, pedagogical usefulness, and non-revealing guidance*, using both automated checks (relevance, code context) and human ratings (instructor judgment). This will allow me to systematically assess which model provides the most educationally useful prompts.

---

## Reasoning (Required)

### 1. What makes a model suitable for high-level competence analysis?
A suitable model must combine **strong code understanding** (syntax + semantics) with **instruction-following** abilities to generate non-revealing guidance. It should handle large code contexts, follow safety constraints, and run under licenses that permit educational deployment.

### 2. How would you test whether a model generates meaningful prompts?
By evaluating outputs against an annotated dataset:  
- **Automated tests:** check if prompts reference relevant parts of the code.  
- **Human scoring:** teachers rate clarity, depth, and whether the prompt encourages thinking without giving solutions.  
- **Iterative refinement:** use multiple prompt styles to see which yields consistent, meaningful feedback.

### 3. What trade-offs might exist between accuracy, interpretability, and cost?
- Larger models (higher accuracy) may be costly to run and harder to interpret.  
- Smaller models are cheaper and more transparent but may miss deeper reasoning.  
- Deploying open-source locally protects privacy but requires more hardware, while cloud APIs are easier but less private.

### 4. Why did you choose the model you evaluated, and what are its strengths or limitations?
I chose **StarCoder** for evaluation because it is openly available, well-documented, and designed for code tasks.  
- **Strengths:** robust code reasoning, permissive license, strong community support.  
- **Limitations:** prone to hallucinations, requires significant compute to run efficiently, and may still miss subtle pedagogical nuances.
Of course! Here is that research plan rewritten to sound more natural and human.

***

### My Plan for Finding the Right AI to Help Student Coders

#### The Plan

My first step is to survey the field of open-source language models to find ones that are good at analyzing Python code. I'll focus on models with permissive licenses (like Apache 2.0 or MIT) that are known for their coding abilities and are readily available on platforms like Hugging Face. The main candidates I have in mind are **StarCoder**, **Code Llama**, and **Falcon**. My evaluation will focus on three key questions: Can it actually understand and reason about student code? Is it good at generating helpful hints that don't give away the solution? And is it practical for a school to actually use (thinking about cost, hardware, and licensing)?

To see if a model is truly a good fit, I'll create a small test set of real Python code submitted by students. This set will include common beginner mistakes like off-by-one errors, using uninitialized variables, messy loops, and conceptual problems with things like recursion. For each model, I’ll prompt it to analyze the code, identify the likely misunderstanding, and then generate a couple of probing questions to guide the student toward the right answer without just handing it to them. I’ll judge the results based on their clarity and how useful they are from a teaching perspective. This will involve some automated checks, but the most important feedback will come from human instructors who will rate the quality of the AI's guidance. This process will help me see which model provides the most educationally valuable support.

---

#### My Reasoning

**1. What makes a model suitable for this kind of high-level analysis?**

A good model needs to do two things really well: it has to deeply understand code (both syntax and what the student was *trying* to do), and it has to be great at following specific instructions, especially the instruction to *not* reveal the answer. Beyond that, it needs to be practical—it should handle a decent amount of code, respect safety guidelines, and have a license that allows it to be used in an educational setting without legal headaches.

**2. How would you test if a model is generating meaningful prompts?**

I'd test the quality of the prompts in a few ways:
* **Automated Checks:** First, a simple check to see if the prompt is even referencing the right part of the student's code.
* **Human Scoring:** This is the most important part. I’d have experienced teachers rate the AI's questions on a simple scale: Is it clear? Does it encourage deep thinking? Does it successfully avoid giving away the solution?
* **Iterative Testing:** I’d also experiment with different ways of asking the model for feedback to see which style of prompt gets the most consistent and helpful results.

**3. What are the trade-offs between accuracy, interpretability, and cost?**

It's the classic balancing act.
* Bigger models are generally "smarter" and more accurate, but they can be very expensive to run and are often "black boxes," making it hard to understand their reasoning.
* Smaller models are cheaper, faster, and easier to understand, but they might miss the mark on more complex logical errors in the code.
* There's also the choice of running the model yourself, which is great for privacy but requires powerful hardware, versus using a cloud API, which is easier but means sending student data to a third party.

**4. Why did you choose StarCoder for this evaluation? What are its strengths and limitations?**

I chose **StarCoder** as the initial model for this plan because it’s open, well-documented, and was specifically designed for code-related tasks.

* **Strengths:** It’s known for strong code analysis, has a permissive license that’s great for our purposes, and is backed by a strong community.
* **Limitations:** Like many models, it can sometimes "hallucinate" or make things up. It also requires a good amount of computing power to run well. Most importantly, while it’s great with code, it might not grasp the subtle pedagogical nuances needed to be a truly effective teaching tool without specific fine-tuning.
---

## 📎 References
- StarCoder: [https://huggingface.co/bigcode/starcoder](https://huggingface.co/bigcode/starcoder)  
- Code Llama: [https://huggingface.co/meta-llama](https://huggingface.co/meta-llama)  
- Falcon: [https://huggingface.co/tiiuae](https://huggingface.co/tiiuae)  
