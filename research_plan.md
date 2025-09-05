# Task 3: Research Plan — Evaluating Open Source Models for Student Competence Analysis

## 📌 Research Plan (2 Paragraphs)

**Paragraph 1 — Approach to identifying & evaluating relevant models**  
I will begin by surveying openly available large language models (LLMs) and code-specialized models that can analyze Python programs. Priority will be given to models with permissive licenses (e.g., Apache 2.0, MIT), proven code-understanding benchmarks, and availability on Hugging Face or other open repositories. Candidate models include **StarCoder (BigCode)**, **Code Llama (Meta)**, and **Falcon**. The evaluation criteria will include: (1) ability to parse and reason about student Python code, (2) strengths in generating non-revealing prompts, and (3) practicality of deployment in an educational setting (cost, resources, licensing).  

**Paragraph 2 — Testing & validation of applicability**  
To validate applicability, I will create a small test set of Python student submissions representing common mistakes (off-by-one errors, uninitialized variables, misuse of loops, conceptual gaps in recursion, etc.). For each model, I will prompt it to: (a) analyze the student’s code and highlight likely misconceptions, (b) generate one or two probing questions that assess conceptual understanding, and (c) encourage exploration without providing direct solutions. Model outputs will be evaluated along dimensions of *clarity, pedagogical usefulness, and non-revealing guidance*, using both automated checks (relevance, code context) and human ratings (instructor judgment). This will allow me to systematically assess which model provides the most educationally useful prompts.

---

## 📌 Reasoning (Required)

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

---

## 📎 References
- StarCoder: [https://huggingface.co/bigcode/starcoder](https://huggingface.co/bigcode/starcoder)  
- Code Llama: [https://huggingface.co/meta-llama](https://huggingface.co/meta-llama)  
- Falcon: [https://huggingface.co/tiiuae](https://huggingface.co/tiiuae)  
