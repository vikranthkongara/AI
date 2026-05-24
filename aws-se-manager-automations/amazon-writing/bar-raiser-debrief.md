# Bar Raiser Debrief Summary

Compile a hiring debrief summary: interview scores, Leadership Principles assessments, strengths and concerns per interviewer, overall hiring recommendation with justification.

## Data Sources
- Internal search: interview scorecards, interviewer written feedback, job description, level expectations
- Email/Slack: debrief scheduling communications, any pre-debrief notes from interviewers
- Calendar: debrief meeting details, interview loop participants

## Instructions
1. **Candidate overview (2-3 sentences).** Role applied for, level, number of interviewers, overall recommendation (hire/no-hire/inclined/not inclined). State the result upfront.
2. **Interview scorecard summary.** For each interviewer:
   - Name and LP(s) assessed
   - Rating (Strong Hire / Hire / Inclined / Not Inclined / No Hire)
   - Key strength observed (1 sentence with specific example from interview)
   - Key concern (1 sentence with specific example, or "None identified")
3. **Leadership Principles assessment.** For each LP evaluated:
   - LP name
   - Consensus rating
   - Supporting evidence (strongest example cited across interviewers)
   - Gaps or concerns (if any)
4. **Strengths summary.** Top 3-4 strengths that multiple interviewers identified. Cite specific examples.
5. **Concerns summary.** Any concerns raised, with severity assessment (blocking vs non-blocking). For non-blocking concerns, note what evidence would be needed to resolve them.
6. **Bar Raiser assessment.** Bar Raiser's independent evaluation: does the candidate raise the bar for the role and level? Specific evidence cited.
7. **Hiring recommendation.** Final recommendation with clear justification. If hire: what makes this candidate exceptional for this role. If no-hire: what specific gap(s) led to this decision.
8. **Dissenting opinions.** If interviewers disagreed, capture both perspectives fairly. Note what evidence was weighed differently.

### Amazon Writing Style Rules
- Evidence-based: every assessment tied to a specific interview example
- No weasel words: "seemed strong technically" must become "solved the system design problem identifying 3 key trade-offs and proposing a scalable solution within time constraints"
- Specificity: reference the exact LP, the exact question type, the exact behavior observed
- Fair and balanced: present concerns with the same rigor as strengths
- No bias language: assess behaviors and outcomes, not style or personality
- "So what" for each data point: what does this observation tell us about the candidate's likely performance at this level

## Output Format
```
[Title: Debrief Summary - <Candidate Name> - <Role/Level>]
[Date: <date>] [Bar Raiser: <name>]

Recommendation: [HIRE / NO HIRE]

Candidate Overview
[2-3 sentences: role, level, loop size, outcome]

Scorecard Summary
| Interviewer | LP Assessed | Rating | Key Strength | Key Concern |
|-------------|-------------|--------|--------------|-------------|
| ...         | ...         | ...    | ...          | ...         |

Leadership Principles Assessment
| LP | Rating | Evidence | Concerns |
|----|--------|----------|----------|
| ...| ...    | ...      | ...      |

Strengths
1. [Strength with evidence from multiple interviewers]
2. ...

Concerns
1. [Concern with severity: blocking/non-blocking]
2. ...

Bar Raiser Assessment
[1 paragraph: does candidate raise the bar, with evidence]

Recommendation Justification
[1-2 paragraphs: clear reasoning for the hiring decision]

Dissenting Opinions (if any)
[Fair representation of disagreements]
```

## Delivery
Send as Slack DM to the hiring manager. Save to the candidate's interview record. If there are action items (e.g., additional reference checks), flag those explicitly.
