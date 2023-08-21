<h1 align="center" style="font-size: 35px">:book: Git Policy :book:</h1>

# Important Git Terminologies

**1. Branch**
Branches represent specific versions of a repository that are separated from your main project.
Branches allow you to track experimental changes you make to the repository and can be reverted to older versions.

**2. Commit**
A commit represents a specific moment in your project's history. Use the commit command along with the git add command to let Git know which changes you want to save in the local repository.

**3. Checkout**
Use the git checkout command to switch between branches. Just enter git checkout followed by the name of the branch you want to switch to, or enter git checkout master to return to the main branch (master branch).

**4. Fetch**
The git fetch command fetches copies and downloads all branch files to your computer. Use it to bring the latest changes into your repository. It can fetch multiple branches at once.

**5. Fork**
A fork is a copy of a repository. Programmers often use forks to experiment with changes without affecting the main project.

**6. Head**
The commits at the top of a branch are called the head. It represents the latest commit of the repository you're currently working on.

**7. Index**
Whenever you add, delete, or change a file, it stays in the index until you're ready to commit the changes. It's like a staging area for Git. Use the git status command to see the content of your index."

**8. Master | Main**
Master is the main branch of all your repositories. It should contain the most recent changes and commits.
![image](https://github.com/dbs-toan/common-docs/assets/126640252/e13e3ab7-f7c1-4f9e-8328-96db6c904906)


**9. Merge**
The git merge command, combined with pull requests, is used to incorporate changes from one branch into another.

**10. Origin**
"Origin" is the default version of the repository. It also serves as a system alias for communicating with the main branch.
The command "git push origin master" is used to push local changes to the main branch.
![image](https://github.com/dbs-toan/common-docs/assets/126640252/78db1d90-2894-4dbb-ac2c-7e158e5a5e63)

**11. Pull**
Pull requests present proposed changes for the main branch. If you're working with a team, you can create pull requests to request that repository maintainers review and merge your changes.
The "git pull" command is used to incorporate changes into the main branch.

**12. Push**
The "git push" command is used to update remote branches with the latest changes you've committed.

**13. Rebase**
The "git rebase" command allows you to split, move, or escape commits. It can also be used to combine two different branches.

**14. Remote**
A remote repository is a copy of a branch. Remotes interact upstream with their root branch (origin branch) and other remotes in the repository.

**15. Repository**
A Git repository contains all project files, including branches, tags, and commits.

**16. Stash**
The "git stash" command removes changes from your index and saves them as stashes.
It's useful when you want to pause what you're doing and work on something else for a while. You can't stash more than one set of changes at a time.

**17. Tags**
Tags provide a way to track important commits. Lightweight tags simply act as pointers, while annotated tags are stored as full objects.

**18. Upstream**
In the context of Git, upstream refers to where you push your changes, usually the main branch (master branch).

**Docs**
- [Git Command Explorer](https://gitexplorer.com/)
- [GitSheet](https://gitsheet.wtf/)
- [Git Cheatsheet](http://ndpsoftware.com/git-cheatsheet.html#loc=index;)

# Commit message guidelines

**1. Commit message guidelines**

Each commit message consists of a header, a body, and a footer.
```
<type>(<scope>): <subject> <meta>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```
The header has a special format that includes a type, a scope, and a subject. The header is mandatory, and the scope of the header is optional.



**1.1 Allowed ```<type>```**

The <type> of a commit message should be a single word or abbreviation drawn from an ontology, according to the nature of the project. This document specifies a programming ontology, with the following elements:

- **feat**: a new feature
- **fix**: a bug fix
- **docs**: documentation only changes
- **style**: changes that do not affect the meaning of the - - - code (white-space, formatting, missing semi-colons, etc)
- **refactor**: a code change that neither fixes a bug nor adds a feature
- **perf**: a code change that improves performance
- **test**: adding missing tests
- **build**: changes to the build/compilation/packaging process or auxiliary tools such as documentation generation
- **ci**: changes in the continuous integration/delivery setup
- **revert**: If the commit reverts a previous commit, it should begin with revert: , followed by the header of the reverted commit. In the body it should say: This reverts commit <hash>., where the hash is the SHA of the commit being reverted.



**1.2 Allowed ```<scope>``` (optional)**
  
Usually, it is convenient to mention exactly which part of the code base changed.

**Example:**
```
feat(auth): introduce sign in via line
```

**1.3 Text**
The subject contains a succinct description of the change:

- use the imperative, present tense: **“change”** not **“changed”** nor **“changes”**
- don’t capitalize the first letter
- no dot **(.)** at the end
- it’s very useful to **reference the issue number** on the body of your commit message.
- limit the subject line to **72 characters**.
- each fix should be committed as a separate change.


**1.4 Message body**
Just as in the subject, use the imperative, present tense: “change” not “changed” nor “changes”. The body should include the motivation for the change and contrast this with previous behavior.

**1.5 Footer**
  
The footer should contain any information about **Breaking Changes** and is also the place to reference GitHub issues that this commit **Closes**.

**Breaking Changes** should start with the word BREAKING CHANGE: with space or two newlines. The rest of the commit message is then used for this.


**1.6 Examples**
  
```
feat(directive): add directives disabled/checked/multiple/readonly/selected

New directives for proper binding these attributes in older browsers (IE).
Added corresponding description, live examples and e2e tests.

Closes #351
```

```
docs(guide): update fixed docs from Google Docs

Couple of typos fixed:
- indentation
- batchLogstashLog -> batchLog
- start periodic checking
- missing brace
```

**2. Rules of Git commit message**

- Separate subject from body with a blank line
- Do not end the subject line with a period
- Do not capitalize the first letter of the subject line and each paragraph
- Use the imperative mood in the subject line
- Wrap lines at 72 characters
- Use the body to explain what and why you have done something. In most cases, you can leave out details about how a change has been made.


**3. Information in commit messages**
  
- Describe why a change is being made.
- How does it address the issue?
- What effects does the patch have?
- Do not assume the reviewer understands what the original problem was.
- Do not assume the code is self-evident/self-documenting.
- Read the commit message to see if it hints at improved code structure.
- The first commit line is the most important.
- Describe any limitations of the current code.
- Do not include patch set-specific comments.

# Create pull request

**1. Pull request rules**

To improve review process quality, there are pull request rules author must follow:

- **Name**: type of the task + task number in Backlog + task name. Sample: Feature/11-login-view
- **File change**: Should be about ~7 files (count only code changes). In case of a large PR that has many file changes, it should be split into smaller pull requests which are small enough to review but large enough to give you the context of the feature, bug fix, or update. Fewer file changes will greatly improve review process quality
- **Content**: pull request content needs to follow the defined template
- **Target branch**: defined by the project management
- **Reviewers**: need to be assigned and the number of reviewers should limit to **2 members**


**2. Pull request template**

```
## Document link:
<!--
A link to project document (Backlog or Trello...)
-->

## Pull request content:
<!--
What is the content of this pull request
-->

## Images or Videos:
<!--
Image or Video evidences which show PR content
```


# Sensitive Data Protection

**1. Git security guide and checklist**

**1.1. Sensitive Data**

<span style="background:#ffecb3">Never store credentials as code/config in Git repository:</span>.
- [ ] Add your file with sensitive data to .gitignore
- [ ] Block sensitive data being pushed to GitHub by git-secrets or its likes as a git pre-commit hook
- [ ] Use ENV variables for secrets in CI/CD and secret managers in production

**1.2. Remove Sensitive Data**

<span style="background:#ffecb3">If sensitive data made to a repo after all:</span>
- [ ] Invalidate tokens and passwords
- [ ] Remove the info and clear the GitHub history (force push rewrite history).
- [ ] Assess the impact of leaked private info

**1.3. Tightly Access Control**

<span style="background:#ffecb3">Create GitHub accounts by work email (@example.com) or use your personal account, but you must connect it to your work e-mail accounts</span>

- [ ] Require Two-factor authentication for all your GitHub accounts
- [ ] Never let users share GitHub accounts/passwords.
- [ ] Any laptops/devices with access to your source code must be properly secured
- [ ] Diligently revoke access from employees who are no longer working with example (for Leader)

**1.4. Rotate SSH keys and Personal Access Tokens**

<span style="background:#ffecb3">Be sure to refresh your keys and tokens periodically, mitigating any damage caused by keys that leaked out</span>

- [ ] Check the list of keys on your account at least monthly
- [ ] Revoke any not in regular use

**2. Personal security checklist**

A list of important security checks for GitHub individual. List items that are considered required are bolded.

**Set the primary email address to your work email @example.com** Personal settings → Emails

**Set a strong password**: Set a strong, random password generated by a password manager. Personal settings → Account → Change password

**Enable 2FA**: Turn on 2FA. The strongest form of 2FA is a hardware-based U2F security key. Personal settings → Security → Two-factor authentication

**Back up your 2FA Recovery codes**: You should put your recovery codes in a safe place or else you may get locked out of your GitHub account permanently. Personal settings → Security → Two-factor authentication

**Enable Vulnerability Alerts**: Personal settings → Notifications → Vulnerability alerts (check both “Email” and “Web”)

**Audit SSH keys regularly**: SSH keys are an alternative to username/password authentication to your GitHub account. An attacker with temporary access to your account could add an SSH key to your account as a backdoor. You should check the list of keys on your account at least monthly and review the last time they were used. Revoke any not in regular use. Personal settings → SSH and GPG keys

**Securely store your SSH keys**: You should only store your GitHub-related SSH keys on computers you consider reasonably secure. Avoid reusing SSH keys for both GitHub authentication and other purposes. Each SSH key should be secured with a strong password. You should regularly review the SSH keys listed on your account and revoke them if they are not in regular use. An attacker who compromises one of your listed SSH keys can access your GitHub account without further authentication secrets. Personal settings → SSH and GPG keys

**Add a dedicated GPG key for signing commits**: All users should have a GPG key to cryptographically sign commits. Keys should be stored securely. Personal settings → SSH and GPG keys

**Do not set a Fallback SMS number**: Most SMS providers are prone to number porting attacks. Personal settings → Security → Two-factor authentication

**Only install OAuth apps you trust**: Only install OAuth apps that you trust for the minimum amount of time you need them. Remove apps no longer in use. You should review their permissions to make sure they are appropriate; Personal settings → Applications → Authorized OAuth Apps

# Release branches (Semantic versioning)

For release branches, we will use the Semantic branching model for versioning the release of any application (Roberto Di Remigio & Radovan Bast)

![release](https://user-images.githubusercontent.com/31382948/234538695-76996a5f-1ac2-4d13-aa73-a3491acde258.png)

**1. Branch semantics rules**

- master collects changes towards the next major release.
- release/X.Y branches collect changes towards the next minor release.
- release/X.Y.Z branches collect changes towards the next patch release.
- New features are directed either towards master or towards release/X.Y branches.
- Patch release branches release/X.Y.Z never receive new features, they only receive bugfixes.

**2. Bugfixes**

- Bugfixes can be directed either towards release/X.Y.Z, or release/X.Y, or master, depending on the intent.
- Bugfixes directed towards release/X.Y.Z require to bump the patch number, signalled by creating a new tag.
- Important bugfixes in a given release/X.Y.Z can, if necessary, be ported to release/X.Y and further to master by merging.
- Important bugfixes in master can, if necessary, be ported to release/X.Y and release/X.Y.Z by cherry picking.
