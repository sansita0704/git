# Version Control System (VCS)

-   It records the changes made to our project over time in a special database called **repository**.
-   We can look at our project history and see who has made what changes when and why.
-   If we made some mistake, we can easily revert back to an earlier state.

-   Without VCS, we have to maintain separate folders of diff versions of our project.
-   It will be more difficult to manage if more than one person is doing a project.
-   Then, we have to merge the changes manually.

## In a nutshell:

-   Using VCS, we can:

1. Track our project history.
2. Work together.

# Types of VCS

1. Centralized (CVCS)
2. Distributed (DVCS)

## 1. Centralized

-   All team members connect to a central server to get the latest copy of the code and to share their changes with others.
-   i.e. there is a single repo where all versions of the project are stored.
-   Developer pull the latest version of the repo from repo and then make changes on it.
-   Then, push it to same repo.
-   So, the clone of repo does not exists in their local comp.
-   **e.g.** - Subversion, Microsoft Team Foundation Server.

![Centralized VCS](Screenshots/1.%20CVCS.png)

-   **Problem:** If this central server goes offline, we cannot collaborate or save snapshots of our project.
-   So, we have to wait until the server comes online.

## 2. Distributed

-   Every member has a copy (clone) of their project and its history on their machine.
-   So, we can save snapshots of our project locally on our machine.
-   Then, we push the changes to remote repo.
-   Here, there is no problem of central server getting offline.
-   If it does go offline, we can synchronize our work directly with others.
-   **e.g.** - Git, Mercury

![Distributed VCS](Screenshots/2.%20DVCS.png)

# Git

Out of all VCS, git is the most popular VCS b/z it is:

-   Free
-   Scalable
-   Super Fast
-   Scalable
-   Operations like branching and merging are superfast in git.

## Various ways to use Git

### 1. The command line:

-   It is the fastest and the easiest way.
-   We can open a terminal or cmd prompt window to execute git commands.
-   **Note:** Use below software to have a colorful terminal window like that of mosh:

![Colorful Terminal Window](Screenshots/For%20colorful%20terminal.png)

**It's Importance:**

-   GUI tools have limitations.
-   GUI tools are not always available.

### 2. Code editors and IDEs

-   Most of the modern code editors have built-in support for basic git features.

### 3. Graphical User Interfaces

-   Go to https://git-scm.com/downloads/guis to see list of GUI.
-   2 most popular GUI are:

1. GitKraken
2. SourceTree

Go to https://git-scm.com/ to install latest version of git.

# Configuring Git

-   When we use git for the first time, we have to configure some settings:

1. Name
2. Email
3. Default Editor
4. Line Ending

<br>

-   We can have these settings on 3 diff levels:

1. **System Level:** Settings apply to all the users of current comp.

2. **Global Level:** Settings apply to all the repo of current user.

3. **Local Level:** Settings apply to the current repo.

<br>

```
git config --global user.name "Sansita Jain"
git config --global user.email sansita7406@gmail.com
git config --global core.editor "code --wait"
```

-   Here, we add double quotes when we have a space in the value.
-   Using wait flag (--wait), we tell the terminal window to wait until we close the new VS code window.

<br>

-   All these configuration setting are stored in a text file.
-   We can edit that file using our default editor (i.e. VS Code).

```
git config --global -e
```

<br>

-   **Carriage Return** (CR): \r
-   **Line Feed** (LF): \n

![Line ending](Screenshots/3.%20CRLF.png)

-   On Windows, end of line is marked with 2 special characters "\r\n" CRLF.
-   On macOS and linux, end of line is marked with LF.
-   If we do not handle end of lines properly, we can have some major issues.
-   To configure it, we use a property called **core.autocrlf** (auto carriage return line feed).

<br>

-   For windows user, it should be set to true.
-   For mac user, it should be set to input.
-   So, the code stored in remote repo has LF for line ending no matter which user pulls or pushes the code.

![Use of core.autocrlf property](Screenshots/4.%20core.autocrlf.png)

| Setting | When Committing (Pushing) | When Checking Out (Pulling)        |
| ------- | ------------------------- | ---------------------------------- |
| `true`  | Converts `CRLF → LF`      | Converts `LF → CRLF`               |
| `input` | Converts `CRLF → LF`      | Leaves files as-is (no conversion) |
| `false` | No conversion             | No conversion                      |

<br>

```
git config --global core.autocrlf input
```

# Getting Help

```
git config --help
git config -h
```

1. **--help:**

-   Tells about the command in detail.
-   Use space key to move to next page and 'q' to exit.

2. **-h**

-   Tells about the command in concise manner.
