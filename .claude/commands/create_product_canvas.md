# Interactive Product Canvas Menu

This command helps you select which type of product canvas you want to create. Each canvas serves a different purpose in your product development process.

## Available Canvas Types

1. **Lean Product Canvas** - Creates a comprehensive product strategy document that identifies business problems, outcomes, users, solutions, and hypotheses.

2. **Lean Strategy Canvas** - Focuses on your 12-18 month strategy with goals, obstacles, strategic approach, and OKRs.

3. **Hypothesis Prioritization Canvas** - Helps evaluate and prioritize product hypotheses based on value and risk.

4. **Hypothesis Tests** - Designs experiments to validate your prioritized hypotheses.

5. **OKR Roadmap** - Translates your strategic OKRs into an actionable quarterly roadmap.

## How to Choose

Consider these questions when selecting a canvas:
- Are you starting a new product idea? → Lean Product Canvas
- Are you planning your upcoming year strategy? → Lean Strategy Canvas 
- Do you have several features/ideas to prioritize? → Hypothesis Prioritization
- Do you have a specific hypothesis to test? → Hypothesis Tests
- Are you ready to define a quarterly implementation plan? → OKR Roadmap

## Usage Instructions

To use a specific canvas, type one of these commands:
- `/create_lean_product_canvas`
- `/create_lean_strategy_canvas`
- `/create_hypothesis_prioritization_canvas`
- `/create_hypothesis_tests`
- `/create_okr_roadmap`

Each command will guide you through the relevant process step by step.

## Notes

- All canvases allow you to specify file paths to documents that should be read as context before starting
- All canvas outputs will be in German and saved as Markdown documents in the docs/product directory
- Each document will include proper metadata, versioning, and date information