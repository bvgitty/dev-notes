# Day 11 notes on Security features

# Things covered
- Risk #1 - Vulnerable dependencies - A library you use has a known security hole (a "CVE") - Tool: Dependabot
- Risk # 2 - Leaked Secrets - An API key committed to the repository - Tool: Secret scanning and push protection
- Risk # 3 - Bugs in your own code - Unsafe file paths, injection - Tool: Code scanning with CodeQL
- Risk # 4 - Outsiders reporting problems - A researcher finds a hole - Tool: SECURITY.md and private vulnerability reporting
- All results show up under Security tab

- Three Feature of Dependabot
- Dependabot alerts - Warns you that a dependency has a known vulnerability - Settings toggle
- Dependabot security updates - Open a PR that upgrades dependency to a fixed version - A settings toggle
- Dependabot version updates - Opens PRs to keep dependencies current, whether or not they're vulnerable- A .github/dependabot.yml file
- All three rely on the dependency graph (Insights → Dependency graph), which GitHub builds by reading files like requirements.txt and dependabot.yml

- all of this is free for public repo. available for private repos Dependabot is free but secret scan and codeQL in paid plan.

-Turn everything on in Settings - advanced security
Setting	Set to
-Dependency graph	Enabled (probably already on)
-Dependabot alerts	Enable
-Dependabot security updates	Enable
-Secret scanning (may be called Secret Protection)	Enable
-Push protection	Enable (may already be on)
-Code scanning → CodeQL analysis	Set up → Default → Enable CodeQL
Private vulnerability reporting	Enable

- CodeQL ran by Default and found an issue with workflow file CI.yml where we did not provide the permissions for read/write 
- The alert: "Workflow does not contain permissions" (Medium)

CodeQL scans more than Python: it also checked your workflow file, .github/workflows/ci.yml, and flagged line 10.

What it means: every workflow run gets an automatic GITHUB_TOKEN, a temporary key that lets the workflow act on your repository. If you don't say what that token may do, it gets the repository's default permissions, which can include write access. Your CI only reads code to run tests, so it should ask for exactly that. This is the principle of least privilege: if a step in the workflow were ever compromised, a read-only token limits the damage.

- Export SBOM - provides export of software bill of materials from requirements file