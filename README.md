# Day 1

### Git best Practices

- Make clean, single-purpose commits
- It is better to keep commits as small and focused as possible for many reasons.
- If the commit has to be rolled back completely, it's far easier to do so.
  `git log`
- Git works best, and works in your favor, when you commit your work often.
- Don't alter published history
- Don't commit generated files. It is useful to add a `.gitignore` to a repositories root.

### Daily Challenge

- Create a new repository named `mobile-friendly-practice`
- Clone the repository

```bash
  git clone https://github.com/your-repo-here
```

- add an `index.html` file
- add a css folder and inside that folder create a `style.css` file
- push your changes to your `main` branch

  ```bash
  git add .
  ```

  - Using a `.` says that you want to add all files in your directory.
  - Verify your files are added with `git status`
  - Commit your changes and add a message, best message summary practices: Short and concise.
    - `Fix X to allow Y to use Z`
    - `feat: Add File X, fix: Fix Bug Y`

  ```bash
  git commit -m 'summary here'
  ```

  - If you need to add additional details you can add a description by adding a second `-m` after the summary

  ```bash
  git commit -m "Summary" -m "Description..."
  ```

  - Finally we push the changes to the desired branch, check branch bottom left of VS code.

  ```bash
  git push
  ```

### Github Flow

Creating and merging branches is critical to keeping large projects organized especially if their are multiple developers working on the same project or if the project is live. Branches are a means of making a silo where you can write potentially experimental code and change as much code as you want without effecting the original.

- Check which branch you are in
  `git branch`
- Create a new branch

```bash
git checkout -b your-branch-name-here
```

- Switch back and forth between branches with
  `git checkout branch-name`
- After you have made the desired changes in your new branch and everything is working the way you want it to the last step is to merge your new branch with your main/master branch.
  - Check which branch you are in with `git branch` switch to your main branch with `git checkout main` if needed.
  - Merge the branch you want

```bash
git merge branch-name
```

VS code tricks - don't forget to use tab

- `!`
- `lorem300`the number after lorem will generate that many words
- ctrl/cmd + alt + ↓ will allow you to edit multiple lines at the same time
- shift + alt + ↓ will copy the line you are on bellow.
- ctrl + d while highlighting a word will select the next word in the document that matches so you can edit both doing this multiple times will select multiple instances of that word
