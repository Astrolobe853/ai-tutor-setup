# Obsidian Vault Architecture Prompt

Use this prompt with an AI (like Claude or GPT-4) to help you design the linking structure for your study vault based on your specific course syllabus.

***

**Prompt for the AI:**

"I am setting up an AI-powered study vault in Obsidian based on the 'AI Study Workflow' template. I need you to act as an expert Knowledge Architect to help me map out my course structure.

**My Goal:** Create a system of 'Hubs' and 'Topics' that allow for high-level navigation and detailed study notes, which an AI tutor can then use to guide me.

**Here is my syllabus/list of topics:**
[INSERT YOUR SYLLABUS, COURSE OUTLINE, OR LIST OF TOPICS HERE]

**Please perform the following steps:**

1. **Categorization**: Analyze the provided material and group the topics into 3-5 broad 'Hubs' (major themes or units).
2. **Topic Mapping**: Under each Hub, list the specific 'Topics' (individual concepts, lectures, or chapters) that belong there.
3. **Linking Strategy**:
    - Define a `Main Index` that links to all the Hubs.
    - For each Hub, suggest which other Hubs it should link to (cross-references).
    - Suggest which Topics are prerequisites for others.
4. **File Blueprint**: Provide a list of all the Markdown files I should create, formatted as:
    - `Indices/Main Index.md`
    - `Hubs/[Hub Name].md`
    - `Topics/[Topic Name].md`
5. **Template Implementation**: For the `Main Index` and one sample `Hub`, provide the actual Markdown code for the links so I can copy-paste them into Obsidian.

Please be logical, hierarchical, and ensure the structure is intuitive for both a human and an AI agent reading the files."
