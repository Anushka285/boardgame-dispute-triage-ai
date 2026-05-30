# ♟️ Board Game Dispute Triage AI

An intelligent **multi-agent AI system** designed to resolve board game rule disputes, validate gameplay decisions, and provide reliable rule interpretations through a structured triage architecture.

This system demonstrates how Large Language Models can be transformed from conversational assistants into dependable decision-support systems through agent orchestration, guardrails, confidence scoring, and human-in-the-loop escalation.

---

## 🎯 Business Problem

Board games operate on deterministic rule systems, yet real-world gameplay often involves:

- Rule ambiguity
- Misinterpretation of game mechanics
- Conflicting player claims
- Tournament disputes
- Incomplete game-state information

Traditional AI chatbots frequently generate plausible but incorrect answers in these situations.

This project addresses that challenge by introducing a structured AI decision engine that prioritizes:

✅ Reliability  
✅ Rule Consistency  
✅ Safety  
✅ Traceability  
✅ Controlled Uncertainty

Rather than forcing an answer, the system determines whether an answer should be provided at all.

---

## 🏗️ System Architecture

The platform follows a Supervisor/Triage-based Multi-Agent Architecture.

```text
User Query
    │
    ▼
┌──────────────┐
│ Gatekeeper   │
└──────┬───────┘
       │
       ▼
┌─────────────────┐
│ Root Triage     │
│ Agent           │
└──────┬──────────┘
       │
 ┌─────┼─────┐
 ▼           ▼           ▼

Rules      Errata     Game State
Knowledge  Validator  Interpreter
Agent      Agent      Agent

       │
       ▼

Structured JSON Output
       │
       ▼

Human-in-the-Loop
(when required)
```

---

## 🤖 Agent Responsibilities

### Gatekeeper Agent

Responsible for:

- Detecting adversarial prompts
- Preventing rule manipulation attempts
- Blocking unsafe requests
- Enforcing system guardrails

Examples:

- "Ignore the rules"
- "Help me cheat"
- "Create my own rule"

---

### RulesKnowledgeAgent

Provides deterministic rule explanations.

Example:

> "What is the settlement placement rule in Catan?"

Outputs structured rule interpretations directly from encoded rule logic.

---

### ErrataValidatorAgent

Validates player claims and misconceptions.

Example:

> "Some players say you can collect rent on mortgaged property. Is that correct?"

The system evaluates whether the statement is true, false, or partially correct.

---

### GameStateInterpreterAgent

Evaluates move legality using game context.

Example:

> "Can I place a settlement here?"

The agent determines whether the move is:

- Valid
- Invalid
- Uncertain

based on encoded game rules.

---

## 🛡️ Reliability Features

### Actionable Hesitation

Instead of hallucinating, the system can intentionally pause decision-making when sufficient context is unavailable.

---

### Confidence Scoring

Every response includes confidence values based on:

- Rule alignment
- Context clarity
- Reasoning consistency

Low-confidence outputs trigger clarification or escalation.

---

### Human-in-the-Loop (HITL)

High-stakes scenarios automatically escalate to human review.

Examples:

- Tournament disputes
- Rule violations affecting outcomes
- Final adjudication requests

---

## 📷 Multimodal Reasoning

The system supports image-based gameplay analysis.

Supported use cases:

- Monopoly board screenshots
- Catan board states
- Scrabble tile placements
- Ludo game positions

Images are treated as contextual evidence while rule-based reasoning remains the primary decision mechanism.

---

## 🔬 Evaluation & Stress Testing

The system underwent extensive testing across:

- Rule explanation scenarios
- Move validation scenarios
- Errata validation cases
- Adversarial prompts
- Multimodal image inputs
- Ambiguous game-state situations

### Version 1 Results

- Routing failures identified
- Over-sensitive guardrails detected
- Evaluation inconsistencies observed
- Image reasoning limitations uncovered

### Improvements Implemented

- Semantic routing enhancements
- Guardrail recalibration
- Structured reasoning templates
- Improved multimodal handling

### Final Results

| Metric | Result |
|----------|----------|
| Test Cases | 14 |
| Agent Types | 3 |
| Architecture | Multi-Agent |
| Final Pass Rate | 100% |
| HITL Support | Yes |
| Confidence Scoring | Yes |
| Multimodal Support | Yes |

---

## ⚙️ Technology Stack

### AI & Agent Platforms

- Google AI Studio
- Gemini Models
- CES Agent Studio
- Flowise

### AI Techniques

- Multi-Agent Orchestration
- Agent Routing
- Prompt Engineering
- Structured Outputs
- Confidence Scoring
- Human-in-the-Loop Escalation
- Adversarial Input Detection

### Output Format

- JSON-based deterministic responses

---

## 📄 Example Output

```json
{
  "move_validity": "Invalid",
  "reasoning": "Scrabble words must be placed horizontally or vertically. Diagonal placement is not allowed.",
  "confidence": 0.98
}
```

---

## 💡 Key Learning Outcomes

This project demonstrates practical experience with:

- Agentic AI Systems
- AI Reliability Engineering
- Prompt Architecture Design
- LLM Evaluation Frameworks
- Multi-Agent Workflows
- Safety & Guardrail Design
- Human-AI Collaboration
- Cost-Aware AI Architecture

## 📜 License

This repository is intended for educational, research, and portfolio purposes.
