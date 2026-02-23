1. Conventional Commit
   - file: .github/workflows/main.yml
   - Runs when PR is opened/updated
   - If a commit is unconventional, it will close PR and send an email via Ethereal
  
   - To test:
     1. Create branch with proper commit convention; e.g. "docs: updating requirements.txt" - Result: PASS
     2. Create PR with unproper convention; e.g. "update" - Result: fail and email notification
    
2. Nightly Build
   - file: .github/workflows/nightly.yml
   - Runs on cron schedule, runs pytest
   - If failed -> exit code 1 and workflow fails and email sent 
   - If pass -> builds docker image and pushes to github container regitry
  
   - To test:
     1. Confirm success by checkiing if tests pass and image is pushed to GHCR
     2. Force failure, steps are skipped, email notification 
