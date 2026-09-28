# Day 08 notes on GitHub Actions and Pages

# Things covered
- Pages to host publich site from within a repo
- while repo is private, page is public (unless on enterprise plan which gives an option to make it private)
- GitHubActions governs workflows
- Workflow can be launched 
    - on: dynamic(Git Hub's built-in hidden deploy)
    - On : push <branch> 
    - on : workflow dispatch - manually triggered

- terms in workflow - job, uses(pre built actions) , run (shell command)
- Also, set automatically delete head branches to delete branch after PR merge