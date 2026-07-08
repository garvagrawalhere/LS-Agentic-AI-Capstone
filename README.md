# Week 4 Capstone – Multi-Agent Resume Tool
### Garv Agrawal
### 23B0360
### Note: This code was written in **Colab**.

This is my solo capstone project for the Agentic AI Learners' Space bootcamp.

The project takes rough, unstructured resume text as input and uses multiple AI agents to convert it into a cleaner Markdown resume. It also performs a simple ATS keyword check and suggests any important technical keywords that are missing.

## Workflow

The project is built using the **Supervisor orchestration pattern** in LangGraph with a shared state dictionary.

The workflow is:

1. The user enters raw resume text.
2. The supervisor routes the request to the **Formatter Agent**, which converts the text into a structured Markdown resume.
3. The supervisor validates the output. If the formatting check fails (missing Markdown headers), it retries the formatter once.
4. After successful formatting, the supervisor sends the resume to the **ATS Analyzer Agent**, which checks for common technical keywords and appends suggestions.
5. Once all steps are complete, the workflow ends and the final resume is displayed.

## Files

- `resume_optimizer.ipynb` – complete implementation of the multi-agent workflow using LangGraph.

## How to Run

1. Open the notebook in Google Colab.
2. Run all cells from top to bottom.
3. Enter your API key in the code if ny doesn't work. I have used API key of openai/gpt-oss-120b model from build.nvidia.com for this project.
4. Paste your rough resume text into the input box in the final cell.
5. The notebook will display the execution of each agent and print the final formatted resume.
