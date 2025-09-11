# GitHub Check for Tanzania Workshop 2025

In this brief tutorial, we will walk through how to set up git and GitHub, then check it works by pushing a change to this very repository.

For a detailed and helpful guide to using R and git, visit <https://happygitwithr.com/>. (This tutorial is adapted from that source.)

## Pre-requisites

-   If you've not yet, download R (<https://cloud.r-project.org/>) and RStudio (<https://posit.co/download/rstudio-desktop/>).

-   Register a GitHub account: <https://github.com/>.

-   Download and install git: <https://git-scm.com/downloads>.

## Introduce yourself to git

In R, run the following:

``` r
install.packages("usethis") ## only need to do this once

library(usethis)

use_git_config(user.name = "Jane Doe", user.email = "jane@example.org")
```

Replace the `user.name` and `user.email` in quotes with the username and email associated with your GitHub account.

## Personal access token (PAT)

Go to <https://github.com/settings/tokens> and click “Generate token”.

Copy the generated PAT to your clipboard.

In R, run:

``` r
gitcreds::gitcreds_set()
```

Paste the PAT in response to the dialogue in the console.

```         
? Enter password or token: ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
-> Adding new credentials...
-> Removing credentials from cache...
-> Done.
```

## Fork, clone, edit, commit and push

Go to: <https://github.com/jt-hicks/github_check_tz_2025>

Click the big green button that says “\<\> Code”.

Copy the displayed HTTPS URL.

In your RStudio console, change the following code and run it:

``` R
usethis::create_from_github(
  "<Paste the HTTPS URL here>",
  destdir = "<Type the path to the folder where you want to save this repo here>",
  fork = TRUE
)
```

The path (`destdir` argument above) is the location on your computer where you want the repository to be saved.

The above code will 'fork' the repo, clone it to your local computer, and opens a new RStudio instance and project.

Best practice is to modify your own branch of the repo, rather than editing the 'main' branch directly. (We'll talk about all this in the workshop so don't worry if you are confused at this point.) To make a new branch called 'myname,' run this in your R console:

``` R
usethis::pr_init(branch = 'myname')
```

This creates the new branch and switches to is (or 'checks it out') in RStudio.

Now, in RStudio, modify the '`participants.R`' file by adding your name.

Save your changes.

Commit your changes:

-   Click the "Git" tab in the upper right pane.

-   Check the "Staged" box for `participants.R`.

-   If you’re not already in the Git pop-up, click “Commit”.

-   Type a message in “Commit message”, such as “Added my name”.

-   Click “Commit”.

Back in your R console, run:

``` R
usethis::pr_init(branch = 'myname')
```

This pushes your committed changes to GitHub and tries to make a new Pull Request (that is, a suggested change). A new browser window will open to a GitHub page. Click the green "Create pull request" button. Type a message in the "Add a description" field, such as your name. Then push the green "Create pull request" button.

I will get a notification that you've suggested a change.

## Check your work.

In a couple days (after I've had time to review and accept your request), go back to your browser and to <https://github.com/jt-hicks/github_check_tz_2025>.

Open participants.R. Do you see your name?

If so, congratulations! See you in Arusha!

If not, post an issue on the Issues tab of <https://github.com/jt-hicks/github_check_tz_2025>. To do this:

-   Go to the 'Issues' tab at the top of the github page (between Code and Pull Requests).

-   Click the green 'New Issue' button.

-   In the title, add your name.

-   In 'Add a description', describe what happened when you tried to do the tutorial. Add any error or warning messages you received.

-   When you are done, click the green 'Create' button. (We'll still see you in Arusha!)
