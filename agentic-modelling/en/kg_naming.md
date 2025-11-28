# KG Engineer: Naming
Review the Knowledge Graph configuration to identify and improve naming conventions for classes and attributes. The goal is to ensure all concept names are clear, properly formatted, and follow best practices. Present findings to the user and ask clarifying questions before making any changes.

# Steps

## 1. Read Knowledge Graph Configuration
Read the relevant VKL files for the Knowledge Graph classes to understand the current naming structure. Focus on the main class definition files in the knowledge-base folder.

## 2. Analyze Naming Issues
Systematically analyze all class and attribute names, looking for the following categories of issues:
- **Abbreviation issues**: Inconsistent capitalization (e.g., "Bpm" vs "BPM"), unexpanded abbreviations that may be unclear to users
- **Formatting issues**: Incorrect spacing in units (e.g., "d B" vs "dB"), missing punctuation (e.g., "U S" vs "U.S."), separated letters that should be combined (e.g., "T V" vs "TV")
- **Unclear or generic names**: Names that lack context or specificity (e.g., generic "Date" that could be more descriptive)
- **Type-related naming issues**: Attributes where the name doesn't clearly reflect the data type or meaning (e.g., numeric codes that might be mistaken for booleans)
- **Missing descriptions**: Attributes that would benefit from descriptions to explain their meaning

## 3. Present Findings
Organize the identified issues into clear categories and present them to the user in a structured format (tables work well). For each issue, show the current name, the suggested improvement, and the reason for the change.

## 4. Ask Clarifying Questions
Before making any changes, ask the user about unclear points (e.g. unclear technical names or abbreviations). 
Offer hyperlinks (#suggested-question) as quick answers for the questions.
Do not bother the user with irrelevant questions that are a matter of taste.

Always offer an option to skip all questions and follow your own judgement.

## 5. Apply Approved Changes
Once the user provides answers to the clarifying questions, update the VKL files to apply the approved naming improvements. Consolidate multiple changes to the same file into a single edit operation.

# Important Considerations
- Always ask the user for input before making changes to the Knowledge Graph
- When suggesting names, prefer clarity over brevity - users should understand what an attribute means from its name
- Consider adding descriptions to attributes where the name alone may not be sufficient to convey meaning
- Respect the existing code style and structure when making edits
