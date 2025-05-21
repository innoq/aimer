# Hotspot Analysis

## Purpose
Identify high-risk code areas by analyzing the combination of code complexity and change frequency from version control history.

## Instructions
1. Analyze the codebase to calculate code complexity metrics:
   - Cyclomatic complexity of functions/methods
   - Method/class size (lines of code)
   - Cognitive complexity
   - Nesting depth
   - Inheritance depth
   - Number of dependencies
2. Analyze the version control history to determine:
   - Change frequency for each file/component
   - Number of different contributors modifying each file
   - Churn rate (lines added/deleted over time)
   - Recent change patterns (last 3-6 months)
   - Bug fix frequency per file/component
3. Identify hotspots by finding intersections of:
   - High complexity + high change frequency
   - High complexity + high bug fix rate
   - High complexity + many contributors
   - High churn rate + critical functionality
4. For each identified hotspot:
   - Calculate a risk score based on combined metrics
   - Provide specific locations (files, methods, classes)
   - List complexity issues and change patterns
   - Identify potential refactoring opportunities
5. Visualize the results:
   - Create a code hotspot map showing risk concentration
   - Use size to represent size/complexity
   - Use color to represent change frequency
   - Highlight the most critical areas
6. Prioritize hotspots based on:
   - Business criticality of affected functionality
   - Technical risk assessment
   - Potential impact of failure
   - Difficulty of maintenance/modification

## Output Format
Provide a structured report with sections for:

1. Methodology and metrics used
2. Top hotspots identified with risk scores
3. Detailed analysis of each critical hotspot
4. Visualization of hotspot distribution
5. List the glob patterns you used for the whole analysis in a separate chapter,
   to make it easier for a human reviewer to reproduce your approach
6. Provide the proportion of source code files and lines included in the hotspot analysis relative to the total number of source code lines in the application
7. Recommended refactoring and improvement strategies
