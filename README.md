# Stack Overflow Survey, Tableau Story

![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=Tableau&logoColor=white)
![Data Visualization](https://img.shields.io/badge/Data_Visualization-4E79A7?style=for-the-badge)
![Respondents](https://img.shields.io/badge/Survey_Respondents-49%2C191-green?style=for-the-badge)
![Countries](https://img.shields.io/badge/Countries-178-blue?style=for-the-badge)

**Course:** BUDT758D, Data Visualization and Web Analytics | University of Maryland, Robert H. Smith School of Business  
**Team:** Group 1 | **Year:** 2025

[![Open on Tableau Public](https://img.shields.io/badge/Live_Dashboard-Open_on_Tableau_Public-E97627?style=for-the-badge&logo=Tableau&logoColor=white)](https://public.tableau.com/app/profile/kunal.roy.chowdhury/viz/StackOverflowSurveyTableauStoryGroup1/OurTableauStory)

---

## Executive Summary

### Problem
The 2025 Stack Overflow Annual Survey captures responses from 49,191 developers across 178 countries at a pivotal moment: AI tools are reshaping how developers work, learn, and use platforms like Stack Overflow. The challenge is turning a massive, multi-dimensional dataset into clear, actionable insights for platform strategists, educators, and technology leaders.

### Solution
Our team built a five-dashboard Tableau Story that guides viewers through four narrative chapters: from who developers are, to how they use Stack Overflow, to how AI is changing the profession. Each dashboard is interactive and filterable by country and AI usage group.

### Key Impact
- **67.32%** of respondents actively learned AI tools in the past year
- **44.4%** use AI tools actively in their work
- **10.3%** report that AI tools are causing friction with their existing Stack Overflow workflows
- Full-stack developers (12,351) are the single largest developer type, and the most engaged AI adopters

---

## Dashboard Overview

The Tableau Story is organized into four narrative tabs. Click the badge above to explore all dashboards interactively on Tableau Public.

### Story Tab 1, The 2025 Developer Story
An introduction to the dataset and the central tension: AI is not replacing Stack Overflow's community; it is reshaping it. Key headline stats: 49,191 respondents, 178 countries, and three critical KPIs.

**Headline KPIs:**
| Metric | Value |
|---|---|
| Respondents who learned AI tools last year | 67.32% |
| Actively use AI tools at work | 44.4% |
| Have a Stack Overflow account | 54.3% |

### Story Tab 2, Who's Building the Future? (Developer Demographics)
A demographic breakdown of the global developer community.

**Key KPIs:**
| Metric | Value |
|---|---|
| Total Respondents | 49,191 |
| Top Age Group | 25-34 years old |
| Countries Represented | 178 |
| % Professional Developers | 76.17% |

**Visualizations included:**
- Developer Type treemap (Full-stack: 12,351 | Back-end: 6,453 | Student: 3,008)
- Age Distribution bar chart (25-34 dominant, followed by 35-44)
- Employment Type breakdown (Employed majority, Self-Employed second)

### Story Tab 3, Stack Overflow in the Age of AI
The core usage and AI impact dashboard with four KPI cards and two interactive charts.

**Key KPIs:**
| Metric | Value |
|---|---|
| % With Stack Overflow Account | 54.3% |
| % Weekly Visitors | 35.1% |
| % Active AI Users | 44.4% |
| % Reporting AI-Driven Friction | 10.3% |

**Participation Frequency:** Active AI users visit Stack Overflow far less frequently than non-AI users. The "never participated" and "less than once a year" bars are dominated by the Active AI User segment, suggesting AI is becoming a first-stop resource before Stack Overflow.

**Friction Heatmap:** Occasional AI users show the highest friction (2,316 reporting "rarely, almost never" useful), compared to 1,107 non-AI users in the same category.

### Story Tab 4, The Rise of AI in 2025
AI adoption, learning patterns, and task delegation behavior.

**Key Stats:**
| Metric | Value |
|---|---|
| Respondents who learned AI tools | 67.32% |
| Learned AI tools required for job/career | 16,400 |
| Learned AI tools for personal use | 14,000 |

**AI Agents Use (bubble chart):** The largest bubble is "No, and I don't plan to," followed by "No, but I plan to" — showing that while AI tool adoption is high, agentic AI use is still nascent.

**Tasks Planned vs. Not Planned for AI:** Documentation and predictive modeling top the "planned" list; code review and architecture decisions remain firmly in human hands.

---

## Technical Architecture

### Data Sources
| Source | Description |
|---|---|
| `survey_results_public` | Main Stack Overflow 2025 Annual Survey dataset |
| `so_usage_clean_v2` | Cleaned usage and platform engagement data |
| `so_content_exploded` | Exploded content preference records (one row per format) |

The workbook uses Tableau's federated data source model, joining survey responses across multiple filtered views.

### Workbook Structure
- **25 Worksheets** covering demographics, AI adoption, usage intensity, friction analysis, content preferences, and geographic maps
- **5 Dashboards:** Developer Demographics, Summary, Usage and AI Impact, AI Adoption, and the full Tableau Story
- **4 Story Tabs** following a narrative arc from context to recommendation

### Key Calculated Fields
| Field | Formula |
|---|---|
| % With SO Account | `SUM([Has SO Account]) / COUNT([ResponseId])` |
| % Visit Weekly or More | `SUM([Weekly Visitor]) / COUNT([ResponseId])` |
| % Active AI Users | `SUM([Active AI]) / COUNT([ResponseId])` |
| % High Friction Users | `SUM([High Friction]) / COUNT([ResponseId])` |

### Dashboard Design Choices
- **Orange = Active AI User** consistently across all charts for visual continuity
- Country and AI User Group filters apply globally across dashboards
- Heatmap color scale highlights friction intensity by group
- Bubble chart for AI agent adoption encodes magnitude by circle size

---

## Real-World Applications

**For Stack Overflow:** With 10.3% of the most engaged users reporting friction, integrating AI-native features (inline AI answers, hybrid Q&A) is urgent to retain active developers.

**For Developers:** Deployment, planning, and code review remain firmly in human hands. Mastering these tasks separates good developers from great ones in an AI-saturated market.

**For Organizations:** 44.4% of developers already use AI actively. The question is no longer whether to adopt AI, but how to use it strategically without displacing institutional knowledge.

**For Educators:** 9.16% of respondents are students. AI literacy must be a foundational skill before graduation, not an elective.

---

## Limitations

- Survey data is self-reported and subject to response bias
- Geographic representation is uneven; English-speaking countries are overrepresented
- "AI usage" categories are defined by respondent self-classification, not measured behavior
- The survey captures a single point in time; AI tool adoption is evolving rapidly
- Stack Overflow friction may reflect survey framing, not actual platform dissatisfaction

---

## How to View

### Option 1, Tableau Public (Recommended)
View the fully interactive story online (no software required):

**[Open on Tableau Public](https://public.tableau.com/app/profile/kunal.roy.chowdhury/viz/StackOverflowSurveyTableauStoryGroup1/OurTableauStory)**

All filters are live. Use the Country and AI User Group dropdowns to explore specific segments.

### Option 2, Tableau Desktop
1. Download `Stack Overflow Survey Tableau Story Team 1-Final.twbx` from this repo
2. Open with Tableau Desktop (version 2023.1 or later recommended)
3. All data is packaged inside the `.twbx` — no external database connection required
4. Navigate the story tabs in order for the full narrative experience

---

*Data source: Stack Overflow Annual Developer Survey 2025, [survey.stackoverflow.co](https://survey.stackoverflow.co)*  
*Built with Tableau Desktop | BUDT758D, University of Maryland*
