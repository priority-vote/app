# Project Workflow

Tickets are listed in priority from top to bottom (descending) on our [project board](https://github.com/priority-vote/app/projects/1)

Take off the top ticket in the Backlog column and assign yourself to the issue under the `Assignees` tab in the issue

Open a branch off of `master` using the following name scheme:
  - Prefix branch name with the number of the issue/ticket followed by a `/`
  - Give some sort of detail to the name, separating the name by underscores

An example branch name would be `3/add_environments`

An example workflow would be as follows:
  1. Switch to master `git checkout master`
  2. Make sure it is up to date `git pull`
  3. Branch off of master to create your new branch `git checkout -b 3/add_environments`
  4. Make changes to the branch as described in the ticket w/o giving into too much scope creep
  5. Stage and commit the changes to your branch
  6. Push the changes to your new branch and open up a PR. *Make sure the PR name is also prefixed by the issue number*

*At this point your issue should have the* `needs-code-review` label assigned to it*

PRs require one review before they are merged into `dev`

*At this point the person who merged the issue should have assigned the* `qa-needed` *label to your issue*

Once in `dev` they will be QA`d.

QA will either assign the `qa-passed` or `qa-failed` label assigned to your issue.

If your issue receives a `qa-failed` label, then you will need to repeat steps 4-6 described above, make changes via feedback from qa, commit and push those changes, and then open a PR for it to be reviewed again.

If `qa-passed` is assigned to your issue, then it will merged into master and pushed to production. 

# Ticket organization

Tickets are specific stories that are part of an overarching milestone (or epic). 

Milestones are large goals of the application, and stories or issues are small tasks that when each is completed the milestone should be accomplished.

For instance a milestone may be  "We want users"

Which could include multiple stories/issues like adding authentication, user dashboards, ability to see other users, ability to login, etc.

Labels on issues are as follows
  - feature: An addition to the project
  - bug: A fix
  - needs-code-review: The issue is in PR and needs to be reviewed
  - qa-needed: The issue has been merged to dev and needs the be QA'd
  - qa-passed: The issue has been confirmed to work from QA and is ready to go into master
  - qa-failed: The issue was denied by QA and needs further work before being accepted into master

# Project organization

The backlog columns contains issues in order of priority

Icebox contains issues that are unprioritized, but may eventually need to be done. If you come across a bug make sure to create an issue with the `bug` label and add it to the Icebox column in the project. 