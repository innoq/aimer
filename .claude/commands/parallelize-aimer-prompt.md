# Parallelize AIMER Prompt

## Purpose
Transform a sequential AIMER prompt into a parallelized architecture using specialized sub-agents for improved performance and analysis depth.

## Context
Sequential prompts can often be decomposed into independent analysis tasks that benefit from parallel execution. This meta-prompt creates an orchestrator-agent architecture that maintains AIMER guideline compliance while enabling concurrent processing.

## Instructions

1. Analyze the provided sequential prompt:
   - Identify distinct analysis phases or tasks
   - Determine dependencies between tasks
   - Extract parallelizable components
   - Note consolidation requirements

2. Design the parallel architecture:
   - Create one orchestrator prompt
   - Define 3-6 specialized sub-agent prompts
   - Establish clear data flow between agents
   - Plan consolidation strategy

3. Generate the orchestrator prompt:
   - Follow AIMER prompt structure exactly
   - Reference all sub-agents by filename
   - Define coordination logic
   - Specify output consolidation

4. Create specialized sub-agent prompts:
   - Each focuses on one specific aspect
   - All follow AIMER guidelines
   - Output structured JSON for interoperability
   - Include clear success criteria

5. Design consolidation mechanism:
   - Either as final orchestrator step
   - Or as separate consolidation agent
   - Ensure no information loss
   - Maintain output format from original

6. Validate the parallel design:
   - Check for complete task coverage
   - Verify no circular dependencies
   - Ensure AIMER guideline compliance
   - Test logical flow

## Output Format

Generate multiple prompt files following this pattern:

### Main Orchestrator: `[original-name]-parallel.md`
- Complete AIMER-compliant prompt
- Clear references to all sub-agents
- Coordination instructions

### Sub-Agents: `[original-name]-parallel-[function].md`
- Specialized analysis prompts
- JSON output format
- Specific success criteria

### Example Structure:
```
original-prompt-parallel.md (orchestrator)
original-prompt-parallel-analyzer-1.md
original-prompt-parallel-analyzer-2.md
original-prompt-parallel-analyzer-3.md
original-prompt-parallel-consolidation.md (if needed)
```

## Success Criteria

- All tasks from original prompt are covered
- Each sub-agent has clear, focused responsibility
- No redundant analysis between agents
- Output matches original prompt's format
- All prompts comply with AIMER guidelines
- Parallel execution provides clear benefits

$ARGUMENTS