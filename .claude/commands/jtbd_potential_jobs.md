You are an expert tasked with identifying potential jobs-to-be-done (JTBDs) that a specific product enables for an end-user.

**End User:** {{end_user}}
**Product:** {{product}}
**Number of JTBDs to generate:** {{n}}

**Instructions:**

1. Analyze the provided {{end_user}} and their likely needs, motivations, and context.
2. Analyze the provided {{product}}, its features, and its intended use.
3. Apply the MECE principle (Mutually Exclusive, Collectively Exhaustive) to ensure the JTBDs are distinct and cover all relevant needs.
4. Generate approximately 80% functional jobs and 20% experiential jobs from the total of {{n}} JTBDs.
5. Do not use adjectives or adverbs in the job statements.
6. Format each JTBD with a bold name followed by "The ability to..." and a detailed explanation.

**Verbs for Functional Jobs (use for approximately 80% of the output):**
• Accessing • Adjusting • Allocating • Automating • Building • Calculating • Capturing • Changing • Combining • Comparing • Connecting • Creating • Decreasing • Deleting • Delivering • Deploying • Developing • Eliminating • Extracting • Formulating • Gathering • Generating • Increasing • Integrating • Launching • Loading • Locating • Migrating • Modifying • Monitoring • Organizing • Preparing • Preventing • Prioritizing • Protecting • Reducing • Removing • Restoring • Retrieving • Sharing • Transferring • Transporting

**Verbs for Experiential Jobs (use for approximately 20% of the output):**
• Adapting • Anticipating • Choosing • Deciding • Empathizing • Envisioning • Experiencing • Feeling • Foreseeing • Imagining • Sensing • Visualizing

**Output Format:**

**{First JTBD Name}**
- The ability to... (Detailed explanation of the job, tailored to the {{end_user}} and {{product}})

**{Second JTBD Name}**
- The ability to... (Detailed explanation of the job, tailored to the {{end_user}} and {{product}})

...(continue until {{n}} JTBDs are generated)

**Output Path:**
• Save your analysis as a markdown file to: docs/domain/jtbd/potential_jobs.md