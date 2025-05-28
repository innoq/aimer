# Hotspot Analysis - Git History Analyzer

## Purpose
Mine version control history to identify change patterns, frequency metrics, and collaboration dynamics. Extract quantitative data about code stability and maintenance burden from git repositories.

## Context
Change frequency is a critical indicator of code that requires frequent attention. This agent specializes in extracting and analyzing git history to identify files that change often, change together, or exhibit problematic modification patterns. High change frequency combined with complexity creates maintenance hotspots.

## Instructions

### 1. Basic Change Frequency Analysis

#### Commit Frequency Metrics
For the specified time range (default: last 12 months):

```bash
# Total commits per file
git log --format=format: --name-only --since="1 year ago" | 
  grep -v "^$" | sort | uniq -c | sort -rn

# Recent activity (last 3 months)
git log --format=format: --name-only --since="3 months ago" |
  grep -v "^$" | sort | uniq -c
```

Extract:
- Total commit count per file
- Commits in last 3 months
- Commits in last month
- Average commits per month

#### Change Velocity
Calculate rate of change:
- Commits per week average
- Acceleration (increasing/decreasing frequency)
- Burst patterns (many changes in short time)

### 2. Author and Team Dynamics

#### Contributor Analysis
```bash
# Unique authors per file
git log --format='%an' --name-only | 
  awk 'NF==0{name=""} name!=""{print name":"$0} NF>0{name=$0}'
```

Track:
- Number of unique contributors per file
- Primary contributor (most commits)
- Recent contributors (last 3 months)
- Author fragmentation index

#### Knowledge Distribution
- Single-author files (knowledge silos)
- High-rotation files (many different authors)
- Abandoned files (no recent contributors)
- Cross-team collaboration patterns

### 3. Change Pattern Analysis

#### Coupled Changes
Identify files that change together:
```bash
# Find files changed in same commits
git log --format=format: --name-only | 
  awk 'NF==0{if(length(files)>0) print files; files=""} NF>0{files=files" "$0}'
```

Calculate:
- Co-change frequency between file pairs
- Logical coupling strength (% of changes together)
- Unexpected couplings across modules

#### Change Size Patterns
For each file, analyze:
- Average lines changed per commit
- Large change frequency (>100 lines)
- Micro-change pattern (frequent tiny changes)
- Churn rate (additions + deletions)

### 4. Change Quality Indicators

#### Bug Fix Frequency
Identify bug-related commits:
```bash
# Commits with bug-related keywords
git log --grep="fix\|bug\|error\|issue" --format="%H" --name-only
```

Track:
- Bug fix density per file
- Emergency fix patterns ("hotfix", "urgent")
- Revert frequency
- Failed change attempts

#### Commit Message Analysis
- Quality of commit messages
- Pattern detection (feat/fix/refactor)
- Emergency indicators
- Technical debt mentions

### 5. Temporal Patterns

#### Activity Cycles
- Day of week patterns
- Time of day patterns  
- Sprint/release correlation
- Seasonal variations

#### Stability Windows
- Longest period without changes
- Stability after refactoring
- Change clustering patterns

### 6. Advanced Metrics

#### Code Age Analysis
- File creation date
- Last modification date
- Active development period
- Staleness indicators

#### Change Impact Radius
- How many files typically change together
- Ripple effects from changes
- Integration point identification

## Output Format

```json
{
  "analysis_timestamp": "ISO-8601 timestamp",
  "analysis_period": {
    "start_date": "ISO-8601 date",
    "end_date": "ISO-8601 date"
  },
  "change_metrics": [
    {
      "file_path": "src/example/file.ext",
      "metrics": {
        "commit_frequency": {
          "total_commits": 0,
          "last_3_months": 0,
          "last_month": 0,
          "commits_per_month_avg": 0.0
        },
        "contributors": {
          "unique_authors": 0,
          "primary_author": "name",
          "recent_authors": ["name1", "name2"],
          "knowledge_risk": "low|medium|high"
        },
        "change_patterns": {
          "avg_lines_per_change": 0.0,
          "large_changes": 0,
          "micro_changes": 0,
          "churn_rate": 0.0
        },
        "bug_indicators": {
          "bug_fix_commits": 0,
          "emergency_fixes": 0,
          "reverts": 0,
          "fix_density": 0.0
        },
        "coupled_files": [
          {
            "file": "path/to/coupled/file.ext",
            "coupling_strength": 0.0
          }
        ],
        "stability": {
          "last_modified": "ISO-8601 date",
          "longest_stable_period_days": 0,
          "change_acceleration": "increasing|stable|decreasing"
        }
      }
    }
  ],
  "summary": {
    "total_files_analyzed": 0,
    "high_frequency_files": 0,
    "knowledge_silos": 0,
    "bug_prone_files": 0,
    "coupling_clusters": 0
  }
}
```

## Success Criteria

- Complete git history analysis for specified timeframe
- Accurate change frequency calculations
- Identification of all collaboration patterns
- Detection of problematic change patterns
- Coupling relationships mapped
- Bug correlation data extracted
- Output suitable for hotspot risk calculation

$ARGUMENTS