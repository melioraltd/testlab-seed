# Project bootstrap

This gives instructions on how to init the project by generating the missing Specifications for existing codebase.
    
## Specification guidelines

Specifications on what the App does should be documented in Testlab ALM via MCP ("testlab").

The principle:

- AGENTS.md: HOW to work (tools, commands, workflow instructions, ...)
- Specification in Testlab ALM: WHAT to build (business requirements, App logic, UI wireframes, Look and feel, high-level non-functional requirements)

## How to bootstrap the project
   
The project is missing the maintained documented specification (the WHAT). The goal is to generate this specification from this existing codebase.
                                                                                                              
Make a plan of the following:

1. As basis of the specification and how to construct the specification, fetch the specifications and inspect the project "SEED" from Testlab. It acts as seed data for the spec.
2. Go through the SEED specification and learn how the specification should be generated from the codebase.
3. Analyze the content in the codebase thoroughly to figure out the requirements needed for the specification. You can ask the user for clarifications if it is needed for figuring out the requirements. Use High Effort for this step as it is the most important aspect of the bootstrap: it is imperative to analyze the codebase thoroughly and document all functions and features in the generated spec.
4. Create a .spec/ directory to the project root (stop and ask the user to remove it if it already exists).
5. By following the structure of the SEED project (step 1), in the .spec/ folder, for each requirement you think the system or App needs,
   - Create a directory named "requirementId - requirement name",
   - Write a meta.json file in each requirement folder - See 'About meta.json files' below for the format,
   - Write the description of the requirement to description.html file in each requirement folder, use simple HTML syntax similar to the SEED project content,
   - Document the sub-requirements needed with the same logic by following the instructions in the SEED project. Create a tree of directories so that sub-requirements are created in the folder of their parent. Do not document sub-requirements and their ids to description content: As the spec is a tree, always document sub-requirements as children to the appropriate parent. 
6. Use 'bootstrap_project' Tool via MCP to create a new project to Testlab with the generated specification.
7. If successful, remove the created .spec/ directory and the zip file.
8. Ask the developer to review the plan and execute it if allowed.

Use UTF-8 encoding for generated files.

### About meta.json files
     
meta.json file documents the metadata for the requirement in the folder it is in. The file is optional. The structure is:

{
  class: 'classification of the requirement'
}

Supported values in this file are:

- class: Sets the type of the requirement. Always determine this from the SEED project content and if you cannot, pick one of the default values: "Folder", "Requirement", "User Story", "Epic". 
