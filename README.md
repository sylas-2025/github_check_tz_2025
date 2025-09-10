---
editor_options: 
  markdown: 
    wrap: 72
---

# GitHub Check for Tanzania Workshop 2025

In this brief tutorial, we will walk through how to set up git and
GitHub, then check it works by pushing a change to this very repository.

For a detailed and helpful guide to using R and git, visit
<https://happygitwithr.com/>. (This tutorial is adapted from that
source.)

## Pre-requisites

-   If you've not yet, download R (<https://cloud.r-project.org/>) and
    RStudio (<https://posit.co/download/rstudio-desktop/>).

-   Register a GitHub account: <https://github.com/>.

-   Install and set up git Download and install git:
    <https://git-scm.com/downloads>.

## Introduce yourself to git

In R:

``` R
## install if needed (do this exactly once):
install.packages("usethis")

library(usethis)

use_git_config(user.name = "Jane Doe", user.email = "jane@example.org")
```

where `user.name` and `user.email` are the username and email associated
with your GitHub account.

## Personal access token (PAT)

Go to <https://github.com/settings/tokens> and click “Generate token”.
Copy the generated PAT to your clipboard.

In R:

``` R
gitcreds::gitcreds_set()
```

Paste the PAT in response to the dialogue in the console.

```         
? Enter password or token: ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
-> Adding new credentials...
-> Removing credentials from cache...
-> Done.
```

## Clone, edit, commit and push

Go to: <https://github.com/jt-hicks/github_check_tz_2025>

Click the big green button that says “\<\> Code”.

Copy the displayed HTTPS URL.

In RStudio, start a new Project:

-   File \> New Project \> Version Control \> Git.

-   In “Repository URL”, paste the URL of your new GitHub repository. It
    will be something like this
    <https://github.com/jt-hicks/github_check_tz_2025.git>.

    -   Do you NOT see an option to get the Project from Version
        Control? Restart RStudio and try again. Still no luck? Go to
        here (<https://happygitwithr.com/rstudio-see-git>) for tips on
        how to help RStudio find Git.

-   Accept the default project directory name, e.g. myrepo, which
    coincides with the GitHub repo name.

-   Take note (or change) where the Project will be saved locally.

-   Check “Open in new session”.

-   Click “Create Project”.

From Rstudio, modify the '`participants.R`' file by adding your name.

Save your changes.

Commit your changes:

-   Click the "Git" tab in the upper right pane.

-   Check the "Staged" box for `participants.R`.

-   If you’re not already in the Git pop-up, click “Commit”.

-   Type a message in “Commit message”, such as “Commit from RStudio”.

-   Click “Commit”.
