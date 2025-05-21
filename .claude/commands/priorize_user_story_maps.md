# User Story Prioritization Task

## Objective
Create prioritized CSV files from all existing user story maps.

## Input
- Source: All user story maps located in `docs/product/user-story-maps/`

## Process
1. Extract all user stories from the source files
2. Consolidate duplicate user stories that have the same content on story level
3. Create two separate groups:
    - MVP stories
    - Future release stories
4. Within each group, sort stories to reflect the natural user journey through the product
5. Generate separate CSV files for each group

## The CSV file has the following structure
```
ID,User Activity,User Task,Story,Source
PM001,"Discover & Browse Prompts","Search for prompts","Als technischer Berater möchte ich nach Prompts mit Schlüsselwörtern suchen, damit ich während Kundenmeetings schnell relevante Prompts finden kann","Prompt Management"
```

Where:
- Unique ID (prefix indicates source map: NM=New Member, O=Organization, PM=Prompt Management, PE=Prompt Evolution)
- User Activity: The higher-level user activity/epic (e.g., "Discover & Browse Prompts")
- User Task: The specific task/feature (e.g., "Search for prompts")
- Story: The user story in German format "Als [persona] möchte ich [action], damit [benefit]"
- Source: Origin of the story (e.g., "Prompt Management" User Story Map)

## Output
- File 1: `docs/product/backlog/user-stories-mvp.csv` - Contains all MVP stories in journey order
- File 2: `docs/product/backlog/user-stories-future.csv` - Contains all future release stories in journey order

## Notes
- Sorting should follow user navigation flow from start to finish
- Maintain all metadata and attributes from original user stories