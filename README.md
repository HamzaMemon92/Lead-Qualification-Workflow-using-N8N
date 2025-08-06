# Lead Qualification Workflow for Big Boy Recruits using n8n

This project is a smart automation workflow built using [n8n](https://n8n.io) (or Activepieces) to help Big Boy Recruits, a Dallas-based tech recruitment firm, automatically qualify inbound leads from their website.



##  Goal

Automatically decide if a company is a good fit based on:

- If the company is **software-based** (SaaS or dev agency)
- If the company is **hiring frequently**
- If they are looking to recruit tech talent

If the lead **is qualified**, it sends their info to a second workflow.  
If the lead **is not qualified**, it sends a polite email rejection using Gmail.

---

##  What's Included

- `main-workflow.json` → Handles form submission, AI analysis (Gemini), and routing
- `target-workflow.json` → Handles qualified leads (more info below)
- `recording.mp4` → A walkthrough of how the system works
- `README.md` → This file!



##  Second Workflow (Target Workflow)

The **target workflow** is triggered via webhook from the main flow when a lead is qualified.

It follows this structure:

1. **Starts with Webhook trigger**  
   Receives lead data (name, message, email, company info) from the first workflow.

2. **Goes to 'Edit Lead' node**  
   Updates or stores the lead information.

3. **AI Agent node** (optional)  
   You can enrich lead info further using Gemini or OpenAI.

4. **Ends in routing logic**  
   Determines if the lead goes to an Agency or SaaS pipeline based on logic.

> ℹ️ In the main flow, an **Output Parser** ensures only the needed fields (name, email, message, company data) are passed to the second workflow clearly.



##  How to Use

1. **Import both JSON files** into your n8n/Activepieces instance.
2. Set up the following:
   - **Webhook** URL in the main flow (paste from target flow trigger)
   - **Gmail credentials** for rejection emails
   - **AI Agent** like Gemini (Google) or OpenAI (ChatGPT)
3. Test with your own form submission tool or manually run with dummy data.





##  Demo (Screen Recording)

Watch how the automation works step-by-step: 

https://drive.google.com/file/d/1EH78_ueJnXIrNeOH-HYWr6DNHoj-tgiy/view?usp=drive_link


---

##  Built For

**Big Boy Recruits** — a Dallas-based recruiting firm helping SaaS and software companies hire elite developers and tech talent post-liquidation or during scaling phases.

---

##  Questions?

Open an issue or connect with me on LinkedIn if you need help implementing this workflow in your own use case.
www.linkedin.com/in/hamza-memon-a002851a7
