# TalTech Curriculum Fit

This stack is tailored to TalTech's `IADB17` IT Systems Development curriculum.

## Program context

- University: TalTech
- Study programme: IT Systems Development
- Study level: Bachelor
- Credits: 180 ECTS
- Valid from: 2025/2026

## Curriculum signals that matter for project design

The provided curriculum emphasizes:

- maintainable code with low maintenance cost
- understanding software development consequences
- practical work both independently and in teams
- common tools, frameworks, and components used in daily development
- data modeling and database technologies
- algorithms and complexity awareness

## Core technical areas reflected in this stack

Associated workflow skills:

- `intake`
- `plan`
- `build`
- `code-quality`
- `deploy`
- `demo`
- `submit`

### Java

Relevant courses:

- `ICD0019` Java
- `ICD0011` Web Programming and Design with Java

Recommended defaults:

- Spring Boot
- Maven
- JUnit
- REST APIs
- server-rendered or API-backed web apps

Associated skill folder:

- `java`

### C#

Relevant courses:

- `ICD0008` Programming in C#
- `ICD0024` Web Applications with C#

Recommended defaults:

- ASP.NET Core
- simple MVC or Web API
- xUnit or NUnit
- SQL Server or SQLite when enough

Associated skill folder:

- `csharp`

### JavaScript and frontend

Relevant courses:

- `ICD0006` JavaScript
- `ICD0026` Advanced JavaScript
- `ICD0007` Web Technologies
- `ICD0018` Hybrid Mobile Applications

Recommended defaults:

- React, Vue, or Angular based on the repo or course context
- Vite for frontend projects
- Vitest or Jest for unit tests
- Playwright for browser verification where needed

Associated skill folders:

- `javascript`
- `react`
- `vue`
- `angular`
- `web-tech`
- `mobile`

### Python

Relevant courses:

- `ICS0019` Advanced Python
- `ICD0023` Programming Microcontrollers with Python

Recommended defaults:

- FastAPI or Flask
- pytest
- virtual environments
- scripts and automation where Python is the natural fit

Associated skill folder:

- `python`

### PHP and web development

The curriculum explicitly includes web technologies and web application work. For PHP-based coursework:

- use Laravel if a framework is expected or allowed
- otherwise keep structure explicit: routing, templates, validation, database access, and tests separated cleanly
- do not build a custom framework for coursework

Associated skill folders:

- `php-web`
- `web-tech`

### Databases, testing, deployment

Relevant courses:

- `ICA0005` Database Basics
- `ICD0004` Automated Testing
- `ICD0029` Container Based Software Deployment

This stack therefore expects:

- sensible schema design
- basic automated testing on the main flow
- deployment that is simple enough for a student team to explain

Associated skill folders:

- `databases`
- `testing`
- `containers`

### Computers, networking, operating systems, and mathematics

Relevant courses and modules include:

- `IAX0043` Computers
- `ICA0019` Fundamentals of Networking
- `ICA0001` Operating Systems and its Management
- mathematics module courses

Associated skill folders:

- `computers`
- `networking`
- `operating-systems`
- `mathematics`

### General studies, internship, and thesis

Relevant modules include:

- General Studies
- Internship
- Final Thesis

Associated skill folders:

- `general-studies`
- `internship`
- `thesis`

## Project selection guidance

A strong TalTech project usually demonstrates several of these together:

- backend logic
- UI or API usability
- persistence
- testing
- documentation
- deployment

It does not need to demonstrate every technology in the curriculum at once.

## Anti-patterns for this curriculum

- over-engineered microservices
- untestable demo-only code
- hidden setup steps
- undocumented environment requirements
- copying trendy architecture without understanding it
- using a framework the team cannot defend orally
