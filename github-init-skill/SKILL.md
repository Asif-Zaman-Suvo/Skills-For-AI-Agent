# Skill: GitHub Repo Initializer

Use this skill whenever the user wants to initialize a new GitHub repository and push it for the first time.

---

## Variables (ask the user before running)

| Variable | Example | Notes |
|---|---|---|
| `REPO_NAME` | _(from user)_ | Repository name; different for each project — parse from the request |
| `ACCOUNT_TYPE` | `personal` or `office` | Determines which SSH host to use |
| `GITHUB_USERNAME` | `Asif-Zaman-Suvo` | GitHub username |

---

## SSH Host Mapping

Based on `ACCOUNT_TYPE`, use the correct SSH alias from `~/.ssh/config`:

| Account Type | SSH Host Alias | Remote URL format |
|---|---|---|
| `personal` | `personal` | `git@personal:USERNAME/REPO_NAME.git` |
| `office` | `office` | `git@office:USERNAME/REPO_NAME.git` |

---

## Commands to Run

```bash
# 1. Create README
echo "# REPO_NAME" >> README.md

# 2. Initialize git
git init

# 3. Stage and commit
git add README.md
git commit -m "first commit"

# 4. Set main branch
git branch -M main

# 5. Add remote — use correct SSH alias
# For personal:
git remote add origin git@personal:GITHUB_USERNAME/REPO_NAME.git

# For office:
git remote add origin git@office:GITHUB_USERNAME/REPO_NAME.git

# 6. Push
git push -u origin main
```

---

## SSH Config Prerequisite

Make sure `~/.ssh/config` has these entries set up:

```
Host personal
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_personal

Host office
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_office
```

---

## Example (filled in)

Substitute the real `REPO_NAME`, `GITHUB_USERNAME`, and SSH host (`personal` vs `office`) before running:

```bash
echo "# <REPO_NAME>" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
# Personal:
git remote add origin git@personal:<GITHUB_USERNAME>/<REPO_NAME>.git
# Office:
# git remote add origin git@office:<GITHUB_USERNAME>/<REPO_NAME>.git
git push -u origin main
```

---

## How to Use in Cursor

When the user asks to create or initialize a new GitHub repo and push it (for example: "initialize a new repo named `my-project` on my personal GitHub account"), do this:

1. **`REPO_NAME`** — Take from the user’s message (the repo / project name they want). It is different for every project; never reuse a name from an old example.
2. **`ACCOUNT_TYPE`** — `personal` or `office`, from what they said or ask if unclear.
3. **`GITHUB_USERNAME`** — From the **Variables** section after you confirm with the user (or their stated handle). Do not assume a fixed username.

Then run the steps in **Commands to Run**, replacing placeholders with those values and choosing the `personal` or `office` `git remote add` line to match `ACCOUNT_TYPE`.
