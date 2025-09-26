
## Employee Score 

- Shubham, Amrendra, Yashwant

- For loop
  - Employees = JSON Arra
  - 001 
    - All folder iterate
    - Extra weightage to career page
    - Text concatenate
    - Chatgpt
    - Response
    - JSON Array.add(001)
  - 1000 size JSON Array
    - All employees

## Org Score 
  * Tell us the skills of the organisation based on employee data, classify it according to experience. 
  * Ensure skill is generated with number of people with that skill and the the overall efficiency for that skill.
  * Prompt - JSON format
    - Approach 1
      - Send the entire data to chatgpt
        - Too large
    - Approach 2
      - **Batch** - Chatgpt - 50 employees size
      - 50 employees ka data
      - Concatenate the next prompt to rebuild the context
        - We have evaluated 100, help us evaluate the next 50
      - Single JSON for organisation




## API generation
    - organsation-skillset - Hardcode
    - employee-skillset?id=001
        - { Employee Score, data for popup }
    
```
{
  "employee": {
    "name": "Rohit Verma",
    "role": "Full Stack Developer",
    "experience": "5 years"
  },
  "overallScore": {
    "current": 72,
    "orgAverage": 78,
    "status": "Slightly Below Average",
    "trend": "Improving"
  },
  "scoreHistory": [
    {
      "month": "2025-06",
      "overallScore": 65,
      "notes": "Good backend work, but weak in frontend frameworks."
    },
    {
      "month": "2025-07",
      "overallScore": 68,
      "notes": "Improved React skills after attending internal training."
    },
    {
      "month": "2025-08",
      "overallScore": 70,
      "notes": "Better API handling, still missing Flutter exposure."
    },
    {
      "month": "2025-09",
      "overallScore": 72,
      "notes": "Maintained steady improvement; Flutter remains a gap."
    }
  ],
  "skillComparison": [
    {
      "skill": "JavaScript",
      "employeeScore": 75,
      "orgAverage": 80,
      "status": "Below Average"
    },
    {
      "skill": "React",
      "employeeScore": 78,
      "orgAverage": 80,
      "status": "On Par"
    },
    {
      "skill": "Node.js",
      "employeeScore": 82,
      "orgAverage": 80,
      "status": "Above Average"
    },
    {
      "skill": "Databases (SQL/NoSQL)",
      "employeeScore": 76,
      "orgAverage": 78,
      "status": "On Par"
    },
    {
      "skill": "DevOps (CI/CD, Docker)",
      "employeeScore": 70,
      "orgAverage": 78,
      "status": "Below Average"
    },
    {
      "skill": "Flutter",
      "employeeScore": 0,
      "orgAverage": 75,
      "status": "Missing"
    }
  ],
  "learningResources": [
    {
      "topic": "JavaScript Advanced Concepts",
      "article": "JavaScript is the foundation of web development. Mastering asynchronous programming, closures, and ES6+ features is essential for scalable applications. Improving in these areas helps close the gap with high-performing peers.",
      "quiz": [
        {
          "question": "What is the difference between 'let', 'var', and 'const' in JavaScript?",
          "options": ["Scope and mutability", "Nothing, they are the same", "Only const is block-scoped", "var cannot be reassigned"],
          "answer": "Scope and mutability"
        },
        {
          "question": "Which JavaScript feature handles asynchronous operations?",
          "options": ["Promises", "Loops", "Closures", "Classes"],
          "answer": "Promises"
        }
      ]
    },
    {
      "topic": "DevOps Essentials",
      "article": "DevOps bridges development and operations. Knowledge of CI/CD, Docker, and cloud deployment enables faster, more reliable releases. Improving DevOps understanding will align delivery speed with industry benchmarks.",
      "quiz": [
        {
          "question": "What does CI/CD stand for?",
          "options": ["Continuous Integration / Continuous Deployment", "Code Integration / Code Delivery", "Centralized Infrastructure / Cloud Development", "Continuous Improvement / Cloud Delivery"],
          "answer": "Continuous Integration / Continuous Deployment"
        },
        {
          "question": "Which tool is widely used for containerization?",
          "options": ["Docker", "Nginx", "PostgreSQL", "Terraform"],
          "answer": "Docker"
        }
      ]
    },
    {
      "topic": "Flutter Training",
      "article": "Flutter is a modern cross-platform framework for building mobile and web apps from a single codebase. With high demand in the organisation, learning Flutter will expand project opportunities. Start by exploring widgets, state management, and hot reload, which make Flutter a powerful UI toolkit.",
      "quiz": [
        {
          "question": "What language is used to develop Flutter apps?",
          "options": ["Kotlin", "Dart", "JavaScript", "Swift"],
          "answer": "Dart"
        },
        {
          "question": "Which feature allows instant UI updates in Flutter during development?",
          "options": ["Hot Reload", "Cold Restart", "Fast Compile", "Quick Deploy"],
          "answer": "Hot Reload"
        }
      ]
    }
  ]
}


```

## Data for Popup
/
    - ChatGPT
        - Employee Profile, comparing it with org score, suggest technolgies for improvement for better alignment. Create some 30 second read articles and few questions for these course
        - Expected output
            - Suggested courses
            - Questions
            - 30 seconds articles for these topics


```aiignore
Generate a JSON for comparing an employee’s skillset inside a technical organisation.

The JSON must contain the following sections:

employee → Basic details (name, role, experience).

overallScore → Current score (out of 100), organisation average, status (e.g., Above Average / Needs Improvement), and trend (Improving / Declining / Stable).

scoreHistory → Past monthly history of overall scores (out of 100) with notes on progress.

skillComparison → A list of skills with employeeScore (0–100), orgAverage (0–100), and status (Above Average, Below Average, On Par, or Missing).

learningResources → For each weak or missing skill:

A short 30-second article explaining why the skill is important and how to improve.

A quiz with at least 2 questions, 4 options each, and the correct answer.

The organisation wants to upskill their resources on flutter.

Notes:

Use a 1000-point scale for all scores.

If the employee is missing a critical skill, ensure it appears in skillComparison with a score of 0 and add a learning resource for it.

Keep the JSON well-structured and ready for direct use in dashboards or APIs.
```


## UX Development

Sharad

    - Will utilise the above JSON to render
        - Employee overall score
        - Graph generation history
        - Suggested courses section
        - Popup of quiz + score++



