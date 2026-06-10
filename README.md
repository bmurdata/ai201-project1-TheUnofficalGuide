# The Unofficial Guide — Project 1

> **How to use this template:**
> Complete each section *after* you've built and tested the corresponding part of your system.
> Do not write placeholder text — if a section isn't done yet, leave it blank and come back.
> Every section below is required for submission. One-liners will not receive full credit.

---

## Domain

<!-- What topic or category of knowledge does your system cover?
     Why is this knowledge valuable, and why is it hard to find through official channels?
     Example: "Student reviews of CS professors at [university] — useful because official
     course descriptions don't reflect teaching style, exam difficulty, or workload." -->
     Civil Service pathways for internships or full time jobs. Students oftne do not know steps or requirements, and there are normal interns and civil service title ones that make it complicated. A system to generalize options and value would be of value.

---

## Document Sources

<!-- List every source you collected documents from.
     Be specific: include URLs, subreddit names, forum thread titles, or file names.
     Aim for variety — sources that together cover different subtopics or perspectives. -->

| # | Source | Type | URL or file path |
|---|--------|------|-----------------|
| 1 | NYC Government |Website |https://www.nyc.gov/site/dcas/employment/urban-fellows-program-information.page |
| 2 | NYC Government | Website-general information |https://www.nyc.gov/site/dcas/employment/internship-and-fellowships-civil-service-pathways-fellowship.page |
| 3 | NYC Government Exam|PDF withe exam information for electrical engineering interns|https://www.nyc.gov/assets/dcas/downloads/pdf/noes/20266047000.pdf |
| 4 |NYC Gov Exam |PDF woth information about Computer Associate Title |https://www.nyc.gov/assets/dcas/downloads/pdf/noes/20255050000.pdf |
| 5 |NYC Gov Exam |PDF woth information about Bridge for Various titles|https://www.nyc.gov/assets/dcas/downloads/pdf/noes/20222978000.pdf |
| 6 |MTA NYC Site |Website with information about  Cybersecurity Internships|https://careers.mta.org/jobs/17731475-cyber-security-operational-technology-and-engineer-fellow-fall |
| 7 |MTA NYC Site |Website with information about Data Analyst Internships|https://careers.mta.org/jobs/17728691-data-analyst-emerging-talent-intern-fall |
| 8 |MTA jobs thread |Reddit thread about frustration with the process |https://www.reddit.com/r/AskNYC/comments/1mmwpn6/why_the_hell_cant_i_find_a_job_with_the_mta/ |
| 9 | OSA union wesbite for staff analysts|Website |https://www.osaunion.org/exam/main.html |
| 10 |Reddit |Thread discussing if civil service is worth it |https://www.reddit.com/r/nycpublicservants/comments/1oeadpj/who_regrets_joining_the_nyc_government_job/ |

---

## Chunking Strategy

<!-- Describe your chunking approach with enough specificity that someone else could reproduce it.
     Include:
     - Chunk size (characters or tokens) and why that size fits your documents
     - Overlap size and why (or why not) you used overlap
     - Any preprocessing you did before chunking (e.g., stripping HTML, removing headers)
     - What your final chunk count was across all documents -->
I will try fixe size 
**Chunk size:**
My chunk size should be about 250 characters, as most of my sources are from government notices which are long.
**Overlap:**
Overlap size should be 100.
**Why these choices fit your documents:**
Toward the end of some paragraphs things repeat and start again in the next chunk.
**Final chunk count:**
The system should use the top 10 chunks as all the information should be there. For the exams, information about requirements is toward the top and for reddit threads or general information sites the information is small enough where 10 chunks should suffice.
---

## Embedding Model

<!-- Name the embedding model you used and explain your choice.
     Then answer: if you were deploying this system for real users and cost wasn't a constraint,
     what tradeoffs would you weigh in choosing a different model?
     Consider: context length limits, multilingual support, accuracy on domain-specific text,
     latency, and local vs. API-hosted. -->

**Model used:**
all-MiniLM-L6-v2 via sentence-transformers
**Production tradeoff reflection:**
This model was used for local use and lower requirements. I chose the top-k approach to get 10 chunks per query. If cose wasnt an issue I would choose an API based system as I wouldnt have to manage my own system or hardware.
---

## Grounded Generation

<!-- Explain how your system enforces grounding — how does it prevent the LLM from answering
     beyond the retrieved documents?
     Describe both your system prompt (what instruction you gave the model) and any structural
     choices (e.g., how you formatted the context, whether you filtered low-relevance chunks).
     Do not just say "I told it to use the documents" — show the actual instruction or explain
     the mechanism. -->

**System prompt grounding instruction:**
You are a college guidance counseler who has been asked to help students find internships or jobs in local NYC government or MTA. You have been asked to read documents and information sites to give students a feel for how to apply and the timeframe expected to get a job or internship. Students have given you 10 documents as examples of interests and want answers based on them. 
**How source attribution is surfaced in the response:**

---

## Evaluation Report

<!-- Run your 5 test questions from planning.md through your system and record the results.
     Be honest — a partially accurate or inaccurate result that you explain well is more
     valuable than a suspiciously perfect result. -->

| # | Question | Expected answer | System response (summarized) | Retrieval quality | Response accuracy |
|---|----------|-----------------|------------------------------|-------------------|-------------------|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |

**Retrieval quality:** Relevant / Partially relevant / Off-target  
**Response accuracy:** Accurate / Partially accurate / Inaccurate

---

## Failure Case Analysis

<!-- Identify at least one question where retrieval or generation did not work as expected.
     Write a specific explanation of *why* it failed, tied to a part of the pipeline.

     "The answer was wrong" is not an explanation.

     "The relevant information was split across a chunk boundary, so retrieval returned
     only half the context — the model didn't have enough to answer correctly" is an explanation.

     "The embedding model treated the professor's nickname as out-of-vocabulary and returned
     results from an unrelated review" is an explanation. -->

**Question that failed:**

**What the system returned:**

**Root cause (tied to a specific pipeline stage):**

**What you would change to fix it:**

---

## Spec Reflection

<!-- Reflect on how planning.md shaped your implementation.
     Answer both questions with at least 2–3 sentences each. -->

**One way the spec helped you during implementation:**

**One way your implementation diverged from the spec, and why:**

---

## AI Usage

<!-- Describe at least 2 specific instances where you used an AI tool during this project.
     For each: what did you give the AI as input, what did it produce, and what did you
     change, override, or direct differently?

     "I used Claude to help me code" is not sufficient.
     "I gave Claude my Chunking Strategy section from planning.md and asked it to implement
     chunk_text(). It returned a function using a fixed character split. I overrode the
     chunk size from 500 to 200 because my documents are short reviews, not long guides." -->

**Instance 1**

- *What I gave the AI:*
- *What it produced:*
- *What I changed or overrode:*

**Instance 2**

- *What I gave the AI:*
- *What it produced:*
- *What I changed or overrode:*
