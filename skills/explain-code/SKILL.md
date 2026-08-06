---
name: explain-code
description: "When the user wants a piece of code explained clearly — with a real-world analogy, a visual diagram, a line-by-line walkthrough, key concepts, common gotchas, and how to modify it. Also use when the user says 'explain this code,' 'what does this do,' 'walk me through this,' 'I don't understand this function,' 'help me onboard to this codebase,' or 'explain this to a beginner.' Designed for learning unfamiliar code or explaining code to someone less technical."
metadata:
  version: 1.0.0
---
# Explain Code

Explain code with diagrams, analogies, and beginner-friendly language.

## Description
Takes a piece of code and explains it thoroughly using real-world analogies, visual diagrams, line-by-line walkthroughs, and common gotchas. Designed for beginners or anyone learning a new codebase.

## When to Use
When you need to understand unfamiliar code, onboard onto a project, or explain code to someone less technical.

## Instructions

When asked to explain code, provide ALL of the following sections:

### 1. Real-World Analogy
Start with a relatable analogy that captures what this code does. Use everyday objects or processes. Keep it to 2-3 sentences.

Example: "This function is like a bouncer at a club. It checks everyone's ID (validates the token), and only lets in people on the guest list (authorized users). If your ID is fake (expired token), you get turned away (401 error)."

### 2. Visual Diagram
Create an ASCII or Mermaid diagram showing the flow:
- For functions: input → processing → output
- For components: parent → children → data flow
- For API routes: request → middleware → handler → response
- For database: tables → relationships → queries

```
Example:
  [User Click] → [API Call] → [Validate Input]
                                    ↓
                              [Query Database]
                                    ↓
                              [Format Response]
                                    ↓
                              [Return to UI]
```

### 3. Line-by-Line Walkthrough
Go through each significant line or block:
- What it does in plain English
- Why it exists (the purpose, not just the syntax)
- What would happen if you removed it

Use this format:
```
Line 5:  const user = await db.users.findUnique({ where: { id } })
         → Looks up the user in the database by their ID
         → If no user found, this returns null (handled on line 8)
```

### 4. Key Concepts
List any programming concepts used, with brief explanations:
- "async/await — lets you write asynchronous code that reads like synchronous code"
- "destructuring — pulls specific values out of an object: `const { name } = user`"
- "guard clause — early return to handle edge cases before the main logic"

### 5. Common Gotchas
What could trip someone up:
- Edge cases not obvious from the code
- Implicit behaviors or side effects
- Common mistakes when modifying this code
- Performance implications

### 6. How to Modify
If you wanted to change this code, here's how:
- "To add a new field: add it to the Zod schema on line 3, then to the query on line 7"
- "To change the error message: update line 12"
- "To add caching: wrap the database call on line 5 with a cache check"

## Tone
- Patient and encouraging — no jargon without explanation
- Use "we" language: "Here we're checking if..."
- Celebrate complexity: "This is a clever pattern because..."
- Never condescending: avoid "simply", "just", "obviously"
