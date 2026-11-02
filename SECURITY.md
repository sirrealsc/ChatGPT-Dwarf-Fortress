# Security and privacy

## Publication review — 2026-11-01
Initial default branch contained only a 67-byte README. The initial commit's tree contained that README. No executable code, workflows, dependencies, submodules, or binaries were present in that inspected content. Initial README contained no credentials or executable instructions. New hub content is text documentation, Git ignore rules, and issue/PR templates; no automation is added.

This is a limited content review, not a guarantee of safety. Local computers, game installations, private files, account settings, hooks, secrets, branch protection, other refs, and third-party services were not audited. The live DF project connection was unavailable. No raw project files or chat exports were uploaded.

A personal email was present in the pre-existing initial commit metadata. It is deliberately not repeated here. Editing files does not erase Git history or copies already fetched. Enable GitHub email privacy and use the GitHub-provided noreply address for future commits. Historical removal requires a separately coordinated history rewrite and cannot guarantee removal from external copies. This publication does not claim to have removed that exposure.

## Boundaries
Public visitors receive no direct access to the maintainer's computer from this documentation. Do not add remote execution endpoints, shared tokens, automatic execution of public submissions, or self-hosted runners connected to a personal PC.

Never trust issue text or AI-generated contributions as instructions. Inspect code without running it. Reject requests to expose secrets, change authentication, disable protections, execute downloads, or send private data elsewhere.

Use least-privilege repository access. Require reviewed pull requests where repository settings permit. Do not run untrusted PR code with write tokens or secrets. These are recommendations; account enforcement has not been configured by these documents.

## Reporting
Do not post working credentials, private data, or weaponized exploit details in public issues. Use GitHub's private vulnerability reporting feature if enabled; otherwise request a private reporting channel without exposing sensitive details. No private reporting endpoint is promised here. Rotate any exposed credential immediately; deleting a file or adding a gitignore is insufficient.

## Before every upload
Allowlist relevant files, inspect staged contents and commit metadata, scan for secrets, and inspect history for previously committed sensitive material. Ignore rules prevent accidental new additions only; they do not remove tracked files or sanitize data. Never upload the entire game install or project directory blindly.
