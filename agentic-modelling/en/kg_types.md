# KG Engineer: Type Validation
Review the Knowledge Graph configuration to identify and fix issues with attribute types. The goal is to ensure all attributes use the correct data types.

# Steps

## 1. Read Knowledge Graph Configuration
Read the relevant VKL files for the Knowledge Graph classes to understand the current structure. Focus on the main class definition files in the knowledge-base folder.

## 2. Analyze Type Issues
Review all attribute types to identify misconfigurations.

For some type issues, you will need to run queries to gather more context. Run these queries first before suggesting changes. For dates in particular, always query for samples and verify the ranges as they can indicate whether a sql transformation is needed.

### 2.1 Numbers that should be classes
Numeric fields that contain categorical codes (e.g., 0=female, 1=male, 2=mixed) rather than actual numeric values
A combination of Numeric Code and Name could be better represented as a class using sql and name_sql. 
Example: Category_Code, Category_Name => Category.

### 2.2 Classes that should be strings
Class attributes containing free-form text (like addresses or comments) rather than a set of categorical values. Use classes for things/people/categories and string for text.

### 2.3 Classes that should be booleans
Classes with only true/false-like values, e.g. 0/1 or No/Yes.

### 2.4 Classes that should be dates
Sometimes a class contain date or datetime values. These may need a sql transformation to be correctly represented as a date.

### 2.5 Integers that should be dates
Sometimes columns that represent years are imported as integer, but we recommend modelling it as date with a datetime_format set to YearFormat instead.

### 2.6 Incorrect date formats or values
Date attributes with wrong granularity settings (e.g. with always 00:00.00 as time) or also in general wrong date values (e.g. starting in year 00XX). Suggest to apply a `sql` transformation to fix it, if it is a consistent mistake.

## 3. Present Findings and Ask for Approval
Organize the identified issues into clear categories and present them to the user in a structured format using tables. For each issue, show the current configuration, the suggested improvement, and the reason for the change. Group findings by category.

Ask for approval to proceed with the changes using a quick answer hyperlink (#suggested-question).

## 4. Apply Approved Changes
Update the VKL files to apply the improvements. Consolidate multiple changes to the same file into efficient edit operations.
