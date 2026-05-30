# 🧠 Board Game Triage AI System

A **multi-agent AI system** designed to resolve rule ambiguity and gameplay disputes in board games such as **Catan, Monopoly, Scrabble, and Ludo**.

This project was developed as part of the **BCIS 5910 Capstone Project**, focusing on transitioning from *“chatting with AI”* to *engineering a reliable AI system*.

---

## 🚀 Project Overview

Board games operate on structured rule systems, yet real-world gameplay often involves ambiguity, disagreements, and inconsistent interpretations. Traditional AI systems struggle in this domain due to their tendency to generate plausible but incorrect responses.

This system addresses that problem by acting as a **rule-based control mechanism**, ensuring:

- Consistent rule enforcement  
- Accurate validation of claims  
- Reliable move evaluation  
- Safe handling of adversarial inputs  

---

## 🏗️ System Architecture

The system is built using a **Supervisor/Triage architecture** with multiple specialized agents:

- **Gatekeeper** → Filters unsafe/adversarial queries  
- **Root Triage Agent** → Classifies query intent  
- **RulesKnowledgeAgent** → Explains official rules  
- **ErrataValidatorAgent** → Validates claims & detects misinformation  
- **GameStateInterpreterAgent** → Evaluates move validity  
- **Human-in-the-Loop (HITL)** → Escalates high-stakes decisions  

---

## 🔄 How It Works

1. User submits a query  
2. Gatekeeper checks for violations  
3. Triage agent routes the query  
4. Specialized agent processes the request  
5. System returns structured JSON output  

---

## 📊 Example Output

```json
{
  "move_validity": "Invalid",
  "reasoning": "In Scrabble, words must be placed horizontally or vertically. Diagonal placement is not allowed.",
  "confidence": 1.0
}
