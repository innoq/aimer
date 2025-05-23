# Stakeholder Interview

## Purpose
Systematically gather diverse perspectives to understand the true problems and root causes affecting the system, not just surface symptoms. Build trust while uncovering both known issues and hidden risks.

## Context
Stakeholder interviews are performed early in the review process (Phase 3) to establish a broad understanding before deep technical analysis. They help identify where to focus subsequent investigations and reveal organizational issues that manifest as technical problems.

## Instructions

### 1. Stakeholder Selection
Ensure broad representation across:
- **Development**: Frontend/Backend developers, architects, tech leads
- **Operations**: DevOps, system administrators, support staff  
- **Business**: Product owners, domain experts, key users
- **Management**: Team leads, department heads, C-level (if appropriate)
- **External**: Key customers, partners (if accessible)

Aim for 6-12 interviews to balance breadth with time constraints.

### 2. Interview Structure (45-60 minutes)

#### Opening (5 min)
- Introduce yourself and review objectives
- Emphasize: "No blame culture - we're here to improve the system"
- Assure confidentiality of specific attributions
- Request permission to take notes

#### Core Questions (30-40 min)

**A. General System Perception**
1. "What are the top 3 problems that keep you up at night regarding this system?"
2. "What would you absolutely want to preserve - what works really well?"
3. "If you had a magic wand, what 3 things would you change immediately?"
4. "What causes the most friction in your daily work with this system?"

**B. Root Cause Exploration**
For each problem mentioned:
- "Can you walk me through a specific recent example?"
- "What do you think is the underlying cause of this issue?"
- "How long has this been a problem? What triggered it?"
- "Who else is affected by this? How severely?"
- "What workarounds have you developed?"

**C. Role-Specific Deep Dives**

*For Developers:*
- "Which parts of the codebase do you avoid touching? Why?"
- "Where do bugs cluster? What types recur most?"
- "What slows down your development velocity most?"
- "If you inherited this system today, what would surprise you most?"

*For Architects:*
- "Which architectural decisions cause the most pain now?"
- "Where does the implementation diverge from the intended design?"
- "What quality attributes are we failing to meet?"
- "What would you do differently with current knowledge?"

*For Operations:*
- "What fails most often in production? What's the pattern?"
- "How much of your time is reactive vs. proactive work?"
- "What's missing from our monitoring/observability?"
- "What manual tasks consume the most time?"

*For Business Users:*
- "Where does the system not match your actual workflow?"
- "What features do you need but work around instead?"
- "How does system performance impact your productivity?"
- "What business opportunities are we missing due to system limitations?"

*For Management:*
- "How well does the system support strategic business goals?"
- "What's the business impact of current system issues?"
- "What constraints limit our ability to improve?"
- "How do system issues affect team morale and retention?"

#### Closing (10 min)
- "What haven't I asked about that I should have?"
- "Who else should I definitely talk to?"
- "What documentation or artifacts would help me understand better?"
- Thank them and explain next steps

### 3. Interview Techniques

**When encountering resistance:**
- Use **Pre-Mortem**: "Imagine it's 2 years from now and the system has failed catastrophically. What went wrong?"
- Try **Risk-Storming**: Show a system diagram and ask "Where would you place warning signs?"

**For surfacing hidden issues:**
- "What would a new team member be most surprised by?"
- "What do you explain most often to others?"
- "What's the thing nobody wants to talk about?"

**Active listening signals:**
- Summarize and reflect back key points
- Ask for clarification on technical/domain terms
- Note emotional responses and energy changes

### 4. Analysis Framework

After each interview:
1. **Immediate capture** (within 1 hour):
   - Key problems identified with specific examples
   - Root causes vs. symptoms mapping
   - Emotional intensity markers (what really frustrates people)
   - Connections to previous interviews

2. **Pattern identification** across all interviews:
   - Problems mentioned by 3+ people independently
   - Contradictions between stakeholder groups
   - Consensus areas (both positive and negative)
   - Unique insights from specific roles

3. **Risk assessment**:
   - Business impact (high/medium/low)
   - Technical complexity to fix
   - Organizational readiness for change

## Output Format

### 1. Interview Summary Matrix
| Stakeholder | Role | Key Problems | Root Causes | Preserve | Quick Wins |
|------------|------|--------------|-------------|----------|------------|
| [Name] | Dev Lead | 1. Deployment takes 3h<br>2. No rollback capability<br>3. Flaky tests | Manual processes, fear of automation | Domain model elegance | Automate DB backup step |

### 2. Problem Clustering Analysis
Group related issues across stakeholders:
- **Technical Debt Cluster**: Testing, code quality, architecture drift
- **Process Friction Cluster**: Deployment, communication, handoffs
- **Knowledge Gaps Cluster**: Documentation, onboarding, expertise silos

### 3. Stakeholder Alignment Map
Visualize where groups agree/disagree on:
- Problem severity
- Root causes  
- Solution approaches
- Priorities

### 4. Key Insights Report

#### Consensus Problems (mentioned by 60%+ of interviewees)
1. **[Problem]**: [Specific examples, impact, suggested root cause]

#### Hidden Risks Discovered
1. **[Risk]**: [Who identified it, potential impact, early warning signs]

#### Contradictions Requiring Investigation
1. **[Topic]**: [Group A view] vs [Group B view] - needs deeper analysis

#### Organizational Dynamics Affecting Technical Issues
1. **[Pattern]**: [How organizational issue manifests technically]

### 5. Recommended Focus Areas
Based on interviews, prioritize these areas for deep-dive analysis:
1. **[Area]**: Why critical, which analysis method to use
2. **[Area]**: Why critical, which analysis method to use
3. **[Area]**: Why critical, which analysis method to use

### 6. Actionable Next Steps
- Immediate actions (< 1 week)
- Short-term improvements (1-4 weeks)  
- Strategic initiatives (1-3 months)

## Success Criteria
- Achieved broad stakeholder representation
- Uncovered root causes, not just symptoms
- Identified both technical and organizational issues
- Found consensus on top 3-5 critical problems
- Discovered at least 2 non-obvious risks
- Built trust for ongoing review process
- Clear direction for subsequent technical analysis

$ARGUMENTS