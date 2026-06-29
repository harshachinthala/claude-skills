---
name: resume-ats-optimizer
description: Optimize resumes for Applicant Tracking Systems. Use when user wants to optimize their resume for ATS, check ATS compatibility, analyze keyword match, mentions "ATS", "not getting interviews", "optimize resume", or "keyword optimization". Also use when user provides a resume and mentions applying to jobs.
---

# Resume ATS Optimizer

## When to Use This Skill

Use this skill when the user wants to:
- Optimize their resume for Applicant Tracking Systems (ATS)
- Check if their resume will pass automated screening
- Understand why their applications aren't getting responses
- Mentions keywords like: "ATS", "not getting interviews", "resume not working", "optimize resume", "keyword optimization"

Also use when the user provides a resume file and mentions they're applying to jobs.

## Core Capabilities

- Parse resume and test ATS compatibility
- Extract and analyze keywords against job descriptions
- Identify formatting issues that break ATS parsers
- Calculate match scores between resume and job postings
- Suggest keyword additions and placements
- Generate ATS-friendly formatting recommendations

## The ATS Problem

75% of resumes are rejected by Applicant Tracking Systems before a human ever sees them. Companies use ATS to:
- Filter out unqualified candidates automatically
- Search for specific keywords from job requirements
- Parse resumes into structured data
- Rank candidates by keyword match percentage

Common reasons resumes fail ATS:
1. Poor formatting (tables, columns, headers/footers)
2. Missing keywords from job description
3. Inconsistent section headers
4. Non-standard fonts or special characters
5. Text embedded in images
6. Incorrect file format

## ATS Compatibility Checklist

### File Format
- Use .docx or .pdf (not .pages, .odt)
- PDF must be text-based, not scanned image
- File name: "FirstName_LastName_Resume.pdf"

### Font & Formatting
- Standard fonts: Arial, Calibri, Georgia, Times New Roman
- Font size: 10-12pt for body, 14-16pt for headers
- No text boxes, tables, or columns
- No headers/footers (put contact info in body)
- No images, graphics, or charts
- Consistent date formats (MM/YYYY)
- Standard bullet points (•, -, *)

### Section Headers
Use standard, recognizable headers:
- "Professional Experience" or "Work Experience"
- "Education"
- "Skills"
- "Summary" or "Professional Summary"

### Contact Information
Put in body, not header/footer. Avoid tables, special characters, multiple phone numbers, and full mailing address (city/state is enough).

## Keyword Optimization Process

### Step 1: Extract Job Description Keywords

Identify three types:
- Hard Skills: Programming languages, tools, platforms, certifications, methodologies
- Soft Skills: Leadership, collaboration, communication, problem-solving
- Industry Terms: B2B, SaaS, e-commerce, ARR, MRR

### Step 2: Match Analysis

For each keyword in job description:
1. Check if exact phrase appears in resume
2. Check for synonyms or variations
3. Count frequency of mention
4. Note location (summary, experience, skills)

### Step 3: Calculate Match Score

Match Score = (Keywords Matched / Total Required Keywords) × 100. Target: 80%+.

### Step 4: Keyword Placement Strategy

- Priority 1: Professional Summary — include 5-8 most important keywords
- Priority 2: Skills Section — list keywords explicitly, use exact phrasing from JD
- Priority 3: Experience Bullets — incorporate naturally into achievement statements

Keyword Density: Critical keywords should appear 2-4 times; important keywords 1-2 times. Don't keyword stuff.

## Analysis Output Format

When analyzing a resume, provide a structured report:
- Overall Score: X/100
- File Format Check (pass/fail)
- Formatting Issues (list each)
- Keyword Analysis: Critical Keywords (found/missing), Important Keywords, Match Score
- Recommended Changes: specific before/after examples
- Estimated New Match Score after changes

## Common ATS Failure Patterns

- Creative formatting (two-column, skill bars, text in colored boxes) → use single column, text-only
- Unconventional section names ("My Journey") → use standard headers
- Missing keywords (using synonyms instead of exact terms) → use exact terminology from JD
- Keyword stuffing → list naturally, avoid repetition

## Industry-Specific Considerations

- Tech: Emphasize programming languages and frameworks; GitHub/portfolio links in Skills section
- Business/Finance: Software proficiency (Excel, SAP, Salesforce); certifications (CPA, CFA, PMP)
- Healthcare: Licenses, specific systems (Epic, Cerner); compliance keywords (HIPAA)
- Marketing: Platform expertise (HubSpot, Google Analytics); channel keywords (SEO, PPC)

## Implementation Checklist

1. Scan current resume for ATS compatibility issues
2. Analyze job description for required keywords
3. Calculate current match score
4. Identify specific missing keywords
5. Suggest exact placements for new keywords
6. Flag formatting problems
7. Provide before/after examples
8. Re-score after suggested changes
9. Verify file format and naming
