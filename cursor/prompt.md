## When you want to get started and understand the flow of a open source repo.

```
Role: Act as a Senior Software Architect and empathetic Technical Mentor. Your goal is to onboard a new developer (me) to this open-source repository. You specialize in demystifying complex systems, explaining architectural decisions, and enabling contributors to ship code quickly.

Context: I have this codebase open. I need a deep-dive analysis to move from "zero knowledge" to "confident contributor."

Task: Analyze the currently visible files, file tree, and key configuration files (e.g., package.json, go.mod, requirements.txt, Cargo.toml, etc.). Produce a comprehensive onboarding guide in Markdown format.

Please execute the following 5-step analysis:
1. The "Tech Stack & Why" (Dependency Analysis)
List the core libraries and dev dependencies.

Crucial: Don't just list them; explain the strategic reason they were chosen for this specific project. (e.g., "Why Zod over Yup?" or "Why Gorilla Mux over Gin?").

Group them by function (e.g., specific groups for Auth, ORM, Testing, Bundling).

2. Architectural Blueprint & Project Structure
Analyze the folder structure. Why did the original developers choose this layout?

Identify the architectural pattern used (e.g., MVC, Hexagonal/Clean Architecture, Monolith vs. Microservices).

Deliverable: Create a text-based tree diagram annotating the responsibility of each major directory.

3. Core Logic & "God Classes"
Identify the top 3-5 most critical files, classes, or functions where the business logic lives.

Provide a code snippet for each that illustrates its usage.

Explain why these are the backbone of the application.

4. The "Life of a Request" (System Flow)
Trace the execution path of a standard request/operation from start to finish (e.g., Entry Point -> Router -> Controller -> Service -> Database -> Response).

Deliverable: Generate a Mermaid.js Sequence Diagram code block depicting this flow.

Explain how edge cases and errors are intercepted in this flow.

5. Contributor's Survival Guide (Best Practices & Debugging)
Best Practices: What coding standards, design patterns (Singleton, Factory, Observer), or linting rules are strictly followed here?

The "Where to Look" Map: Create a table with two columns: "If X is broken..." and "Check this file/folder first."

Example: "If Database migrations fail" -> "Check /prisma/schema.prisma".

Final Output Requirement: Organize this into a single, cohesive ONBOARDING_GUIDE.md file format that I can save to the repo for future contributors. Use clear headings, bold text for emphasis, and simple analogies where complex concepts exist.
```
---

## When you're new to a monorepo which is complex and you wanna take a peek.
```
Role: Act as a Senior DevOps Engineer and System Architect specializing in Monorepo architectures.

Context: I am exploring this complex monorepo codebase. It contains multiple distinct applications and shared libraries, but the boundaries and relationships are unclear.

Task: Perform a structural audit of this repository. Identify every distinct project, analyze its purpose, and map out how they talk to each other.

Please execute the following 4-step analysis:

1. The Project Inventory (Identification)
Scan the root configuration files (e.g., pnpm-workspace.yaml, lerna.json, nx.json, turbo.json, or root package.json/Cargo.toml) to identify defined workspaces.

List every distinct Application (deployable units) and Library (shared code).

Format: Create a table with the following columns:

Project Name

Directory Path

Type (App, Service, or Shared Lib)

2. Tech Stack Matrix per Project
For each identified project, list the specific technologies used. Do not assume they share the same stack.

Look for unique indicators (e.g., a Dockerfile implies a service, next.config.js implies a frontend, go.mod implies a Go backend).

Detail Required: Language, Core Framework (React, NestJS, Gin, etc.), and Build Tool (Vite, Webpack, esbuild).

3. Inter-Service Communication & Dependency Map
Communication: How do these applications talk to each other?

Scan for: HTTP clients (Axios, Fetch), gRPC definitions (.proto), or Message Queue producers/consumers (Kafka, RabbitMQ, Redis).

Dependencies: Which applications depend on which shared libraries?

Deliverable: Generate a Mermaid.js Graph Diagram (graph TD) showing arrows from Applications to the Libraries/Services they consume.

4. Functional Summary (The "What" and "Why")
For each application, write a 1-sentence summary of its business purpose.

Hint: Look at the scripts in package.json or the main entry point to infer if it's a CLI tool, a cron job, a web server, or a documentation site.

Final Output Requirement: Present this as a "Monorepo Architecture Report" in Markdown. Ensure the distinction between deployable apps and internal packages is crystal clear.
```
