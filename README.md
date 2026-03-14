# Stratum

**See the layers beneath your code.**

Stratum is a VS Code and Cursor plugin that makes the hidden structure of your
codebase visible — as interactive, always-in-sync diagrams. Edit the diagram
and your code updates. Edit your code and the diagram updates. Every layer of
your application, always readable, always current.

Built for the whole team: developers who want to understand codebases faster,
product owners who need to describe features without writing code, and
stakeholders who need to read and review without a development environment.

---

## What Stratum Shows You

| Layer | What You See | Who Edits It |
|---|---|---|
| **Logic** | Your state machines as interactive graphs — states, transitions, events, and guards, live-synced with your C#, Java, or TypeScript code | Developers |
| **UI** | Your screens as a live WYSIWYG canvas — components, layouts, and data bindings, synced with your XML, SwiftUI, or JSX | Developers |
| **Scenarios** | Your application's behaviour as plain-English Scenario cards — "When the user logs in…", "If the payment fails…" — authored without code | Developers + Product Owners |
| **Database** | Your schema as a live ERD — entities, columns, relationships, and queries, synced with your ORM entities and migration files | Developers |
| **Data Flow** | The complete path from a database column through a query, through a state variable, to the UI component that displays it — in one click | All roles |

---

## Three Roles, One Codebase

Stratum introduces structured roles directly into VS Code, configured in a
single file committed to your repository.

### 🔵 Developer
Full access to all canvases and the code editor. Developers see the complete
picture — logic graphs, UI layouts, database schemas, queries, and all the
source code they generate from.

### 🟢 Product Owner
Authors Scenarios and configures business rules — thresholds, timeouts,
display text, feature flags — without touching code. Sees all canvases in
read-only mode. Submits Change Proposals for structural changes that require
a Developer.

### ⚫ Viewer
Read-only access to all canvases. Can navigate every screen, read every
Scenario, inspect the database schema, and add comments. No installation of
developer tooling required for the web IDE (coming soon).

Roles are stored in `.stratum/access.json` in your project, resolved from
your `git config user.email`, and committed to version control like any other
project configuration.

---

## Natural Language Input

Describe what you want to build in plain English. Stratum proposes a complete
Scenario — trigger, steps, and outcomes — for you to review and refine.

> *"When the user hasn't logged in for 30 days, end their session and show them
> the login screen with a message explaining why."*

Stratum builds the Scenario structure, wires it to the logic canvas, and
shows you what it will look like — before any code is written.

NL input is available to Developers and Product Owners. It requires explicit
consent before any text is sent to an AI provider. An offline rule-based mode
is always available with no network dependency.

---

## Bidirectional Sync

Every change in a canvas updates your source files. Every change in your
source files updates the canvas. The round-trip target is 300 milliseconds.

```
Edit HRSG canvas → C# / Java / TypeScript state machine updates
Edit state machine code → HRSG canvas updates

Design component on canvas → Android XML / SwiftUI / JSX updates
Edit layout file → Canvas re-renders

Author Scenario → HRSG sub-graph compiles automatically
```

External editors work too. Edit a file in another tool while Stratum is open
and the relevant canvas updates within a polling cycle.

---

## Supported Languages and Frameworks

### Logic Layer (HRSG)
- C# — Entity Framework, ASP.NET, Blazor
- Java / Kotlin — Spring Boot, Android
- TypeScript / JavaScript — React, Node.js, Angular, Vue

### UI Layer (WYSIWYG)
- Android — XML layouts, Jetpack Compose
- iOS — SwiftUI, UIKit
- Web — React / JSX, HTML / CSS
- Cross-platform — React Native, Flutter / Dart

### Database Layer (VDB)
- ORM: Entity Framework Core, Hibernate / JPA, Prisma, TypeORM, Drizzle, Room, Drift
- Raw SQL: PostgreSQL, MySQL, SQLite DDL
- NoSQL: MongoDB (Mongoose), Firebase Firestore (schema inference)

---

## Getting Started

### Installation

Search **Stratum** in the VS Code Extensions panel, or install from the
command line:

```bash
code --install-extension stratum-ide.stratum
```

For Cursor:
```bash
cursor --install-extension stratum-ide.stratum
```

### Initialise a Project

Open your project folder in VS Code, then run:

```
Ctrl+Shift+P → Stratum: Initialise Project
```

Stratum creates a `.stratum/` directory in your project root containing:
- `project.json` — project metadata and platform targets
- `access.json` — team roles (you are set as Developer automatically)
- `scenarios.json` — empty Scenario model
- `tokens/design-tokens.json` — default design token set

Commit the `.stratum/` directory to your repository — it is the shared
configuration for your whole team.

### Open a Canvas

```
Ctrl+Shift+P → Stratum: Open Logic Graph
Ctrl+Shift+P → Stratum: Open Scenarios
Ctrl+Shift+P → Stratum: Open UI Canvas
Ctrl+Shift+P → Stratum: Open Schema
```

Or click the **Stratum** icon in the Activity Bar.

### Add a Team Member

Edit `.stratum/access.json`:

```json
{
  "version": "1",
  "defaultRole": "viewer",
  "members": [
    {
      "id": "alice@company.com",
      "displayName": "Alice Chen",
      "role": "developer",
      "addedBy": "you@company.com",
      "addedAt": "2026-03-14T09:00:00Z"
    },
    {
      "id": "carol@company.com",
      "displayName": "Carol Singh",
      "role": "product_owner",
      "addedBy": "you@company.com",
      "addedAt": "2026-03-14T09:00:00Z"
    }
  ]
}
```

Commit and push. Team members see their role-appropriate canvas interface
when they open the project.

---

## Requirements

| Requirement | Minimum Version |
|---|---|
| VS Code | 1.85.0 |
| Cursor | Latest release |
| Node.js (for TypeScript LSP) | 18.0.0 |
| .NET SDK (for C# LSP, optional) | 8.0 |
| JDK (for Java LSP, optional) | 17 |

Language server components are downloaded on first use for each language.
The core canvases (Scenario, HRSG, WYSIWYG, Schema) work immediately after
installation.

---

## Subscription Tiers

TBD

---

## Privacy

Stratum is designed to keep your code on your machine.

- **Source files** — read locally, never transmitted to Stratum's servers
- **Project models** (`.stratum/` files) — stored in your repository, nowhere else
- **NL input** — sent to a configured AI provider only after your explicit consent;
  no source code is ever included
- **Telemetry** — disabled by default; opt-in aggregate usage counts only

[Full Privacy Policy →](https://github.com/petar-v-ganchev/stratum/privacy-policy)

---

## Documentation

TBD

---

## Support

- **Bug reports & feature requests:** [GitHub Issues](https://github.com/petar-v-ganchev/stratum/issues)
- **Questions & discussion:** [GitHub Discussions](https://github.com/petar-v-ganchev/stratum/discussions)
- **Support:** [petar.v.ganchev@gmail.com](mailto:petar.v.ganchev@gmail.com)
- **Sales:** [petar.v.ganchev@gmail.com](mailto:petar.v.ganchev@gmail.com)
- **Security vulnerabilities:** [petar.v.ganchev@gmail.com](mailto:petar.v.ganchev@gmail.com)

---

## License

Stratum is proprietary software. See [LICENSE](LICENSE) for full terms.
The Free tier is free to use indefinitely under the terms of the Free tier
licence. Pro, Team, and Enterprise tiers require a paid subscription.

---

*© 2026 Stratum
