
## Employee Score 

- Shubham, Amrendra, Yashwant

- For loop
  - Employees = JSON Arra
  - 001 
    - All folder iterate
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
    "name": "Ananya Nanda",
    "role": "Delivery Manager",
    "experience": "10 years"
  },
  "overallScore": {
    "current": 63,
    "orgAverage": 76,
    "status": "Needs Improvement",
    "trend": "Improving"
  },
  "scoreHistory": [
    {
      "month": "2025-06",
      "overallScore": 58,
      "notes": "Struggled with Scrum and Project Management practices."
    },
    {
      "month": "2025-07",
      "overallScore": 60,
      "notes": "Started Agile refresher workshops; minor improvements."
    },
    {
      "month": "2025-08",
      "overallScore": 62,
      "notes": "Improved in stakeholder management through coaching."
    },
    {
      "month": "2025-09",
      "overallScore": 63,
      "notes": "Maintained performance; identified missing technical awareness."
    }
  ],
  "skillComparison": [
    {
      "skill": "People Management",
      "employeeScore": 80,
      "orgAverage": 70,
      "status": "Above Average"
    },
    {
      "skill": "OKRs",
      "employeeScore": 90,
      "orgAverage": 70,
      "status": "Above Average"
    },
    {
      "skill": "Agile",
      "employeeScore": 80,
      "orgAverage": 80,
      "status": "On Par"
    },
    {
      "skill": "Stakeholder Management",
      "employeeScore": 70,
      "orgAverage": 80,
      "status": "Slightly Below Average"
    },
    {
      "skill": "Project Management",
      "employeeScore": 60,
      "orgAverage": 80,
      "status": "Below Average"
    },
    {
      "skill": "Scrum",
      "employeeScore": 60,
      "orgAverage": 80,
      "status": "Below Average"
    },
    {
      "skill": "Technical Awareness",
      "employeeScore": 0,
      "orgAverage": 70,
      "status": "Missing"
    }
  ],
  "learningResources": [
    {
      "topic": "Project Management Fundamentals",
      "article": "Project Management is the backbone of successful delivery. Strong project managers break down complex goals into achievable tasks, track dependencies, and mitigate risks early. A weak score here indicates a need to sharpen planning and execution abilities. Even 30 minutes of daily review of project tracking tools like Jira or MS Project can boost efficiency significantly.",
      "quiz": [
        {
          "question": "What is the primary goal of project management?",
          "options": ["Deliver features fast", "Ensure team harmony", "Deliver value within scope, time, and cost", "Create documentation"],
          "answer": "Deliver value within scope, time, and cost"
        },
        {
          "question": "Which of these is NOT a project management knowledge area?",
          "options": ["Risk Management", "Cost Management", "Sleep Management", "Scope Management"],
          "answer": "Sleep Management"
        }
      ]
    },
    {
      "topic": "Scrum Practices",
      "article": "Scrum empowers teams to be adaptive and iterative. Daily stand-ups, sprint reviews, and retrospectives ensure continuous improvement. A low score in Scrum suggests difficulty in leveraging ceremonies or coaching teams. By practicing effective backlog refinement and sprint planning, you can drastically improve team velocity and morale.",
      "quiz": [
        {
          "question": "How long is a typical Scrum sprint?",
          "options": ["1 week", "2-4 weeks", "6 weeks", "3 months"],
          "answer": "2-4 weeks"
        },
        {
          "question": "Which role in Scrum ensures the team follows Scrum practices?",
          "options": ["Product Owner", "Scrum Master", "Stakeholder", "Tech Lead"],
          "answer": "Scrum Master"
        }
      ]
    },
    {
      "topic": "Technical Awareness for Managers",
      "article": "In today’s organisations, even managers benefit from basic technical literacy. Understanding APIs, cloud deployments, and modern software stacks helps in effective stakeholder conversations and reduces miscommunication. Without this, managers may struggle to align technical and business goals. Start with 15 minutes daily on cloud concepts or software architecture overviews to build this foundation.",
      "quiz": [
        {
          "question": "What does API stand for?",
          "options": ["Advanced Program Interface", "Application Programming Interface", "Automated Process Integration", "Applied Programming Instruction"],
          "answer": "Application Programming Interface"
        },
        {
          "question": "Which of these is a cloud service provider?",
          "options": ["AWS", "Slack", "Jira", "Figma"],
          "answer": "AWS"
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

Notes:

Use a 100-point scale for all scores.

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



