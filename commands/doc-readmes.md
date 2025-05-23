# Documentation READMEs

You are tasked with creating a system of README files to improve the navigation of a project's documentation. The main README file already exists, but you need to create additional README files in the docs directory and its subdirectories to facilitate easy navigation through the documentation structure.

Your task is to create README.md files in the docs directory and its immediate subdirectories. These README files should contain links to the subdirectories and documents within them, using relative paths to ensure compatibility with GitHub's rendered markdown.

Follow these steps:

1. Locate the main README file for this project.
2. Localte and analyze the structure of the documentation directory.
3. For each directory in the docs structure (including the root docs directory), create a README.md file.
4. In each README.md file:
   a. Start with a brief description of the current directory's purpose.
   b. List all subdirectories and files in the current directory.
   c. Create relative links to each subdirectory and file.
5. Use relative paths for all links. For example:
   - To link to a file in the same directory: `[File Name](file-name.md)`
   - To link to a subdirectory: `[Subdirectory Name](subdirectory-name/)`
   - To link to a file in a subdirectory: `[File Name](subdirectory-name/file-name.md)`
6. In the main README.md file (in the project root), add a link to the docs directory: `[Documentation](docs/)`

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

Remember to create README.md files only for the docs directory and its immediate subdirectories, not for deeper levels of the directory structure.

$ARGUMENTS
