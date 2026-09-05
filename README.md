# German Recruiter AI Persona

## Project by MaloneFreak (Pedro Giácomo)

This project provides a detailed AI persona prompt designed to transform any capable Large Language Model (LLM) into an experienced German HR Recruiter. This "skill" helps job seekers by analyzing job postings and resumes, then generating tailored, ATS-safe resumes and compelling cover letters in either English or German.

## How it Works

Once you paste the provided AI persona prompt into your preferred LLM, the AI will adopt the role of a German recruiter and guide you through the following process:

1.  **Resume & Job Analysis:** You will provide your current resume (e.g., paste the text, or describe its key sections) and one or more job descriptions. The AI will then analyze your resume against the job requirements and suggest the best matches.
2.  **Job Selection:** Based on the AI's analysis, you select the job you want to apply for.
3.  **Tailored Resume Generation:** The AI will create a customized resume specifically for the chosen job.
    *   **Format:** The resume will be generated in **Markdown** format. Markdown is highly versatile, easy to read, and can be converted to various document types (including PDF) using simple online tools or software (e.g., Typora, VS Code with Markdown extensions, Pandoc, or even Google Docs/Microsoft Word importing a .md file). This ensures it's both ATS-safe and user-friendly for conversion.
    *   **Language:** The resume will be generated in the language of the job description (English or German).
4.  **Interview Questioning:** To gather specific details for your cover letter, the AI will ask you a few pertinent questions related to the job and your experience.
5.  **Cover Letter Generation:** Using your answers, the AI will craft a persuasive cover letter tailored to the position.
    *   **Format:** Like the resume, the cover letter will be in **Markdown** format for easy conversion and ATS compatibility.
    *   **Language:** The cover letter will match the job description's language (English or German).

## Why Markdown for Output?

Markdown is chosen for its simplicity, readability, and compatibility across various platforms and tools. It's plain text with simple formatting syntax, making it:
*   **ATS-Safe:** Most Applicant Tracking Systems can easily parse well-structured Markdown.
*   **Easy to Convert:** Numerous free online converters and software can transform Markdown files into professional-looking PDFs, Word documents, or HTML files with minimal effort. This gives you full control over the final visual presentation without relying on the AI to generate a specific graphical format.

## How to Use This Skill

1.  **Copy the AI Persona Prompt:** Copy the entire text from the `german_recruiter_persona_prompt.txt` (or the prompt provided below in this README).
2.  **Start a New Chat:** Go to your preferred LLM (e.g., Gemini, ChatGPT, Claude) and start a brand new conversation.
3.  **Paste the Prompt:** Paste the copied prompt into the chat and send it. The AI will now adopt the persona.
4.  **Follow the AI's Instructions:** The AI will introduce itself and ask you to provide your resume and the job descriptions.
5.  **Iterate:** Follow the steps as outlined by the AI to get your tailored resume and cover letter.

## Example Workflow

*   **You:** (Paste the persona prompt)
*   **AI:** "Guten Tag! I am your experienced German HR Recruiter..."
*   **You:** (Provide your resume text)
*   **You:** (Provide job description 1, job description 2)
*   **AI:** "Based on my analysis, Job 1 at Siemens and Job 2 at Bosch seem like excellent fits..."
*   **You:** "I'd like to proceed with Job 1 at Siemens."
*   **AI:** (Generates resume in Markdown)
*   **AI:** "Now, to craft a compelling cover letter, please tell me: 1. What specifically attracts you to Siemens? 2. How does your experience in X directly relate to Y in this role?"
*   **You:** (Answer the questions)
*   **AI:** (Generates cover letter in Markdown)

## Contributions

Feel free to suggest improvements or enhancements to the prompt!

---
