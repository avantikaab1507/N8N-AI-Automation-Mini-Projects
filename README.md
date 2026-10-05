# N8N AI Automation Mini Projects

A collection of mini AI and automation workflows built with **n8n** and **Google Gemini**, covering workflow automation, AI-powered text processing, intelligent classification, and agent-based student assistance.

These projects were developed as part of my **Semester 5 RPA / Agentic AI PEP training** to gain practical experience in building AI-powered workflows using n8n.

---

## 📌 Projects Included

### 1. Student Marks Evaluation Workflow

A simple automation workflow that evaluates a student's mark and determines whether the student has passed or failed.

**Workflow:**

`Manual Trigger → Edit Fields → IF Condition → PASS / FAIL`

**How it works:**

- Accepts a student name and mark as input.
- Checks whether the mark is greater than or equal to 40.
- Routes the input through an IF condition.
- Returns `PASS` when the mark is 40 or above.
- Returns `FAIL` when the mark is below 40.

**Concepts practiced:**

- Workflow triggers
- Data input using Edit Fields
- Conditional branching
- IF node
- Workflow outputs

---

### 2. AI Paragraph Summarizer

An AI-powered workflow that uses **Google Gemini** to summarize a paragraph into exactly three concise bullet points.

**Workflow:**

`Manual Trigger → Edit Fields → Basic LLM Chain → Google Gemini`

**How it works:**

- Accepts a paragraph as input.
- Sends the paragraph to a Basic LLM Chain.
- Uses the Gemini 2.5 Flash model to process the text.
- Instructs the model to return exactly three concise bullet points.
- Prevents unnecessary introductions, conclusions, and numbering.

**Concepts practiced:**

- LLM-based text processing
- Prompt engineering
- Google Gemini integration
- Structured AI output
- n8n expressions

---

### 3. AI Support Ticket Classifier

An AI-powered workflow that automatically classifies customer complaints into predefined categories.

**Categories:**

- Billing
- Technical
- Sales

**Workflow:**

`Manual Trigger → Edit Fields → Basic LLM Chain → Switch → Category Output`

**How it works:**

- Accepts a customer complaint as input.
- Uses Google Gemini to classify the complaint.
- The AI returns one of the predefined categories.
- A Switch node routes the result to the corresponding category.

**Example classifications:**

- Duplicate payment or incorrect charge → `Billing`
- Application crash or login issue → `Technical`
- Pricing or premium plan enquiry → `Sales`

**Concepts practiced:**

- AI-based classification
- Prompt engineering
- Switch-based routing
- Conditional workflow logic
- AI + automation integration

---

### 4. Student Helpdesk AI Agent

A simple AI agent designed to answer common student helpdesk questions using a controlled set of information.

**Workflow:**

`Manual Trigger → Edit Fields → AI Agent → Google Gemini Chat Model`

**How it works:**

- Accepts a student question.
- Passes the question to an AI Agent.
- The agent uses a defined student helpdesk knowledge base.
- The system prompt restricts the agent to the provided information.
- If the requested information is unavailable, the agent provides a predefined fallback response.

**Example questions:**

- What time does the Python class start?
- What is the attendance requirement?
- Who should I contact for certificate issues?

**Concepts practiced:**

- AI agents
- System prompts
- Controlled knowledge
- Fallback handling
- Google Gemini integration
- n8n AI Agent node

---

## 🏗️ Workflow Architecture

The four workflows demonstrate different levels of automation and AI integration:

| Project                      | Main Concept           | AI Used       | Automation Logic   |
| ---------------------------- | ---------------------- | ------------- | ------------------ |
| Student Marks Evaluation     | Conditional automation | No            | IF condition       |
| AI Paragraph Summarizer      | AI text processing     | Google Gemini | LLM Chain          |
| AI Support Ticket Classifier | AI classification      | Google Gemini | LLM Chain + Switch |
| Student Helpdesk AI Agent    | AI agent               | Google Gemini | AI Agent           |

Together, these workflows demonstrate how traditional automation logic can be combined with AI capabilities to build practical intelligent workflows.

---

## 🤖 AI Integration

The AI-powered workflows use **Google Gemini 2.5 Flash** through n8n's AI nodes.

### AI Paragraph Summarizer

The Gemini model is instructed to:

- Produce exactly 3 bullet points
- Include one important idea per bullet
- Avoid introductions and conclusions
- Avoid numbering
- Keep the output clear and concise

### AI Support Ticket Classifier

The Gemini model is instructed to classify complaints into:

- Billing
- Technical
- Sales

The classification result is then used by the Switch node for routing.

### Student Helpdesk AI Agent

The AI Agent uses a system message containing predefined student helpdesk information.

The agent is instructed to:

- Use only the provided information
- Avoid guessing or inventing information
- Give clear and concise answers
- Use a predefined fallback response when information is unavailable

This demonstrates the use of **controlled AI behavior and fallback handling**.

---

## 🧪 Testing

Each workflow was manually executed and tested in n8n.

### Student Marks Evaluation

Test cases included:

- Mark = 78 → `PASS`
- Mark = 35 → `FAIL`

The workflow correctly routed the student based on the IF condition.

### AI Paragraph Summarizer

The workflow was tested with an educational paragraph about artificial intelligence in education.

The Gemini model successfully generated **exactly 3 concise bullet points** according to the prompt instructions.

### AI Support Ticket Classifier

Test cases included:

| Complaint                          | Expected Category | Result       |
| ---------------------------------- | ----------------- | ------------ |
| Duplicate charge                   | Billing           | ✅ Billing   |
| Application crashing / login issue | Technical         | ✅ Technical |
| Premium plan / pricing enquiry     | Sales             | ✅ Sales     |

### Student Helpdesk AI Agent

Test cases included:

| Question                        | Result                          |
| ------------------------------- | ------------------------------- |
| Python class timing             | ✅ Correct answer               |
| Attendance requirement          | ✅ Correct answer               |
| Certificate-related issue       | ✅ Correct answer               |
| Unknown Java timetable question | ✅ Controlled fallback response |

The unknown-question test demonstrated that the agent does not simply invent an answer when the information is unavailable.

---

## 🔄 Key Workflow Concepts Learned

Through these projects, I practiced:

- n8n workflow creation
- Manual triggers
- Edit Fields node
- IF conditions
- Switch-based routing
- Basic LLM Chain
- AI Agent
- Google Gemini integration
- Prompt engineering
- n8n expressions
- Structured AI outputs
- Controlled AI responses
- Fallback handling
- Workflow testing and debugging

---

## 🛠️ Technologies Used

- **n8n** – Workflow automation and AI orchestration
- **Google Gemini 2.5 Flash** – Large language model for AI-powered workflows
- **n8n AI Nodes** – Basic LLM Chain and AI Agent
- **Conditional Logic** – IF and Switch nodes
- **JSON** – Workflow export and sharing format

---

## 🔐 Credentials & Security

The workflow files included in this repository have been prepared for public sharing.

- No API keys are included.
- No passwords or authentication tokens are included.
- No private URLs are included.
- n8n credential references have been sanitized.
- Personal information has been removed from sample workflow inputs.
- n8n instance-specific identifiers have been removed from the workflows where applicable.

The JSON files are intended to demonstrate workflow structure and configuration without exposing private credentials.

---

## 📂 Repository Structure

```text
N8N-AI-Automation-Mini-Projects/
│
├── README.md
│
├── 01-student-marks-evaluation/
│   └── student-marks-evaluation.json
│
├── 02-ai-paragraph-summarizer/
│   └── ai-paragraph-summarizer.json
│
├── 03-ai-support-ticket-classifier/
│   └── ai-support-ticket-classifier.json
│
└── 04-student-helpdesk-ai-agent/
    └── student-helpdesk-ai-agent.json
```

---

## 🚀 Future Enhancements

Possible future extensions for these workflows include:

- Connecting workflows to external APIs and real-time data sources
- Adding database integration for storing and retrieving information
- Replacing manual triggers with event-based or scheduled triggers
- Adding email or messaging notifications
- Expanding the Student Helpdesk Agent with a larger knowledge base
- Integrating additional AI agents and tools
- Building more advanced multi-step AI automation workflows
- Connecting AI workflows with external applications and services

---

## 📄 Note

These projects were developed as hands-on learning exercises during Semester 5 RPA / Agentic AI PEP training to explore practical applications of n8n and AI-powered automation.
