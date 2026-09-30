# Notes from Day 06 - forks , clone

Things covered
- Forks
- workflow for forks - Upstream/upstream - Fork to Github bvgitty/upstream - Clone to Local -> branch -> fix -> push to Gh fork -> PR and merge to upstream - delete all branches and git pull origin main
- how to keep a fork in synch : two ways
    -    In GitHub, you can navigate the forked repo and use the Synch Fork button, review the incoming commits and click update branch
    - or, in the commiand line you can,
        - git remote add upstream <url-of-original-repo>
        - git fetch upstream
        - git checkout main
        - git merge upstream/main (or git rebase upstream/main)
        - git push origin main
        - essentially the synch process is upstream -> local -> origin/main


