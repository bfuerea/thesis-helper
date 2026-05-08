***

# 🎓 MVT Dashboard: Minimum Viable Thesis

## Overview
The **MVT (Minimum Viable Thesis) Dashboard** is a lightweight, single-page project management tool designed for the final stages of a PhD in Veterinary Pathology Digitization. Instead of a complex Jira or Trello board, this dashboard serves as a **psychological anchor**, keeping the focus on the "Minimum Viable" requirements for graduation and providing a strict guard against technical over-engineering (rabbit holes).

## 🎯 Core Philosophy
The dashboard is built around the **MVT Principle**: 
> *"A perfect thesis is a finished thesis."*

It prioritizes:
1. **Submission over Perfection**: Focuses on "Good Enough" standards for committees.
2. **Scope Guarding**: Constant reminders to stop polishing UI or fixing minor bugs that don't contribute to the doctoral degree.
3. **Volume Balance**: Ensuring the personal research (Part II) outweighs the literature review (Part I).
4. **Leveraging Existing Expertise**: Treating pipeline additions (like the `.szi` to NAS extraction) as an automation engineering problem. Write the Python/JS scheduler, write the tests, deploy it, and move immediately back to writing the manuscript.

## 🚀 Features

### 1. Priority Sprints
A categorized task list that visually differentiates between **Highest/High** priority (critical path, currently locked to Part 1 completion) and **Low** priority (nice-to-have/completed tasks like MongoDB Standardization). Each task includes a "Pivot Command" (Failsafe) to tell you exactly when to stop and move on.

### 2. Thesis Volume Tracker
A dynamic progress bar that reads a CSV file (`Heading_Pages_Export.csv`) to track:
- Total page count against the 150-page target (USAMV Norm 1.3).
- The ratio between Part I and Part II.
- Visual alerts if Part II is not sufficiently larger than Part I.

### 3. Scope Guard
A dedicated sidebar containing the "Zotero Rule" and a "Relevance Filter" to interrogate whether current technical struggles actually contribute to the field of **Digital Pathology**.

### 4. Deadline Countdown
A "Working Backwards" timeline from the defense date to ensure public submission and announcement deadlines are met.

## 🛠 Technical Setup

### Requirements
- A modern web browser.
- No installation required (Zero-dependency).

### How to Run
Simply open `index.html` in any web browser.

### Customization & Maintenance

#### Updating Tasks & Deadlines
To update your goals, open `index.html` and edit the `tasks` array in the `<script>` section. 

*Example of a standard task format:*
```javascript
const tasks = [
  { 
    id: 4, 
    category: 'Digital Lab', 
    title: 'OpenSeadragon Optimization', 
    detail: 'Extracted data from .szi can be served via FastAPI V3 and viewed via SlideViewerDemoV3.', 
    priority: 'Low',
    deadline: 'No Deadline (Nice-to-have)',
    subtasks: [
      'Add Python/Node.js scheduler to extract from .szi and place files in the NAS folder.',
      'Add basic automation tests for the scheduler.'
    ],
    failsafe: 'Stick to the working SVS -> DZI local conversion pipeline. Do not overwork the NAS compute resources.'
  },
  // ...
];
Updating Page Volume
The dashboard automatically fetches data from Heading_Pages_Export.csv. To update page counts:

Update your Word/PDF document.

Export the heading/page count to a CSV named Heading_Pages_Export.csv in the same folder.

Refresh the browser.

📂 File Structure
Plaintext
├── index.html                 # The main dashboard
└── Heading_Pages_Export.csv   # Page count data for the Volume Tracker
⚠️ Warning
Do not spend more than 15 minutes a week updating this dashboard. If you find yourself spending hours polishing the CSS, adding new frameworks, or modifying the JavaScript beyond simple task updates, you have fallen into a Technical Rabbit Hole. Stop immediately, close the IDE, and go back to writing Thesis Part 1.
