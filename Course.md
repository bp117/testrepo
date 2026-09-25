GenAI Masterclass: From First Prompt to Responsible Enterprise Development
Audience: Fresh college graduates joining the organization
Format: Four classes × 60 minutes, with demonstrations and short hands-on exercises.

Use one running example throughout: build an employee FAQ assistant—start with prompts, develop the code, add enterprise context, and discuss responsible deployment through Tachyon.

Class 1 — GenAI Foundations and Prompt Engineering

Goal: Understand how GenAI works and learn to write clear, testable prompts.

Time	Topic	Coverage / activity

0–10 min	GenAI fundamentals	AI vs. ML vs. GenAI; what an LLM does; prompts, tokens, and outputs; why fluent answers can still be wrong.
10–20 min	Understanding model behavior	Probabilistic responses, hallucinations, knowledge limitations, and the need to verify outputs.
20–35 min	Anatomy of an effective prompt	Task, relevant context, constraints, examples, and output format. Demonstrate a vague prompt and an improved version.
35–45 min	Practical prompting techniques	Zero-shot and few-shot prompting; breaking complex tasks into steps; asking clarifying questions; requesting structured outputs.
45–55 min	Hands-on: improve a prompt	Write a prompt for an employee FAQ assistant that answers from supplied policy text and acknowledges missing information.
55–60 min	Recap and Q&A	A reusable prompt checklist and common mistakes.


Class 2 — AI-Assisted Coding: From Requirement to Reviewed Code

Goal: Use AI throughout development while retaining responsibility for correctness.

Time	Topic	Coverage / activity

0–10 min	Where AI fits in development	Understanding unfamiliar code, planning, generating code, debugging, testing, refactoring, and documentation.
10–20 min	Giving a coding assistant a useful brief	Requirements, acceptance criteria, language/framework, repository conventions, dependencies, and relevant files.
20–35 min	Live demo: build a small feature	Create an FAQ API using a starter project. Move from requirement → implementation plan → code → execution.
35–45 min	Debugging and testing with AI	Use errors and logs effectively; generate meaningful tests; cover edge cases; check whether tests actually validate requirements.
45–55 min	Hands-on: review and repair AI code	Identify a planted bug or unsafe pattern, ask for a focused fix, and verify the resulting diff.
55–60 min	Developer accountability and Q&A	Read before accepting; verify dependencies; protect secrets; follow normal review and release processes.


Class 3 — Context Engineering and Token Economics

Goal: Supply the right information to an AI system and understand the cost of every interaction.

Time	Topic	Coverage / activity

0–10 min	From prompts to context engineering	Prompt engineering shapes instructions; context engineering selects and organizes the information available to the model.
10–25 min	What goes into context	System instructions, user request, conversation history, retrieved documents, tool results, and memory. Context-window limits and conflicting information.
25–35 min	Grounding with enterprise knowledge	RAG basics: retrieve → assemble context → generate → cite. Discuss relevance, freshness, access permissions, and handling missing evidence.
35–45 min	Token economics	Input and output tokens; repeated history; tool results; multi-step calls and retries. Calculate a simple request cost using illustrative rates.
45–55 min	Hands-on: optimize the FAQ assistant	Replace a large document dump with relevant excerpts; limit unnecessary output; compare answer quality, token usage, and latency.
55–60 min	Recap and Q&A	Trade-offs among quality, cost, and latency; introduction to model selection, caching, and context summarization.


Class 4 — Responsible AI and Tachyon Offerings

Goal: Recognize responsible-use boundaries and know how to begin building with the organization’s platform.

Time	Topic	Coverage / activity

0–10 min	AI ethics and accountability	Bias, fairness, transparency, intellectual property, accessibility, and human responsibility for AI-assisted work.
10–20 min	Safe enterprise use	Sensitive data, approved tools, secrets, prompt injection, output validation, and human oversight for consequential decisions.
20–30 min	Scenario discussion	“Can I paste this customer log?” “Can I trust this generated answer?” “Can this agent take an action without approval?” Discuss decisions and escalation paths.
30–40 min	Tachyon offerings: platform tour	Position Tachyon and Higgs.ai; introduce approved model access through AI Bridge, Prompt Studio/chat, ingestion and inference APIs, collections, and relevant access controls.
40–55 min	Live demo: the end-to-end developer journey	Walk through access/use-case onboarding, model experimentation, connecting the FAQ assistant to an approved endpoint, grounding with a collection, and reviewing available usage/evaluation capabilities.
55–60 min	Getting started and Q&A	Where to find internal documentation, starter examples, support channels, and the next learning exercise.


Preparation: Provide a starter repository, synthetic policy documents, approved coding-tool access, and a working Tachyon demo environment. Align the final platform tour with the offerings and access paths currently available to new joiners.
