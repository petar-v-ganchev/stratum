# Security Policy

## Reporting a Vulnerability

**Please do not report security vulnerabilities through GitHub Issues, GitHub
Discussions, or any other public channel.** Public disclosure of an
unpatched vulnerability puts all Stratum users at risk.

To report a security vulnerability, email us at:

*petar.v.ganchev@gmail.com*

Encrypt your report using our PGP key if the vulnerability is sensitive.

### What to Include

To help us triage and resolve the issue quickly, please include:

- A description of the vulnerability and its potential impact
- The component affected (Plugin, web properties, API, or specific feature)
- Steps to reproduce — the more specific, the faster we can verify and fix
- Your assessment of severity (Critical / High / Medium / Low)
- Whether you have a suggested fix or mitigation
- Your name and contact details (for credit and follow-up)

You may report anonymously if you prefer, though this limits our ability
to follow up or credit you.

---

## Our Response Commitments

| Severity | Acknowledgement | Status Update | Target Resolution |
|---|---|---|---|
| **Critical** — data exfiltration, remote code execution, auth bypass | 24 hours | Every 48 hours | 7 days |
| **High** — privilege escalation, sensitive data exposure | 48 hours | Every 72 hours | 14 days |
| **Medium** — limited impact, requires user interaction | 72 hours | Weekly | 30 days |
| **Low** — minimal impact, defence-in-depth issues | 7 days | On resolution | 90 days |

These are targets, not guarantees. Complex vulnerabilities may require more
time. We will keep you informed of progress and will not leave you without
a status update for more than the intervals above.

---

## Supported Versions

We provide security fixes for the following versions:

| Version | Supported |
|---|---|
| Latest stable release | ✅ Active security support |
| Previous stable release | ✅ Critical fixes only (90 days after superseded) |
| Older releases | ❌ No security support — please upgrade |

We strongly recommend always running the latest version of Stratum. The VS Code
Extension Marketplace handles updates automatically unless you have disabled
auto-updates.

---

## Scope

The following are **in scope** for responsible disclosure:

- The Stratum VS Code / Cursor extension (stratum-ide.stratum)
- The Stratum web properties: stratum.dev, docs.stratum.dev, app.stratum.dev
- The Stratum account and billing API (api.stratum.dev)
- The Stratum NL interpretation service
- The `.stratum/access.json` role system and any bypass of role controls
- Any component that could allow an attacker to access source code, project
  models, or git identity outside the user's intended scope

The following are **out of scope:**

- Vulnerabilities in third-party AI providers used by the NL input feature
  (report these directly to the provider)
- Vulnerabilities in VS Code or Cursor themselves (report to Microsoft or
  Anysphere respectively)
- Social engineering attacks against Stratum staff
- Physical attacks against Stratum infrastructure
- Denial-of-service attacks against Stratum servers
- Issues that require the attacker to already have Developer-level access to
  the target project (Stratum's role system is a workflow tool, not a security
  boundary — see the Privacy Policy and Terms of Service)

---

## Safe Harbour

Stratum supports responsible security research. We commit that:

- We will not pursue civil or criminal action against researchers who discover
  and report vulnerabilities in good faith under this policy
- We will not refer researchers to law enforcement for good-faith research
- We consider good-faith research under this policy to be authorised and
  will not take action against it under the Computer Fraud and Abuse Act
  (CFAA) or equivalent laws

"Good faith" means: you do not access data that is not yours, you do not
perform denial-of-service testing, you do not exploit a vulnerability beyond
what is necessary to demonstrate it, and you report the issue to us before
any public disclosure.

---

## Disclosure Policy

We follow a **coordinated disclosure** model:

1. You report the vulnerability to petar.v.ganchev@gmail.com
2. We acknowledge receipt and begin investigation
3. We develop and test a fix
4. We release the fix
5. We notify you when the fix is deployed
6. We publish a security advisory (after the fix is deployed and users have
   had reasonable time to update — typically 7 days for critical, 30 days
   for others)
7. You are free to publish your own disclosure after the advisory is public

If you wish to publish your research before we have resolved the issue,
please give us a minimum of 90 days from your report before public
disclosure, and contact us to coordinate timing.

---

## Security Hall of Fame

We gratefully acknowledge security researchers who have reported
vulnerabilities to us in good faith. 

---

## Bug Bounty

Stratum does not currently operate a paid bug bounty programme. We offer:

- Public acknowledgement in our Security Hall of Fame (with your consent)
- A complimentary Pro subscription for the duration of the calendar year
  following a confirmed High or Critical vulnerability report
- A personal thank-you from the team

We are evaluating a formal paid bounty programme for a future release.

---

## Contact

- **Security reports:** security@stratum.dev
- **PGP key:** https://stratum.dev/.well-known/pgp-key.asc
- **Security advisories:** https://github.com/stratum-ide/stratum/security/advisories
- **General enquiries:** hello@stratum.dev

*Last updated: [DATE]*
