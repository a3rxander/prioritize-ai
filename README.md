# Prioritize AI

Prioritize AI is a smart todo list application that uses AI to help users decide what they should do first.

The main goal of this project is to build a full-stack application using C#, ASP.NET Core, React, TypeScript, and Azure, while practicing real-world backend, frontend, database, and AI integration concepts.

## Main Idea

Most todo list apps help users write down tasks, but they do not help users decide what actually matters.

Prioritize AI allows users to add their tasks, define their available time, energy level, and main goal for the day. Then, the system uses AI to generate a prioritized daily plan.

The app helps answer questions like:

- What should I do first?
- What can wait?
- What should I avoid today?
- What task gives me the most progress?
- How should I organize my day?

## Core Features

### Task Management

- Create tasks
- Edit tasks
- Delete tasks
- Mark tasks as completed
- Organize tasks by category
- Define estimated time, urgency, importance, and energy required

### AI Prioritization

- Analyze all pending tasks
- Recommend the top priorities for the day
- Explain why each task was selected
- Suggest which tasks should be postponed
- Generate a simple daily schedule

### Daily Planning

Users can provide daily context such as:

- Available time
- Current energy level
- Main goal for the day

Based on that, the app generates a focused plan.

## Tech Stack

### Backend

- C#
- ASP.NET Core Web API
- Entity Framework Core
- SQL Server or PostgreSQL
- Clean Architecture principles
- AI service integration

### Frontend

- React
- TypeScript
- Vite
- Axios
- TanStack Query
- React Hook Form
- Zod

### Cloud

- Azure App Service
- Azure SQL Database or Azure Database for PostgreSQL
- Azure Key Vault
- Application Insights

## Project Structure

```txt
prioritize-ai/
  backend/
    src/
      PrioritizeAI.Api/
      PrioritizeAI.Application/
      PrioritizeAI.Domain/
      PrioritizeAI.Infrastructure/

  frontend/
    prioritize-ai-web/

  docs/