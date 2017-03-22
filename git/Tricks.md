### Retroactively deleting git ignored files from repository

```
git rm --cached `git ls-files -i --exclude-from=.gitignore
```

```
(Windows)
git ls-files -i --exclude-from=.gitignore | xargs git rm --cached
```

---

### git submodules

What:
* Attach external repositories to current repository
* External repository has independent VCS, not affected by current respository

How:

```
git submodule add <git@github ...> lib/my-lib/
```

---

### Fixing stuff on a commit stuck in CI (i.e. Jenkins)not made by you

* `git add .`
* `git stash`
* `git checkout [commit hash]`
* Fix stuff
* `git commit --amend`
* `git push REFS/FOR/[BRANCH]` (if CI==Jenkins)
* `git checkout [previous branch]`
