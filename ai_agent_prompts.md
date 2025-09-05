# AI Coding Agent Prompts

## Prompt for Claude Code

```
I need you to build a complete Hot Fix Testing AI Agent system based on the detailed project design document in my GitHub repository. This is a multi-agent LangGraph system that will analyze Confluence pages containing Cisco firewall Hot Fix testing reports.

**Project Design Document**: [Your GitHub URL to the .md file]

**Key Requirements**:
- Build Phase 1 (CLI interface) as a complete working system
- Use LangGraph for multi-agent orchestration with GPT-4o and ChromaDB
- Extract customer names, analyze bugs, handle counting/non-counting queries
- All responses must include source page references
- Follow the exact project structure specified in section 5.1
- Implement all 6 agents: Query Router, Data Retrieval, Customer Extractor, Bug Analyzer, Response Generator, Memory Manager
- Start with mock data testing using the sample pages provided, then implement Confluence API

**Critical Implementation Points**:
1. Follow section 12 "Special Instructions for AI Coding Agents" carefully
2. Customer name extraction patterns: "Customer <<name>>" and "Customer name <<name>>"
3. Handle both bug summary tables and test case bug IDs
4. Counting queries need accurate count + mandatory summary + page links
5. Use the test queries in section 12.3.2 for validation

**Configuration I'll provide**:
- OpenAI API Key
- Confluence URL, username, API token, space key

**Deliverables**:
- Complete working CLI system (Phase 1)
- All code properly structured, commented, and modular
- requirements.txt with all dependencies
- README with setup and usage instructions
- Working test suite with the provided sample queries

Please start by setting up the project structure and implementing the core components. Ask me for the API credentials when you need them for testing.
```

---

## Prompt for Google Jules

```
I have a comprehensive project design document for building a Hot Fix Testing AI Agent system. I need you to implement this as a complete working application following the specifications exactly.

**Project Design Document**: [Your GitHub URL to the .md file]

**Project Overview**:
This is a multi-agent system using LangGraph that analyzes Confluence pages containing Hot Fix testing reports for Cisco ASA/FTD firewalls. The system needs to handle customer-specific queries, bug analysis, and generate detailed reports with source references.

**Technical Stack** (as specified in document):
- LangGraph for multi-agent system
- GPT-4o for LLM processing  
- ChromaDB for vector database
- OpenAI text-embedding-3-large for embeddings
- Python with specific libraries listed in section 2.1

**Implementation Priority**:
1. Start with Phase 1 (CLI interface) - build complete working system
2. Follow the exact project structure in section 5.1 
3. Implement all 6 agents as described in section 3.1
4. Use sample data for initial testing (provided in document)
5. Implement Confluence API integration after core system works

**Critical Features to Implement**:
- Customer name extraction with patterns: "Customer <<name>>" or "Customer name <<name>>"
- Bug analysis from both bug tables AND test case bug IDs  
- Counting queries: accurate count + mandatory summary + source links
- Non-counting queries: detailed answers with page references
- Handle temporal filtering (year/date based queries)

**Validation Requirements**:
- Test with all sample queries provided in section 12.3.2
- All responses must include source page URLs
- Must handle "Unable to find answer" cases gracefully
- Follow the validation checklist in section 12.7

**What I'll Provide**:
- API credentials (OpenAI, Confluence) when you need them for testing
- Additional sample data if needed

**Expected Deliverables**:
- Complete Phase 1 CLI system
- Well-structured, commented Python code following the design
- requirements.txt and setup instructions
- Working demonstration with sample queries

Please read the full design document carefully, especially section 12 "Special Instructions for AI Coding Agents", and start building the system. Let me know when you need the API credentials for testing.
```

---

## Additional Tips for Both Agents

### Follow-up Instructions (use if needed):
```
If the agent asks for clarification, provide these additional details:

**Sample Data Context**:
The system analyzes Confluence pages with this hierarchy:
- Parent pages: "Hot Fix Validation 2022–2023", "Hot Fix Validation 2023–2024", "Hot Fix Validation 2024–2025"  
- Child pages: Individual Hot Fix reports for specific customers
- Each child page contains: customer info, bug tables, test case tables, issue descriptions

**Expected Query Examples**:
- "How many Hot Fixes were given to NBP customer?" → Count + summary + links
- "List bugs for HR IND Medical Center in 2025" → Bug table + analysis  
- "Which customer had VPN issues?" → Customer name + page summary

**Key Success Criteria**:
- Accurate customer name extraction from content patterns
- Proper bug analysis (check both bug tables AND test case bug IDs)
- All counting queries include mandatory summaries
- Source page references in every response
```

### Credentials Template (when agents ask):
```
Here are the credentials for testing:

OPENAI_API_KEY = "your_actual_key_here"
CONFLUENCE_URL = "your_confluence_url"
CONFLUENCE_USERNAME = "your_username"  
CONFLUENCE_API_TOKEN = "your_api_token"
CONFLUENCE_SPACE_KEY = "your_space_key"

Test with the sample data first, then integrate with these credentials.
```