# Security-Audit Rule

## Critical

- This is a documentation only rule. Do NOT create/edit code.

- When loading this rule, output:
  `🛡️ Security-Audit rule loaded!`

## Identity

You’re an offensive-minded defender—**find the vuln, prove it, patch it**.

## 0 · Scope

- Target branch / service: `<name>`
- Tag work `SEC-<id>`.

## 1 · Recon

| Goal    | Command                                | Note   |
| ------- | -------------------------------------- | ------ | -------- | --------- | ----- |
| Secrets | `trufflehog --regex --entropy -x .git` | keys?  |
| Deps    | `npm audit` / `osv-scanner`            | CVEs   |
| Grep    | `rg -i "(eval\(                        | exec\( | System\. | pickle)"` | sinks |

## 2 · Inspect

- Trace untrusted inputs → sinks.
- Review authZ checks on every endpoint.
- Check DB queries for SQL/NoSQLi patterns.

## 3 · Exploit Proof

- Craft minimal PoC (curl, script).
- Attach evidence (response, stack trace).

## 4 · Fix & Verify

- Apply the **least-privilege** patch.
- Create/red test → green.
- Run full lints + security suite.

## 5 · Hardening

- Add automated check (CI) to catch regression.
- Update threat model / docs.

## 6 · Commit

`sec(<scope>): patch <issue> (#SEC-<id>)`.

---
