You are tasked with creating a system of README files to improve the navigation of a project's documentation. The main README file already exists, but you need to create additional README files in the docs directory and its subdirectories to facilitate easy navigation through the documentation structure.

Here is the content of the main README file:

<readme_content>
{{README_CONTENT}}
</readme_content>

And here is the structure of the docs directory:

<docs_structure>
{{DOCS_STRUCTURE}}
</docs_structure>

Your task is to create README.md files in the docs directory and its immediate subdirectories. These README files should contain links to the subdirectories and documents within them, using relative paths to ensure compatibility with GitHub's rendered markdown.

Follow these steps:

1. For each directory in the docs structure (including the root docs directory), create a README.md file.

2. In each README.md file:
   a. Start with a brief description of the current directory's purpose.
   b. List all subdirectories and files in the current directory.
   c. Create relative links to each subdirectory and file.

3. Use relative paths for all links. For example:
   - To link to a file in the same directory: `[File Name](file-name.md)`
   - To link to a subdirectory: `[Subdirectory Name](subdirectory-name/)`
   - To link to a file in a subdirectory: `[File Name](subdirectory-name/file-name.md)`

4. In the main README.md file (in the project root), add a link to the docs directory: `[Documentation](docs/)`

Here's an example of what a README.md file in a subdirectory might look like:

```markdown
# Subdirectory Name

This directory contains documentation related to [brief description].

## Contents

- [File 1](file1.md)
- [File 2](file2.md)
- [Subdirectory 1](subdirectory1/)
- [Subdirectory 2](subdirectory2/)

[Back to parent directory](../)
```

Your task is to create these README.md files for the docs directory and its immediate subdirectories, ensuring easy navigation through the documentation structure. Make sure to use relative paths for all links so that they work correctly when rendered on GitHub.

Provide your answer in the following format:

<answer>
[Your created README.md files, with clear indications of which file goes in which directory]
</answer>

Remember to create README.md files only for the docs directory and its immediate subdirectories, not for deeper levels of the directory structure.
