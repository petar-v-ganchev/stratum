# Contributing to Stratum

Thank you for your interest in Stratum. This document explains how you can
contribute — whether that's reporting a bug, requesting a feature, improving
the documentation, or (for open-source components) submitting code.

---

## Stratum is Proprietary Software

Stratum's core extension code is proprietary. We do not currently accept
code contributions to the core plugin. If you are interested in contributing
at an architectural or advisory level, reach out at petar.v.ganchev@gmail.com.

We do accept contributions to:
- This documentation and the docs site
- Open-source components we maintain as separate repositories
- Translations of the documentation

---

## How to Report a Bug

Before reporting, please:

1. **Search existing issues** at
   [github.com/petar-v-ganchev/stratum/issues](https://github.com/petar-v-ganchev/stratum/issues)
   to check whether the bug has already been reported.

2. **Check the known issues** section of [changelog.md](changelog.md) for
   the current release — your issue may already be acknowledged.

3. **Try the latest version** — the bug may already be fixed.

### Reporting a Security Vulnerability

Do **not** open a public GitHub Issue for security vulnerabilities.
See [security.md](security.md) for our responsible disclosure process.

### Opening a Bug Report

Open an issue at
[github.com/stratum-ide/stratum/issues/new](https://github.com/stratum-ide/stratum/issues/new)
using the **Bug Report** template. Please include:

**Required:**
- Stratum version (visible in the status bar or Extensions panel)
- VS Code version (`Help → About`)
- Operating system and version
- The language / framework of the project you were working on
- Steps to reproduce — as specific as possible
- What you expected to happen
- What actually happened
- Whether the issue is reproducible every time or intermittent

**Helpful additions:**
- Screenshots or screen recordings
- The Stratum output log (`View → Output → Stratum` in VS Code)
- Your `.stratum/project.json` (remove any sensitive project names if needed)
- Whether disabling other extensions resolves the issue

**Please do not include:**
- Your source code
- Credentials or API keys
- Personal or sensitive business information

---

## How to Request a Feature

Open an issue using the **Feature Request** template at
[github.com/stratum-ide/stratum/issues/new](https://github.com/stratum-ide/stratum/issues/new).

A good feature request describes:
- **The problem you are trying to solve** — not the specific solution you
  have in mind. We may have a better way to solve the underlying problem.
- **Your role** — are you a Developer, Product Owner, or Viewer? This helps
  us understand the context.
- **How you currently work around the problem**, if at all.
- **The impact** — is this blocking your workflow, or would it be a nice
  improvement?

Feature requests are triaged weekly. We label them and add them to our
public roadmap at docs.stratum.dev/roadmap when they are accepted.

We cannot commit to timelines for specific features, but we read every
request and they directly influence our roadmap priorities.

---

## Improving the Documentation

The Stratum documentation site at docs.stratum.dev is built from the
`/docs` directory in this repository using [Docusaurus](https://docusaurus.io/).

To suggest a documentation improvement:
- Open an issue with the **Documentation** label
- Or open a pull request directly against the `/docs` directory

Documentation pull requests are reviewed and merged by the Stratum team.
We accept contributions to documentation from all users — you do not need to
be a Developer or have any specific technical background to improve the docs.

### Documentation Style Guide

- Write for the audience of each page. The Scenario authoring guide targets
  Product Owners. The HRSG reference targets Developers. Use the vocabulary
  appropriate for each audience.
- Avoid jargon specific to Stratum's internal architecture (HRSG, VCT, VDB)
  in pages targeted at Product Owners or Viewers.
- Use plain English. Short sentences. Active voice.
- Include concrete examples wherever possible.
- Code examples should be minimal — the smallest example that demonstrates
  the point.

---

## Questions and Discussion

For general questions about using Stratum:

- **GitHub Discussions:**
  [github.com/petar-v-ganchev/stratum/discussions](https://github.com/petar-v-ganchev/stratum/discussions)
  — for open-ended questions, sharing how you use Stratum, and community
  conversation.

- **Support:** petar.v.ganchev@gmail.com — for issues specific to your
  subscription or account.

- **Sales:** petar.v.ganchev@gmail.com — for enterprise-specific questions
  about SSO, private deployment, or custom contracts.

Please do not use GitHub Issues for general questions — Issues are for bugs
and tracked feature requests only.

---

## Code of Conduct

All interactions in Stratum's GitHub repository, Discussions, and any other
Stratum community spaces are governed by our Code of Conduct.

In brief: be respectful and constructive. We are here to build good software
together. Harassment, discrimination, or personal attacks of any kind will
result in removal from the community.

To report a code of conduct violation: petar.v.ganchev@gmail.com.

---

## Translations

We welcome translations of the Stratum documentation into languages other
than English. If you would like to contribute a translation:

1. Open an issue with the title "Translation: [Language Name]"
2. We will create a dedicated branch and directory for the translation
3. Translations are reviewed by at least one native speaker before merging

Currently supported documentation languages: English

---

## Acknowledgements

Contributors who improve Stratum's documentation, report valid bugs, or
submit accepted feature requests are acknowledged in our
[release notes](CHANGELOG.md) where appropriate, with their consent.

Security researchers are acknowledged separately — see [security.md](security.md).

---

*Questions about this document? Open a GitHub Discussion or email
hello@stratum.dev.*
