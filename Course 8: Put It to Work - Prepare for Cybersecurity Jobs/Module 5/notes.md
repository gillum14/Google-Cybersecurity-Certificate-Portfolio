# Course 8, Module 5 – Use AI to Optimize Workflows

## Overview

This module introduced AI and generative AI fundamentals, the TCREI prompting framework, and responsible AI use, then walked through real-world examples (via a Google cybersecurity professional, Luis) of using gen AI for security frameworks, debugging, code improvement, understanding vulnerabilities, and detection/incident response. It closed with cover letter guidance and technical/non-technical interview preparation.

---

## Learning Objectives

After completing this module, I can:

- Define AI and generative AI, and explain AI's dual role as both a security tool and a target
- Apply the TCREI prompting framework and responsible AI usage guidelines
- Describe real-world gen AI use cases: security frameworks, debugging, code improvement, vulnerabilities, and incident response
- Write a tailored cover letter and prepare for technical and non-technical interviews

---

## Reading: Introduction to AI in Cybersecurity

**Artificial intelligence (AI)** refers to computer programs that complete cognitive tasks typically associated with human intelligence — used to augment/automate tasks like drafting emails/documents, summarizing information, and analyzing data. This module covers foundational AI concepts, tools used in cybersecurity, real-world professional examples, and hands-on practice streamlining tasks with AI.

### The Double-Edged Sword of AI

AI is a powerful ally, but AI systems are also increasingly attractive targets for malicious actors — cybercriminals can use AI to launch more sophisticated attacks, evade detection, and exploit weaknesses. Security professionals need to understand AI's potential for both good and harm, mastering the tools/techniques to secure AI systems while staying ahead of those who'd misuse them.

**Key takeaway:** AI is simultaneously a productivity tool for defenders and a growing attack surface in its own right — both sides matter for a security professional's future.

---

## Reading: Use Generative AI to Work Smarter and Faster

**Generative AI (gen AI)** is AI capable of generating new content (text, images, other media) in response to a **prompt** — input that instructs the AI on what to generate. Examples: Gemini, ChatGPT, Microsoft Copilot.

### Applications for Cybersecurity Professionals

- **Create content:** E.g., generating large sets of fake data to test cybersecurity tools.
- **Analyze information quickly:** E.g., summarizing reports or meeting transcripts for key security details.
- **Answer questions in detail:** E.g., researching common threats like malware and ransomware.
- **Simplify day-to-day work:** E.g., getting an initial analysis of whether an email looks malicious.

### AI's Role in Cybersecurity

AI automates routine tasks (freeing analysts for higher-level work), and assists with understanding complex security frameworks, identifying vulnerabilities, and debugging code.

### The TCREI Prompting Framework

- **Task:** Clearly define what you want the AI to do, including persona (e.g., speechwriter) and output format (e.g., bulleted list, table).
- **Context:** Provide details that help the AI understand the request specifically.
- **References:** Include examples or relevant information to guide accurate output.
- **Evaluate and Iterate:** Assess whether the output meets your needs, then refine the prompt as needed.

### Responsible AI Usage

AI should complement human skills, not replace them — a **human-in-the-loop approach** means always training, using, verifying, and refining AI results with human oversight. Be mindful of what information (especially confidential/sensitive data) you input into AI tools, and verify the accuracy of AI output.

**Key takeaway:** Gen AI tools extend an analyst's efficiency across content creation, analysis, research, and routine tasks — but only when paired with a structured prompting approach (TCREI) and responsible, human-verified use.

---

## Video: AI and NIST Security Frameworks

### The Challenge of Security Frameworks

Frameworks like NIST Special Publication 800-53 are crucial for mitigating risk but are extensive and dense, making specific controls time-consuming to locate and understand.

### How Generative AI Can Help

Tools like Gemini can explain a specific control's (e.g., NIST SI-5) purpose, implementation methods, and potential enhancements — providing detailed prompts with context (e.g., whether an enhancement is mandatory or desirable) yields more tailored responses.

### Optimizing AI for Learning

For a complex topic/control/framework, ask for different explanations (simplified language, analogies) or real-world examples to connect concepts to practical application; voice input can speed up iteration on prompts.

**Key takeaway:** Gen AI can turn a dense, hard-to-navigate framework into a conversational, adjustable-difficulty learning resource — useful for both quick lookups and deeper understanding.

---

## Video: AI for Debugging Code

### The Value of AI in Debugging

AI tools can catch bugs a human programmer might miss, even in code that appears to work correctly — reducing human error and saving significant time versus manual debugging.

### How AI Identifies and Resolves Bugs

AI acts as a code reviewer, identifying edge-case issues (e.g., a zero division error when a user has zero average logins) and proposing solutions, like adding conditional statements to handle errors gracefully.

### Effective Prompting for AI Debugging

Provide precise, structured prompts and avoid excessive context that could distract the AI; always verify AI recommendations and review/adjust suggested changes rather than applying them blindly.

**Key takeaway:** AI is a strong second set of eyes for catching edge-case bugs, but its suggestions still require the same scrutiny an analyst would apply to their own code.

---

## Video: AI for Improving Existing Code

### Enhancing Code with AI

Gen AI tools can add explanatory comments to existing code (helpful for understanding code written by others, or reviewing your own) and suggest concrete improvements with explanations.

### Practical Applications and Benefits

Even analysts new to Python can use AI to understand and improve log analysis scripts written by colleagues — saving time and boosting productivity on both existing code and new programs written from scratch.

**Key takeaway:** Gen AI lowers the barrier to working with unfamiliar code, making it a practical support tool even for analysts still building their Python skills.

---

## Video: AI for Understanding Vulnerabilities

### Understanding Vulnerabilities with Generative AI

Gen AI can define a vulnerability, identify its potential system impact, and suggest immediate mitigation steps — providing context (e.g., identifying yourself as a junior analyst) helps tailor the response to your skill level.

### Iterating and Refining AI Prompts

**Iteration** means refining prompts/outputs through repeated testing and adjustment. Tips: give specific guidance, offer examples, clarify phrasing, and highlight which parts of a prior output you liked.

### Verifying Information and Interview Preparation

Always verify gen AI output against reliable sources, since it can be inaccurate or outdated. Gen AI can also generate sample interview questions about vulnerabilities (with answers) for interview practice.

**Key takeaway:** Gen AI is a strong starting point for understanding vulnerabilities and prepping for related interview questions — but verification against reliable sources remains a non-negotiable step.

---

## Video: AI for Detection and Incident Response

### Gen AI as a Troubleshooting Assistant

Gen AI can help prioritize threats and investigate alerts by reviewing logs — e.g., prioritizing IDS alerts, explaining its reasoning, and suggesting additional considerations like checking for correlations or having a well-defined incident response plan.

### Enhancing Incident Response Plans

Gen AI can help identify appropriate responses/priority for incidents not yet covered in an existing incident response plan, and assist in documenting actions for new alert types or vulnerabilities to keep the plan updated.

**Key takeaway:** Gen AI functions well as a real-time troubleshooting assistant during detection/response — prioritizing alerts, explaining reasoning, and helping keep incident response plans current as new threat types emerge.

---

## Lesson Key Takeaways

- **The growing role of AI:** Understanding AI matters for career success as it becomes more common in the field; AI can help identify risks, automate responses, and prioritize threats; analysts may also be involved in securing AI systems themselves.
- **Generative AI for working smarter/faster:** Use gen AI to create content (e.g., best-practice lists), analyze/summarize information (e.g., security reports), answer common threat questions, and simplify daily tasks (e.g., phishing email triage).
- **Responsible use guidelines:** Review outputs carefully for accuracy/usefulness, disclose your use of gen AI, consider privacy/security implications (avoid entering sensitive information), and apply a human-in-the-loop approach — and always check your company's specific gen AI policies.
- **AI in action:** Real-world applications (via Luis at Google) include understanding/navigating security frameworks, scanning code for errors/vulnerabilities/bottlenecks, suggesting code improvements, describing vulnerabilities and mitigations, and assisting with detection/response tasks like investigating alerts.

**Key takeaway (TCREI mnemonic):** "Thoughtfully Create Really Excellent Inputs" — a memorable way to recall Task, Context, References, Evaluate, and Iterate when prompting gen AI tools.

---

## Video: Crafting Cover Letters

### The Purpose of a Cover Letter

A resume presents facts about your experience; a cover letter reveals your personal story and motivations — a chance to explain your interest in cybersecurity, especially relevant if transitioning careers or if you have a personal connection to cybercrime.

### Crafting Your Cover Letter

Start with a few lines about yourself, then focus on what makes you unique and how you've overcome challenges. If transitioning careers, clearly articulate why cybersecurity excites you and what was missing from previous roles.

### Tailoring Your Cover Letter

Avoid generic cover letters — research the company's mission, purpose, and products, and integrate that research into the letter to show genuine interest.

**Key takeaway:** A cover letter's job is to convey the personal "why" behind a resume's facts — genuine, company-specific tailoring matters more than a polished but generic template.

---

## Video: Technical Interview Preparation for Security Engineer Roles

### Interview Preparation Fundamentals

Interviewers look for understanding of fundamental concepts, not just the ability to answer trivia. Key preparation areas: the functions/purposes/internals of tools like Splunk and Wireshark, and fundamentals in network security, web application security, OS internals, and security protocols.

### Mastering Open-Ended Questions

Start with clarifying questions to narrow ambiguous/complex questions; use the STAR method (Situation, Task, Action, Result) and think aloud so the interviewer can follow your reasoning process.

### Ideal Candidate Qualities

Interviewers value a love of learning, humility, honesty, and the ability to manage ambiguity/complexity — plus resilience, a growth mindset, and qualities of mentorship/leadership.

**Key takeaway:** Technical interviewers are assessing depth of understanding and thought process as much as correct answers — clarifying questions and thinking aloud are as important as technical accuracy.

---

## Reading: Prepare for Technical Interviews

### What Are Technical Interviews?

The main distinction from other interview rounds is a focus on required knowledge of specific tools, beyond the introductory/hiring-manager/panel interviews already covered.

### Python

Python is an important security tool, valued for ease of use and extensive libraries/integrations for automation. You might be asked to whiteboard pseudocode — confidently using Python terminology signals a solid understanding of what it's used for.

### General Techniques

Be ready to discuss security frameworks (e.g., specific NIST frameworks like the CSF) and network security (keeping an organization's network infrastructure secure from unauthorized access). Writing the full question down before answering helps ensure a complete, structured response to multi-part questions.

### Possible Technical Interview Questions

- **What is the TCP/IP model?** A framework used to visualize how data is organized and transmitted across a network.
- **What is the OSI model?** A standardized concept describing the seven layers computers use to communicate and send data over a network.
- **What are SIEM tools and what are they used for?** Security information and event management tools used to identify and analyze security threats, risks, and vulnerabilities.

**Key takeaway:** Even without prior professional security experience, a technical interview is an opportunity to demonstrate certificate-program knowledge and genuine excitement to apply it — preparation and structured answers matter more than having every possible answer memorized.

---

## Video: Technical and Non-Technical Interview Preparation

### Technical Interview Preparation

Focus on networking and information security fundamentals; ask clarifying questions to understand the problem and interviewer's expectations, and if you don't know an answer, say so and explain your approach to figuring it out.

### Non-Technical Interview Preparation

Practice interviews with a friend to identify weak spots; showcase soft skills like teamwork, project leadership, and open-source collaboration, since these are crucial in cybersecurity.

### Advice for Newcomers and Job Seekers

Cultivate curiosity and ask insightful questions even without knowing everything; don't be discouraged by rejection — applying to many jobs before landing one is common, and it's worth applying even if you only meet the minimum qualifications.

**Key takeaway:** Interview readiness spans both technical fundamentals and soft-skill storytelling — and persistence through rejection is a normal, expected part of the job search process, not a sign something's wrong.

---

## Glossary Terms from Module 5

| Term | Definition |
|------|------------|
| AI bias | Risks involved when bias is present in artificial intelligence (AI) data, potentially leading to inaccurate, unfair, or unreliable outputs |
| Artificial intelligence (AI) | Computer programs designed to perform cognitive tasks typically associated with human intelligence, such as learning, problem-solving, and understanding language |
| Context (in prompting) | The necessary details provided to an artificial intelligence (AI) tool to help it understand what you need from it |
| Evaluate (in prompting) | The step in the TCREI framework where you review the output from an artificial intelligence (AI) tool to determine if it meets your needs and expectations |
| Generative AI (Gen AI) | A type of artificial intelligence (AI) that is capable of creating new content, such as text, images, code, or other media, in response to prompts |
| Human-in-the-loop approach | A method of using artificial intelligence (AI) responsibly that combines the strengths of machine intelligence with human oversight, involvement, and validation to train, use, verify, and refine AI results |
| Iterate (in prompting) | The process in the TCREI framework of refining and improving artificial intelligence (AI) prompts and outputs through repeated cycles of testing and adjustments to achieve desired results |
| Prompt | The input (which can be text, images, or other data) you provide to an artificial intelligence (AI) model to elicit a specific response or generate new content |
| References (in prompting) | Examples or specific information provided to an artificial intelligence (AI) tool to use as a guide when creating its output |
| STAR method | A storytelling framework that helps you communicate your experience and skills in a clear, concise, and compelling way to help an interviewer understand exactly how you successfully managed a certain situation; stands for Situation, Task, Action, and Result |
| Task (in prompting) | The specific instruction or goal you give to an artificial intelligence (AI) model, often including details about the desired persona and format for the output |
| TCREI framework | A practical framework for writing effective prompts for generative artificial intelligence (AI) tools, which stands for Task, Context, References, Evaluate, and Iterate |

---

## Course Wrap-Up: Final Course Review

This closing course item reviewed the final course's key themes:

- **Protecting assets and communicating incidents:** Developing a security mindset to protect assets and communicate incidents effectively, plus guidance on when/how to escalate incidents before small issues grow into major problems.
- **Influencing stakeholders and engaging the community:** Communication strategies (visuals, various channels) to influence stakeholder decisions, plus ways to engage with the security community through conferences and networking with other analysts.
- **Job search and interview preparation:** Practical career development — finding, preparing for, and applying to cybersecurity jobs, building compelling resumes, and navigating the interview process.

---

## Personal Reflection

This module reframed AI for me less as a novelty and more as a genuinely practical toolkit — dense frameworks like NIST 800-53 becoming conversational, code getting an extra reviewer, and IDS alerts getting an initial priority pass are all concrete, immediately usable applications rather than abstract hype. The recurring emphasis on verification (checking AI output against reliable sources, reviewing suggested code changes, not entering sensitive data) also landed as the real throughline of the module: AI is a force multiplier for an analyst's judgment, not a replacement for it. Heading into interviews, the "state what you don't know and explain your approach" advice feels like the single most useful, low-stress reframe from this whole course — confidence isn't about having every answer memorized.
