# General-AI-Tools
Code repository for skills, agents, steering files, documentation and more.


# Documentation
### Claude Code
 - Skills: https://code.claude.com/docs/en/skills#configure-skills

# Videos
- 2026 AI Workflow: https://www.youtube.com/watch?v=-QFHIoCo-Ko
- https://www.youtube.com/watch?v=vy7o1g2iHY8

# Agents

## What Are Agents?
- Agents are full configuration profiles that define how a agent behaves, what tools it can use, and what context the LLM have access to.
 - They are managed by a JSON file which takes a prompt, tools, tool settings, mcp servers, hooks, and resources.
 - Agents can use one skill but have additional configs above or multiple skills to perform more procedural tasks. 
  
# Skills

## What Are Skills?
- Skills are the procedural memory of agents, these can be stand-alone to perform a task, or they can be grouped with other skills in an agent to perform procedural tasks.

# When to use an Agent vs a Skill
- Agents should be used when you need a fundamentally different mode of operation - different tools, perms, system prompt. Examples of this are a read-only code review agent oir a full-stack development agent (both are large procedural tasks)
- Skills should be used when you want to give an agent access to domain knowledge or guidelines that should be consulted contextually.

- TLDR; Agents are configurabvle and can perform multi-steped tasks, skills can perform multi-step tasks within their context or domain, but agents can chain multiple skills together.

# AI Skills

### Plan Understanding

**About the skill:**
Helps the agent understand the user's request before making changes. The agent should restate the goal, confirm feature expectations, and use available codebase context when possible. If the intent is unclear or the codebase does not provide enough context, the agent should ask the developer for clarification before proceeding.

**Useful for:**

* Understanding feature requests
* Aligning on expected behavior
* Creating better implementation plans
* Reducing incorrect assumptions
* Using existing codebase context before asking questions

---

### Recently Changed Code Awareness

**About the skill:**
Helps the agent detect code that was recently added or changed during AI-assisted work. The agent can identify new helpers, patterns, utilities, technologies, or architectural decisions and update the appropriate skill files so future sessions are aware of them.

**Example:**
If a new utility file is added that contains many hard-coded strings, the agent could recognize that this file should be tracked by a `common-language` skill.

**Useful for:**

* Tracking new files and patterns
* Updating skill documentation automatically
* Keeping project knowledge current
* Noticing new utilities, helpers, or React patterns
* Maintaining consistency across future AI sessions

---

### Common Language

**About the skill:**
Defines shared language, naming conventions, terminology, and files that should be watched for hard-coded strings or repeated copy. This skill helps the agent understand how the codebase communicates concepts and where language-related updates may need to happen.

**Useful for:**

* Shared terminology
* UI copy consistency
* Hard-coded string detection
* Naming conventions
* Updating language-sensitive files

---

### Refactor Planning

**About the skill:**
Helps the agent discuss refactoring opportunities with the developer before modifying code. The agent should suggest patterns for restructuring or optimizing code while preserving existing behavior. Once a direction is agreed on, the agent can execute the changes.

**Useful for:**

* Preserving behavior during refactors
* Avoiding unnecessary rewrites
* Improving naming
* Extracting repeated logic
* Simplifying complex code
* Restructuring files or components

---

### Database Design

**About the skill:**
Helps the agent work with database models, schema changes, migrations, and query patterns. This skill should account for backwards compatibility, clean architecture layers, Prisma usage, and the impact of schema changes across the application.

**Useful for:**

* Model design
* Prisma schema updates
* Database migrations
* Backwards compatibility
* Query consistency
* Checking schema change impact
* Keeping database logic in the correct layer

---

### Documentation Updates

**About the skill:**
Helps the agent keep project documentation up to date as the codebase changes. This can include updating a `documentation.md` file, documenting API routes, writing feature overviews, explaining setup steps, and capturing known gotchas.

**Useful for:**

* Feature overviews
* Setup steps
* Architecture notes
* API contracts
* Known gotchas
* Testing instructions
* Route-level documentation
* Application-level documentation



# Agents
