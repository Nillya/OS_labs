# Практичне завдання “Work-case 1”

## Виконав студент групи РПЗ-23Б

- **Нагорний I.М.**

## What is git used for, what are the main actions and commands performed in it

git - is a version control system used by both large companies and individual software developers. git allows you to conveniently save intermediate work results, for quick return to any of the stages of development, or division of labor between different specialists.

### Basic commands git:
  - `git init` - initializes the repository in the selected folder
  - `git add <file>` - adds the file to the repository
  - `git commit -m "<commit name>"` - creates a new commit
  - `git branch <name>` - creates a new branch
  - `git checkout <branch name>` - sets the HEAD pointer to the specified branch
  - `git checkout <commit id>` - sets the HEAD pointer to the specified commit
  - `git push <remote repository>` - pushes the current branch to the specified branch in the remote repository
  - `git merge <branch name>` - "glues" the current branch with the one specified in the command, and creates a new commit belonging to the specified branch
  - `git remote add <link>` - tells the current repository the link under which the remote repository is stored
  - `git pull` - a quick command that replaces the alternate execution of the next two commands:
    - `git fetch <remote branch>` - retrieves the state of the specified remote branch
    - `git merge` - updates the local branch to the pulled state of the remote branch

## What is a "commit" and how does it allow you to track changes to files?

Commit may be a preview of the state of the working tree at a certain point in time. The commit pointed to by HEAD gets to be its parent when a modern commit is made. This implies that git within the commit spares the changes made on the past commit (parent).

Working tree is any registry on your record framework that includes a store related with it. Incorporates all records and subdirectories of that registry.

A store may be a collection of commits, each of which is an file of what the project's working tree looked like at a few point within the past. It too indicates the head (HEAD), which recognizes the department or commit from which the current working tree branches. 
