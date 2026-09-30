# Day 10 notes

# Things covered
- Protecting branches
- Classic Rule based protection 
- newer Ruleset protection
- both work on public repos, provate repo protection needs paid plan
- create rules to protect branches from merges
- can set default branch so main is protected from accidental merges
- needs PR to merge can be turned on
- needs test passing or CI passing to merge can be turned on
- if test fail, PR will not allow merge, closing will move pr status to closed and not merged.
- add exempt team/role/id to have them be exempt from these rules
- add CODEOWNERS under .github so it looks at who owns what module and adds them as approvers by default for merges in these areas
- solo developers skip "require review from CODEOWNERS" in rulesets because all PRs will be blocked as PR does not allow approval by self.
- fail-fast is an option in CI worflow yml that can be turned on/off so all scheduled tests fail upon any one failing first and is not waiting for all runs. 
gh pr --merge --auto queue PR to merge after CI passes --admin flag - allows admin override of pr merge even with failures