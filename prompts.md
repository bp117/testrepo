Here are **5 hands-on playground exercises** designed to practice the core concepts from the slide deck. Each exercise provides a **Bad/Naive Prompt** (to observe how the model fails in the playground) and a **Rebuilt Efficient Prompt** using the frameworks and techniques from the session.

---

### **Exercise 1: Grounding & Preventing Hallucinations (The 'Riding Hood' Rule)**
* **Target Concept**: Preventing the model from walking into the "Dark Forest" of invented facts when context is missing.
* **Playground Setup**: Open your LLM chat interface (ChatGPT, Claude, Gemini, or Chatbot Arena).

#### ❌ **Step 1: Test the Naive Prompt (Watch it Fail)**
```markdown
Write an FAQ answer explaining our company's remote work stipend policy for home office furniture.
```
* **What Happens**: Because the model is an eager pattern-completion engine with complete amnesia, it invents a plausible dollar amount (e.g., "\$500 allowance") to fill the void.

#### ✅ **Step 2: Rebuild using the CLEAR / RTC-CF Framework**
Apply **Context**, **Limitations**, **Audience**, and **Role**:
```markdown
[ROLE] You are an HR Policy Assistant.
[TASK] Answer the employee question below about home office reimbursements.
[CONTEXT]
Company Policy Text:
- Employees may work remotely up to 2 days per week with manager approval.
- Home internet stipend is $50/month.
- Equipment requests must be submitted 14 days in advance.

[CONSTRAINTS / LIMITATIONS]
1. Answer using ONLY the policy text above.
2. If the answer is NOT in the text, reply EXACTLY: "I cannot find this in our policy text. Please contact hr@company.com." Do NOT guess or use outside knowledge.
3. Maximum 2 sentences.

[QUESTION] Can I get reimbursed for an ergonomic office chair?
```
* **Key Takeaway**: The model correctly triggers the fallback constraint instead of hallucinating.

---

### **Exercise 2: Few-Shot Pattern Anchoring (Show, Don't Tell)**
* **Target Concept**: Anchoring tone and enforcing strict output structure using examples rather than a paragraph of adjectives.

#### ❌ **Step 1: Test the Zero-Shot Prompt**
```markdown
Classify this customer review into sentiment and category. Make it professional, concise, clean, and nicely formatted.

Review: "The app crashes every time I tap on my monthly invoice."
```
* **What Happens**: The model generates conversational fluff ("Sure! Here is your classification...") and inconsistent layout.

#### ✅ **Step 2: Rebuild using Few-Shot Prompting**
```markdown
Classify customer reviews into JSON format. Follow these exact input/output patterns:

Input: "The dashboard loads super fast now!"
Output: {"sentiment": "Positive", "category": "Performance"}

Input: "I was billed twice for my subscription this month."
Output: {"sentiment": "Negative", "category": "Billing"}

Input: "The app crashes every time I tap on my monthly invoice."
Output:
```
* **Key Takeaway**: Implicit examples anchor the model's predictions faster and eliminate conversational filler.

---

### **Exercise 3: The Internal Monologue (Chain-of-Thought)**
* **Target Concept**: Giving the AI a "thought budget" to prevent instant guessing on multi-step logic.

#### ❌ **Step 1: Test the Overloaded Single Prompt**
```markdown
We had 1,200 active users in Q1 and 1,450 in Q2. In Q3, user count dropped by 12% compared to Q2. Did Q3 perform better or worse than Q1 in absolute numbers? Answer immediately.
```
* **What Happens**: Models often rush the math calculation and guess incorrectly.

#### ✅ **Step 2: Rebuild with Step-by-Step Reasoning**
```markdown
[TASK] Compare Q3 active users against Q1 active users.

[DATA]
- Q1: 1,200 users
- Q2: 1,450 users
- Q3: 12% drop from Q2

[INSTRUCTION] Think step-by-step before providing your final answer:
1. Calculate Q3 user count (1,450 minus 12%).
2. Compare Q3 user count directly to Q1 user count (1,200).
3. State whether Q3 was higher or lower, and by how many users.
```
* **Key Takeaway**: Forcing an internal monologue dramatically reduces logical and arithmetic errors.

---

### **Exercise 4: The Sandwich Technique for Long Documents**
* **Target Concept**: Overcoming the "Valley of Meh" where the model forgets instructions placed in the middle of long contexts.

#### ❌ **Step 1: Test Middle-Weighted Context**
```markdown
Summarize the key compliance risks in 3 bullet points.

[PASTE 10 PAGES OF A LEGAL REPORT OR POLICY DOCUMENT HERE]
```
* **What Happens**: The model pays attention to the start and end, but misses critical details buried in the middle.

#### ✅ **Step 2: Rebuild with Top and Bottom Buns**
```markdown
TOP BUN (Main Role & Instruction):
You are a Legal Compliance Auditor. Extract compliance risks from the report below.

MEAT (Context Document):
[PASTE YOUR 10 PAGES OF TEXT HERE]

BOTTOM BUN (Crucial Refocusing):
REMINDER: Extract exactly 3 compliance risks from the document above. Format as Markdown bullet points with a strict 20-word limit per bullet.
```
* **Key Takeaway**: Placing critical constraints at the bottom refocuses the model right before token generation begins.

---

### **Exercise 5: The Multi-Turn Iteration Loop (Draft → Critique → Refine)**
* **Target Concept**: Treating prompting as a 3-step conversation rather than expecting a perfect result in a single pass.

#### 🔄 **Execute the 3-Pass Workflow in the Same Thread**:

1. **Pass 1 (The Table Read)**:
   > `"Draft a 150-word announcement email introducing our new AI governance framework to the engineering team."`
2. **Pass 2 (The Notes Session / Self-Audit)**:
   > `"Audit your draft above. Flag any claims or technical terms that might sound vague, overly authoritative, or confusing to a junior developer."`
3. **Pass 3 (Take Two / Refine)**:
   > `"Rewrite the email addressing those exact flags. Keep the tone warm, collaborative, and concise."`

* **Key Takeaway**: Three fast iterations in the same chat thread consistently outperform a massive, overly complicated single prompt.

---

🛠️ Would you like to turn these 5 playground exercises into a downloadable attendee worksheet, or add an automated grading rubric to your quiz artifact?
