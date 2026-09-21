# Student Information Agent

A Gemini-powered LangChain agent that answers student-related questions by dynamically selecting the appropriate tools.

## Project Overview

This project demonstrates a tool-based AI agent using Gemini and LangChain. The agent receives a student-related question, decides which tools are needed, uses the tools, and then produces the answer.

The project uses SQLite to store student information and marks.

## Tools

The agent has five tools:

1. `get_student_info(student_id)` - Gets the student's name and department.
2. `get_student_marks(student_id)` - Gets marks in Python, Database, AI, and Web.
3. `calculator(expression)` - Performs numerical calculations such as total and average.
4. `get_passing_rules()` - Returns the university passing requirements.
5. `get_class_statistics(query)` - Handles class-level statistics such as subject averages, department counts, and highest marks.

The fifth tool is an extension to the required four tools.

## How It Works

The agent does not follow one fixed sequence of tool calls.

```text
User Question
      ↓
Gemini reads the available tools
      ↓
Selects the required tool(s)
      ↓
Receives tool results
      ↓
Uses additional tools if needed
      ↓
Returns the final answer
