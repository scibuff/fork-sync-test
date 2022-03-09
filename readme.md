# Fork Sync Test

Make a 'private' fork of this repository using the following commands

```bash
git clone --bare https://github.com/scibuff/fork-sync-test.git fork-sync-test
cd fork-sync-test

git push --mirror <private repo>

cd ..
rm -rf fork-sync-test

git close <private repo> fork-sync-test
cd fork-sync-test

git remote add upstream https://github.com/scibuff/fork-sync-test.git
git remote set-url --push upstream DISABLE

git remote -v
```

Then:
- create a new file, commit it and push changes to origin
- create a different file in the upstream, commit it and push changes to upstream
- sync the local repo with upstream (resolving any conflicts)
- push changes to origin
