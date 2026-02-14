# Global Agent Instructions

These are global instructions for all projects. Follow them every time.

## 1) Use plain language
- Do not use technical jargon.
- Assume the user has no development background.
- Explain things in simple, everyday words.

## 2) Always handle setup fully
- Always prepare all required setup steps.
- This includes installing packages, creating required files, and configuring project basics.
- Do not leave setup gaps.

## 3) Keep user intervention minimal and clear
- Only ask the user to do environment variable setup when needed.
- Pre-create the env file for them (for example: `.env.local`, `.env`, or another clearly named file).
- Tell the user the exact file name and exact lines to add.
- For every required key or secret:
  - Explain what it is in plain language.
  - Provide the direct URL where the user can get it.
  - Give copy/paste-ready variable names and value format.

## 4) Preferred tech stack (default unless user says otherwise)
- Frontend: Next.js + TypeScript
- Database and file storage: Convex
- Authentication: Clerk
- Email automation (if needed): Resend
- For crucial setup steps or when blocked, check the latest official documentation online before proceeding.

## 5) Repo memory: always maintain `AGENTS.md` in each project root
- Every project must have its own root `AGENTS.md`.
- Use that file as working memory for that specific repository:
  - What worked well
  - What failed and why
  - Gotchas, fixes, and decisions
  - User remember/forget requests
- Update it when information changes.
- Remove notes that are outdated or incorrect.

## 6) Keep `README.md` current
- Always keep `README.md` up to date.
- It must clearly explain setup, environment variables, run steps, and key project behavior.
- Write it so both humans and AI agents can quickly understand and use the project.

## 7) Git commit strategy
- Commit each meaningful section of work in every chat session.
- Commit message rules:
  - Subject line max 80 characters
  - Add a blank line
  - Then add a simple explanation in plain language of what changed and why

## 8) Clarify unclear requests early
- If a request is unclear or misses an important consideration, ask questions.
- Always include a recommended option.
- Clearly say when an option changes direction from the current plan.
- If the request is significantly different, suggest a better boundary:
  - Separate project
  - Separate module
  - Separate branch

## 9) Long chat context handling
- If the chat becomes long and the user starts a new task, suggest starting a new chat.
- If prior context is needed, provide a short ready-to-paste summary + request snippet for the new chat.

## Goal
- Enable project creation and contribution with minimal technical knowledge.
- Keep instructions simple, complete, and continuously improved based on real issues found during work.
