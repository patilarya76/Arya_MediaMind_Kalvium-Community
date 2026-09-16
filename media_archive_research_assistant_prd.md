# Product Requirements Document (PRD)

## Product Name
**Media Archive Research Assistant**

## 1. Problem Statement

A media company has decades of articles, interview transcripts, and archived footage notes. Journalists struggle to quickly find relevant historical information while working on developing stories.

The product should allow journalists to **search the company's archive using natural language**, retrieve relevant historical context, and see **accurate source attribution** for every piece of information.

## 2. Goal

Build an internal research assistant that helps journalists:

- Find relevant historical content quickly.
- Understand the background/context of a developing story.
- Verify information against original sources.
- Easily identify where each piece of information came from.

## 3. Target Users

### Primary User
**Journalists / Reporters**

### Secondary Users
- Editors
- Researchers
- Archive teams

# 4. Core Functionalities

## 4.1 Archive Upload & Indexing

The system should allow authorized users to upload/archive:

- Articles
- Interview transcripts
- Footage notes
- PDFs/documents
- Text files

For each document, store metadata such as:

- Title
- Date
- Author
- Source/publication
- Content type
- URL/file reference

The system should process and index the content for search.

## 4.2 Natural Language Search

Journalists should be able to search the archive using questions rather than exact keywords.

**Example:**

> "What happened during the 2019 protests in Mumbai?"

The system should return relevant:

- Articles
- Interviews
- Footage notes
- Historical events

## 4.3 Contextual Answer Generation

The system should generate a concise answer based **only on retrieved archive content**.

Example:

> **Background:**  
> The protests began in June 2019 following...

The answer should include relevant historical context instead of requiring the journalist to read dozens of documents.

## 4.4 Source Attribution

Every generated claim should have a source reference.

Example:

> The protests began in June 2019 and continued for three weeks. **[Source 1]**

Sources should display:

- Article/document title
- Author
- Publication date
- Source type
- Link or archive reference

Journalists should be able to open the original source.

## 4.5 Search Results

Along with the generated answer, show the underlying documents.

Example:

**Relevant Sources**

1. *Mumbai Protests Enter Third Week* — June 18, 2019
2. *Interview with Protest Leader* — June 21, 2019
3. *Archive Footage Notes: Mumbai, 2019* — June 25, 2019

## 4.6 Source Verification

Journalists should be able to click a citation and see the **exact relevant passage** from the original document.

This helps prevent:

- Misinterpretation
- Hallucinated information
- Incorrect attribution

## 4.7 Filters

Search results should be filterable by:

- Date/year
- Content type
- Author
- Publication/source
- Topic

Example:

> Search: `India-China border conflict`

Filters:

`2010–2020` | `Articles` | `Interviews`

# 5. Basic User Flow

```text
Journalist enters question
        ↓
System searches archive
        ↓
Relevant documents retrieved
        ↓
AI analyzes retrieved content
        ↓
Answer generated
        ↓
Citations attached to claims
        ↓
Journalist verifies sources
        ↓
Original document/passage opened
```

# 6. Functional Requirements

| ID | Requirement |
|---|---|
| FR1 | Authorized users can upload archive documents |
| FR2 | System extracts and indexes document content |
| FR3 | Users can search using natural-language queries |
| FR4 | System retrieves semantically relevant documents |
| FR5 | System generates answers from retrieved documents |
| FR6 | Every answer must provide source attribution |
| FR7 | Users can view the exact source passage behind a citation |
| FR8 | Users can open the original document |
| FR9 | Users can filter results by date, author, source and content type |
| FR10 | System should clearly indicate when sufficient information is not found |

# 7. Non-Functional Requirements

### Accuracy
The system should prioritize **source-grounded answers** and avoid generating unsupported claims.

### Performance
Search and answer generation should ideally complete within **a few seconds** for normal queries.

### Security
Only authorized employees should be able to access internal archives.

### Scalability
The system should support **millions of archived documents** over time.

# 8. MVP Scope

For the first version, build only:

1. **Document upload**
2. **Document processing/indexing**
3. **Natural-language search**
4. **AI-generated contextual answers**
5. **Citations/source attribution**
6. **Source passage preview**
7. **Basic filters**
8. **User authentication**

### Out of Scope for MVP

- Automated news writing
- Publishing articles
- Social-media monitoring
- Video generation
- Journalist collaboration tools
- Automated fact-checking against the entire internet
- Complex newsroom workflow management

# 9. Success Metrics

The MVP will be considered successful if:

- Journalists can find relevant historical sources significantly faster than manual archive searches.
- Most generated claims have valid source citations.
- Journalists can trace an answer back to the original document.
- Search results are relevant to the journalist's query.
- The system does not present unsupported information as fact.

# 10. Key Product Principle

> **The AI should never be more authoritative than the archive.**

Every generated answer should be **grounded in retrieved company sources, transparent about its evidence, and easy for a journalist to verify.**
