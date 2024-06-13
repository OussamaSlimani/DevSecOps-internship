# Basic Git and GitHub Commands

---

## 1. git init

Initializes a new Git repository in the current directory.

```sh
git init
```

## 2. git clone

Clones a repository into a newly created directory.

```sh
git clone <repository-url>
```

## 3. git add

Stages changes to be committed.

```sh
git add <file/directory>
```

## 4. git commit

Commits the staged changes to the repository.

```sh
git commit -m "commit message"
```

## 5. git status

Displays the status of the working directory and staging area.

```sh
git status
```

## 6. git push

Uploads local repository content to a remote repository.

```sh
git push <remote> <branch>
```

## 7. git pull

Fetches and integrates changes from a remote repository to the local repository.

```sh
git pull <remote> <branch>
```

## 8. git fetch

Downloads objects and refs from another repository.

```sh
git fetch <remote>
```

## 9. git merge

Merges branches together.

```sh
git merge <branch>
```

## 10. git branch

Lists, creates, or deletes branches.

```sh
git branch
```

## 11. git checkout

Switches branches or restores working tree files.

```sh
git checkout <branch/file>
```

## 12. git log

Shows the commit logs.

```sh
git log
```

## 13. git reset

Resets current HEAD to the specified state.

```sh
git reset <commit/file>
```

## 14. git diff

Shows the changes between commits, commit and working tree, etc.

```sh
git diff
```

## 15. git tag

Creates, lists, deletes or verifies a tag object signed with GPG.

```sh
git tag <tag-name>
```

## 16. git config

Gets and sets repository or global options.

```sh
git config --global user.name "your name"
```

## 17. git rm

Removes files from the working tree and from the index.

```sh
git rm <file>
```

## 18. gh auth login

Authenticates with GitHub from the command line.

```sh
gh auth login
```

## 19. gh repo create

Creates a new repository on GitHub.

```sh
gh repo create <repo-name>
```

## 20. gh release create

Creates a release on GitHub.

```sh
gh release create <tag> <files>
```

## 21. gh repo fork

Forks a repository on GitHub.

```sh
gh repo fork <repo>
```
