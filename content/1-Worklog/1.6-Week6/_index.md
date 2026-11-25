---
title: "Week 6 Worklog"
date: 2026-10-19
weight: 1
chapter: false
pre: " <b> 1.6. </b> "
---
### Week 6 Objectives:

- Design system prompt and context rules for the chatbot.
- Design data schema for the legal knowledge base.
- Prepare a sample question set to test answer quality.

### Tasks to be implemented this week:

| Day | Task | Start Date | Completion Date | Reference Source |
| --- | --------- | ------------ | --------------- | -------------- |
| 2 | Read the structure of Decree 13/2023/ND-CP. Select key articles: personal data, consent, data subject rights, marketing, handling of violations. | 19/10/2026 | 19/10/2026 |  |
| 3 | Create a Groq account and API key, get familiar with Playground. Write a system prompt by role: answer in Vietnamese, cite legal articles, include a disclaimer. | 20/10/2026 | 20/10/2026 | Groq Docs |
| 4 | Add constraints to answer only based on provided context and fallback responses when lacking legal basis. Test with out-of-scope questions (for example about taxes). | 21/10/2026 | 21/10/2026 | Groq Docs |
| 5 | Design the LegalArticles table schema including id, law_name, article_number, content, keywords. Define how to assemble prompts: system prompt + legal context + question, limiting number of articles and length. | 22/10/2026 | 22/10/2026 | AWS Docs: DynamoDB |
| 6 | Draft a sample question set including in-scope questions, out-of-scope questions, and real-world scenario questions, then test on Playground. Edit and finalize the prompt template. | 23/10/2026 | 23/10/2026 | Groq Docs |

### Achieved results of Week 6:

- Understood the main structure of Decree 13/2023 and selected articles to include in the chatbot.
- Wrote the system prompt and context constraints, with fallback responses.
- Completed designing the LegalArticles schema and prompt assembly method.
- Had a sample question set for subsequent testing rounds.