---
tags:
  - guide
  - artificial-intelligence/workflow
  - notes
tier:
  - 4 - Below Average
---

# BRD, PRD, Backlog, Zen MCP and Memory Bank

Reference: https://www.reddit.com/r/ClaudeAI/comments/1lxfll3/comment/n2m6nq4/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button
Type: Workflow

- Backup of Reference
    
    For context, I am an SDE, 7+ years, backend, enterprise.
    
    I have been coding with Cline initially and now switched over to Claude Code. I have built 8 projects using the system I set out below, iterating on this and improving. One project is now in production and we are doing user testing.
    
    I use the following system:
    
    1. Prepare the spec. This is your ideas for the project. Spend some time writing this out - what you want, how you want it, deployment, features, language, frameworks.
    2. Prepare BRD, PRD, Backlog Basically, I stole this guy's templates:
    
    [https://youtu.be/CIAu6WeckQ0?si=_xykOxTFlu9C_iOU](https://youtu.be/CIAu6WeckQ0?si=_xykOxTFlu9C_iOU) Place your spec (that you wrote), BRD, PRD and backlog into your project directory.
    
    3. Go to GitHub, find .cursorrules for a language you want to use. If you cannot find one, look for a typescript one or a golang one, then paste it into chatgpt or Claude and ask it to convert it to the language of your choice. Save it in .clauderules directory, default-development.md 4. Download and set up zen mcp from [https://github.com/BeehiveInnovations/zen-mcp-server](https://github.com/BeehiveInnovations/zen-mcp-server) I cannot describe how good this is. Basically, you start every prompt to Claude code with “In cooperation with zen mcp, do <blah>” It works. Installation is a breeze. I use chatgpt, gemini pro and xai. Results have been nothing short of awesome. 5. Now, you can run /init command. 6. Once done, go to Cline doc page, get the memory bank prompt - [https://github.com/nickbaumann98/cline_docs/blob/main/prompting/custom%20instructions%20library/cline-memory-bank.md](https://github.com/nickbaumann98/cline_docs/blob/main/prompting/custom%20instructions%20library/cline-memory-bank.md) amend it to replace “Cline” with Claude Code (ai) thing in CLAUDE.md. Paste the amended memory bank prompt in the top of CLAUDE.md. 7. Now, create memory-bank directory and tell Claude code to initialise memory bank.
    
    I also make it keep track with .claude-updates as per ideas in point 2 but it is not necessary - it helps me, YMMV.
    
    If you (or anyone else) got any questions - feel free to reach out. I feel that systematising the way you work with CC delivers predictable and awesome results.
    
    I am currently working on an MCP server to provide a "boosted" memory bank with a local ai assistant for better context management but it is not ready yet.
    

[https://github.com/kleneway/next-ai-starter](https://github.com/kleneway/next-ai-starter)

# Steps

1. Manually prepare the project specifications
2. Create the initial documents needed: Business Requirements Document(BRD), Product Requirements Document(PRD) 
    
    https://chatgpt.com/share/67c5ee78-0b94-800d-b467-ceecdbf6ce70
    
    - Backup of ChatGPT Conversation
        
        Below are three "enhanced prompts" tailored to each scenario. Each prompt specifies multiple real-world analytical frameworks and outlines a structured, step-by-step approach. You can copy and paste these prompts directly into your preferred generative AI tool and simply replace the placeholder text (e.g., `<SPECS GO HERE>`) with your actual content.
        
        ---
        
        ## Scenario One
        
        **Goal**: You are a Senior Product Manager creating a **Business Requirements Document (BRD)**. You have high-level product specs and want to translate them into a formal, detailed BRD.
        
        ### Enhanced Prompt
        
        ```
        markdown
        CopyEdit
        You are a Senior Product Manager. Create a comprehensive Business Requirements Document (BRD) based on the high-level specs below.
        
        <SPECS GO HERE>
        
        Follow these steps:
        
        1. **Stakeholder & User Analysis (RACI Matrix + User Personas)**
           - Identify key stakeholders and their roles using a RACI (Responsible, Accountable, Consulted, Informed) matrix.
           - Develop user personas that highlight core needs and pain points.
        
        2. **Value Proposition & Differentiation (Value Proposition Canvas)**
           - Use the Value Proposition Canvas to map out how the product solves user needs and stands out against alternatives.
           - Clearly articulate the unique selling points (USPs).
        
        3. **Business Model & Market Context (Business Model Canvas)**
           - Populate a Business Model Canvas to outline revenue streams, cost structure, partners, and customer segments.
           - Include a brief competitive landscape overview (Porter's Five Forces) to identify major risks or barriers.
        
        4. **Requirements Gathering & Prioritization (MoSCoW)**
           - Translate the high-level specs into clear business requirements.
           - Apply the MoSCoW (Must, Should, Could, Won’t) framework to prioritize these requirements.
        
        5. **Risk & Assumption Analysis (SWOT + Risk Register)**
           - Conduct a mini-SWOT (Strengths, Weaknesses, Opportunities, Threats) analysis to anticipate challenges.
           - Maintain a risk register with mitigation plans for top critical risks.
        
        6. **Success Metrics & KPIs**
           - Propose quantifiable success metrics (e.g., user adoption rate, revenue targets, NPS, etc.).
           - Link each requirement to specific KPIs.
        
        7. **Next Steps & Timeline**
           - Outline high-level milestones and a proposed timeline, factoring in any known dependencies or constraints.
        
        Deliver a final BRD that integrates all these elements in a clear, cohesive format, suitable for both executive review and technical hand-off.
        
        ```
        
        ---
        
        ## Scenario Two
        
        **Goal**: You are a Senior Product Manager creating a **Product Requirements Document (PRD)**. You have an existing BRD and want to convert those business requirements into a detailed product specification.
        
        ### Enhanced Prompt
        
        ```
        markdown
        CopyEdit
        You are a Senior Product Manager. Create a comprehensive Product Requirements Document (PRD) based on the business requirements below.
        
        <BRD GOES HERE>
        
        Follow these steps:
        
        1. **Feature Definition & Prioritization (Kano Model)**
           - Break down the business requirements into specific features.
           - Use the Kano Model to classify features (Basic, Performance, Excitement).
        
        2. **Functional & Non-Functional Requirements**
           - For each feature, define functional requirements (what the feature does).
           - Outline non-functional requirements (performance, security, scalability, compliance) in detail.
        
        3. **User Workflows & Journeys (User Story Mapping)**
           - Construct detailed user journeys by mapping each feature to user goals and tasks.
           - Identify potential bottlenecks or friction points in the user flow.
        
        4. **Technical Feasibility & Architecture (Conceptual Architecture Diagram)**
           - Propose a high-level architecture diagram (e.g., microservices vs. monolith, cloud components, APIs).
           - Discuss technical constraints or dependencies.
        
        5. **Acceptance Criteria (Gherkin Syntax)**
           - Provide acceptance criteria for each feature in a clear “Given-When-Then” format (or a similar structured approach).
           - Ensure each requirement has a testable outcome.
        
        6. **Release Strategy & Timeline (Incremental Roadmap)**
           - Outline how features will be rolled out over multiple releases.
           - Indicate any dependencies, gating factors, or parallel workstreams.
        
        7. **Risk Management & Assumptions (RAID Log)**
           - Maintain a RAID (Risks, Assumptions, Issues, Dependencies) log.
           - Provide mitigation strategies for key risks.
        
        Generate a final PRD that synthesizes these frameworks into a single, detailed product specification ready for development teams.
        
        ```
        
        ---
        
        ## Scenario Three
        
        **Goal**: You are a Senior Product Manager who needs to create a detailed list of **one-story-point stories** based on an existing PRD. Each story should be small, clear, and actionable.
        
        ### Enhanced Prompt
        
        ```
        sql
        CopyEdit
        You are a Senior Product Manager. Create a detailed list of one-story-point user stories based on the following Product Requirements Document (PRD).
        
        <PRD GOES HERE>
        
        Follow these steps:
        
        1. **Epic & Feature Breakdown (User Story Mapping)**
           - Identify the major epics or features from the PRD.
           - Break each feature down into granular steps that can be completed in a single day or less.
        
        2. **User Stories (INVEST Criteria)**
           - Write each user story following the INVEST model (Independent, Negotiable, Valuable, Estimable, Small, Testable).
           - Use the format: “As a [type of user], I want [action], so that [benefit].”
        
        3. **Acceptance Criteria (Clear & Testable)**
           - Provide acceptance criteria for each user story, ensuring it is testable and unambiguous.
           - Example format: “Given [context], when [action], then [expected result].”
        
        4. **Prioritization & Sequencing (WSJF or RICE)**
           - Apply a lightweight prioritization framework (e.g., Weighted Shortest Job First (WSJF) or RICE) to order stories.
           - Include a brief explanation of priority rankings.
        
        5. **Dependency Identification**
           - Note any inter-story or external dependencies.
           - Indicate if certain stories must be completed before others can start.
        
        6. **Quality & Testing Considerations (Definition of Done)**
           - Outline a Definition of Done that includes code review, testing, and documentation updates.
           - Ensure each story can be accepted independently once its criteria are met.
        
        7. **Roadmap Integration**
           - Map the final list of one-story-point stories into sprints or iterations.
           - Clarify how these stories align with the overall release timeline and milestones.
        
        Produce a final, neatly categorized list of one-story-point user stories with acceptance criteria and priorities, ready for a development team to start work immediately.
        
        ```
        
        ---
        
        ### How to Use These Prompts
        
        1. **Copy and Paste**: Take the enhanced prompt you need and paste it into your AI tool.
        2. **Insert Your Data**: Replace `<SPECS GO HERE>`, `<BRD GOES HERE>`, or `<PRD GOES HERE>` with your actual content.
        3. **Generate**: Let the AI do the work by following the frameworks and structure outlined in the prompt.
        4. **Refine as Needed**: Review the output and refine or iterate if something needs more depth or clarity.
        
        These prompts ensure that each final document (BRD, PRD, or user story list) is built upon multiple proven product management and strategic frameworks, resulting in robust, actionable deliverables.
        
3. **Create default-development.md.** Use a reference .cursorrules from Github relevant to the programming language your want to use. You can ask Claude to convert one to the language you want to use in case you can’t find one.
4. **Use Zen MCP**. [Zen MCP](https://www.notion.so/Zen-MCP-22e50704f72a80e290a2dd4f19528849?pvs=21) 
5. Run `/init` command
6. **Use a memory bank prompt**. Append the initialized [`CLAUDE.md`](http://CLAUDE.md) with a memory bank prompt from https://github.com/nickbaumann98/cline_docs/blob/main/prompting/custom%20instructions%20library/cline-memory-bank.md. Create a memory-bank directory(can be `.claude/memory/` and tell Claude code to initialize the memory bank