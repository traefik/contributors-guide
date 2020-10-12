# Pull Request Guidelines

## Before You Submit a Pull Request

This guide is for contributors who already have a pull request to submit.
If you're looking for information on setting up your developer environment and creating code to contribute to Traefik or related projects,
see the [development guide](https://docs.traefik.io/contributing/building-testing/).

First-time contributors should head to the Contributor Guide to get started.

Make sure your pull request adheres to our best practices.
These include following project conventions, making small pull requests, and commenting thoroughly.
Please read the more detailed section on Best Practices for Faster Reviews at the end of this doc.

## Run Local Verifications

You can run these local verifications before you submit your pull request to predict the pass or fail of continuous integration

- `make pull-images`
- `make validate`
- `make test`

## The Pull Request Submit Process

Merging a pull request requires the following steps to be completed before the pull request will be merged automatically.

- [Open a pull request](https://help.github.com/articles/about-pull-requests/)
- Pass the linter
- Pass all tests
- Get all necessary approvals from reviewers and code owners

## Pull Requests and the Release Cycle

Occasionally, a project may freeze their own code base when working towards a specific feature or goal that could impact other development.
During this time, your pull request could remain unmerged while their release work is completed.

## The Testing and Merge Workflow

Pull Requests are managed by the bot [Myrmica Lobicornis](https://github.com/traefik/lobicornis).
It is responsible for verifying Github Checks (CI, Tests, etc), mergability, and minimum reviews.
In addition, it will rebase or merge with the base PR branch if needed.
It performs several other housekeeping items and you can read more about those on the [README](https://github.com/traefik/lobicornis/blob/master/readme.md) for Lobicornis.

The maintainer giving the final LGTM must add the `status/3-needs-merge` label to trigger the merge bot.

By default, a squash-rebase merge will be carried out.

The status `status/4-merge-in-progress` is only used by the bot.

If the bot is not able to perform the merge, the label `bot/need-human-merge` is added.
In such a situation, solve the conflicts/CI/... and then remove the label `bot/need-human-merge`.

To prevent the bot from automatically merging a PR, add the label `bot/no-merge`.

The label `bot/light-review` decreases the number of required LGTM from 3 to 1.

This label can be used when:

- Updating a dependency
- Merging branches back into master
- For minor documentation changes
- Changelog PRs

## Why was my pull request closed?

Pull requests older than 90 days may be closed.
Exceptions can be made for pull requests that have active review comments, or that are awaiting other dependent pull requests.
Closed pull requests are easy to recreate, and little work is lost by closing a pull request that subsequently needs to be reopened.

We want to limit the total number of pull requests in flight to:

- Maintain a clean project
- Remove old pull requests that would be difficult to rebase as the underlying code has changed over time
- Encourage code velocity

## Why is my pull request not getting reviewed?

A few factors affect how long your pull request might wait for review.

If it's the last few weeks of a milestone, we need to reduce churn and stabilize.

Or, it could be related to best practices.
One common issue is that the pull request is too big to review.
Let's say you've touched 39 files and have 8657 insertions.
When your would-be reviewers pull up the diffs, they run away - this pull request is going to take 4 hours to read and they don't have 4 hours right now.
They'll get to it later, just as soon as they have more free time (ha!).

There is a detailed rundown of best practices, including how to avoid too-lengthy pull requests, in the next section.

But, if you've already followed the best practices and you still aren't getting any pull request love, here are some things you can do to move the process along:

- Ping the assignee (`@username`) on the pull request comment stream.
- If you have fixed all the issues from a review, and you haven't heard back, you could ping the assignee on the comment stream with a "please take another look" (`PTAL`) or similar comment indicating that you are ready for another review.

Read on to learn more about how to get faster reviews by following best practices.

## Best Practices for Faster Reviews

Most of this section is not specific to Traefik, but it's good to keep these best practices in mind when you're making a pull request.

You've just had a brilliant idea on how to make Traefik better.
Let's call that idea Feature-X.
Feature-X is not even that complicated.
You have a pretty good idea of how to implement it.
You jump in and implement it, fixing a bunch of stuff along the way.
You send your pull request - this is awesome! And it sits. And sits.
A week goes by and nobody reviews it.
Finally, someone offers a few comments, which you fix up and wait for more review.
And you wait. Another week or two go by. This is horrible.

Let's talk about best practices so your pull request gets reviewed quickly.

### Is the feature wanted? File a Traefik Feature Request

Are you sure Feature-X is something the Traefik team wants or will accept?
Is it implemented to fit with other changes in flight? Are you willing to bet a few days or weeks of work on it?

It's better to get confirmation beforehand.

When you want to make a significant change, you should open an Issue and file a feature request.

Even for small changes, it is often a good idea to gather feedback on an issue you filed.

### KISS, YAGNI, MVP, etc.

Sometimes we need to remind each other of core tenets of software design - Keep It Simple, You Aren't Gonna Need It, Minimum Viable Product, and so on.
Adding a feature "because we might need it later" is antithetical to software that ships.
Add the things you need NOW and (ideally) leave room for things you might need later - but don't implement them now.

### Smaller Is Better: Small Commits, Small Pull Requests

Small commits and small pull requests get reviewed faster and are more likely to be correct than big ones.

Attention is a scarce resource.
If your pull request takes 60 minutes to review, the reviewer's eye for detail is not as keen in the last 30 minutes as it was in the first.
It might not get reviewed at all if it requires a large continuous block of time from the reviewer.

#### Breaking up commits

Break up your pull request into multiple commits, at logical break points.

Making a series of discrete commits is a powerful way to express the evolution of an idea or the different ideas that make up a single feature.
Strive to group logically distinct ideas into separate commits.

For example, if you found that Feature-X needed some prefactoring to fit in, make a commit that JUST does that prefactoring.
Then make a new commit for Feature-X.

Strike a balance with the number of commits.
A pull request with 25 commits is still very cumbersome to review, so use your best judgment.

#### Breaking up Pull Requests

Or, going back to our prefactoring example, you could also fork a new branch, do the prefactoring there and send a pull request for that.
If you can extract whole ideas from your pull request and send those as pull requests of their own, you can avoid the painful problem of continually rebasing.

Traefik is a fast-moving codebase - lock in your changes ASAP with your small pull request, and make merges be someone else's problem.
We want every pull request to be useful on its own, so use your best judgment on what should be a pull request vs. a commit.

As a rule of thumb, if your pull request is directly related to Feature-X and nothing else, it should probably be part of the Feature-X pull request.
If you can explain why you are doing seemingly no-op work ("it makes the Feature-X change easier, I promise") we'll probably be OK with it.
If you can imagine someone finding value independently of Feature-X, try it as a pull request.
(Do not link pull requests by `#` in a commit description, because GitHub creates lots of spam.
Instead, reference other pull requests via the pull request your commit is in.)

### Put changes that are unrelated to your feature into a different pull request

Often, as you are implementing Feature-X, you will find bad comments, poorly named functions, bad structure, weak type-safety, etc.

You could fix those things (or at least file issues, please) - but not in the same pull request as your feature.
Otherwise, your diff will have way too many changes, and your reviewer won't see the forest for the trees.

### Comments Matter

In your code, if someone might not understand why you did something (or you won't remember why later), comment it.
Many code-review comments are about this exact issue.

If you think there's something pretty obvious that we could follow up on, add a `TODO`.

Read up on [GoDoc](https://blog.golang.org/godoc-documenting-go-code) - follow those general rules for comments.

### Tests Matter

Nothing is more frustrating than starting a review, only to find that the tests are inadequate or absent.
Very few pull requests can touch the code and NOT touch tests.

If you don't know how to test Feature-X, please ask!
We'll be happy to help you or to suggest appropriate test cases.

### Commit Message Guidelines

Commits and their commit messages are the *"permanent record"* of the changes being done in your PR and their commit messages should accurately describe both *what* and *why* it is being done.

Commit messages are comprised of two parts; the subject and the body.

The subject is the first line of the commit message and is often the only part that is needed for small or trivial changes.
Those may be done as "one liners" with the `git commit -m` command, but only if the what and especially why can be fully described in that few words.

The commit message body is the portion of text below the subject when you run `git commit` without the `m` flag which will open the commit message for editing in your [preferred editor](https://help.github.com/en/github/using-git/associating-text-editors-with-git).
Typing a few further sentences of clarification is a useful investment in time both for your reviews and overall later project maintenance.

```bash
This is the commit message subject

Any text here is the commit message body
Some text
Some more text
...

# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
# On branch example
# Changes to be committed:
#   ...
#

```

Use these guidelines below to help craft a well formatted commit message.

### Commit Message Subject Line Guidelines

#### Try to keep the subject line to 50 characters or less; do not exceed 72 characters

The 50 character limit for the commit message subject line acts as a focus to keep the message summary as concise as possible.
It should be just enough to describe what is being done.

The hard limit of 72 characters is to align with the max body size.
When viewing the history of a repository with `git log`, git will pad the body text with additional blank spaces.
Wrapping the width at 72 characters ensures the body text will be centered and easily viewable on an 80-column terminal.

#### Use imperative mood in your commit message subject

Imperative mood can be be thought of as a *"giving a command"*; it is a **present-tense** statement that explicitly describes what is being done.

Good Examples:

- Fix x error in y
- Add foo to bar
- Revert commit "baz"
- Update pull request guidelines

Bad Examples:

- Fixed x error in y
- Added foo to bar
- Reverting bad commit "baz"
- Updating the pull request guidelines
- Fixing more things

A general guideline from [Chris Beams](https://chris.beams.io/) on forming an imperative commit subject is it should complete this sentence:

```
If applied, this commit will <your subject line here>

```

Examples:

- *If applied, this commit will* **Fix x error in y**
- *If applied, this commit will* **Add foo to bar**
- *If applied, this commit will* **Revert commit "baz"**
- *If applied, this commit will* **Update the pull request guidelines**

### Commit Message Body Guidelines

#### Use the commit message body to explain the *what* and *why* of the commit

Commits and their commit messages are the *"permanent record"* of the changes being done in your PR.
Describing why something has changed and what effects it may have.
You are providing context to both your reviewer and the next person that has to touch your code.

If something is resolving a bug, or is in response to a specific issue, you can link to it as a reference with the message body itself.
These sorts of breadcrumbs become essential when tracking down future bugs or regressions and further help explain the *"why"* the commit was made.

#### Add a single blank line before the commit message body

Git uses the blank line to determine which portion of the commit message is the subject and body. Text preceding the blank line is the subject, and text following is considered the body.

#### Wrap the commit message body at 72 characters

The default column width for git is 80 characters. Git will pad the text of the message body with an additional 4 spaces when viewing the git log.
This would leave you with 76 available spaces for text, however, the text would be "lop-sided".
To center the text for better viewing, the other side is artificially padded with the same amount of spaces, resulting in 72 usable characters per line.
Think of them as the margins in a word doc.

#### Avoid using GitHub Keywords and Mentions in your commit message

[GitHub keywords](https://help.github.com/articles/closing-issues-using-keywords) in a PR to close issues is considered a convenience item, but can have unexpected side-effects; often closing something they shouldn't.

- Avoid using (`@`)Mentions in your commit message:
  - (`@`)mentions within the commit message will send a notification to that user, and will continually do so each time the PR is updated.
- Avoid using these keywords in your commit message:
  - close, closes, closed, fix, fixes, fixed, resolve, resolves, resolved

### **Additional Resources**

- [How to Write a Git Commit Message - Chris Beams](https://chris.beams.io/posts/git-commit/)
- [Distributed Git - Contributing to a Project (Commit Guidelines)](https://git-scm.com/book/en/v2/Distributed-Git-Contributing-to-a-Project)
- [What’s with the 50/72 rule? - Preslav Rachev](https://preslav.me/2015/02/21/what-s-with-the-50-72-rule/)
- [A Note About Git Commit Messages - Tim Pope](https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html)

## It's OK to Push Back

Sometimes reviewers make mistakes.
It's OK to push back on changes your reviewer requested.
If you have a good reason for doing something a certain way, you are absolutely allowed to debate the merits of a requested change.
Both the reviewer and reviewee should strive to discuss these issues in a polite and respectful manner.

You might be overruled, but you might also prevail.
We're pretty reasonable people.

Another phenomenon of open-source projects (where anyone can comment on any issue) is the dog-pile - your pull request gets so many comments from so many people it becomes hard to follow.
In this situation, you can ask the primary reviewer (assignee) whether they want you to fork a new pull request to clear out all the comments.
You don't HAVE to fix every issue raised by every person who feels like commenting, but you should answer reasonable comments with anexplanation.

### Common Sense and Courtesy

No document can take the place of common sense and good taste.
Use your best judgment, while you put a bit of thought into how your work can be made easier to review.
If you do these things your pull requests will get merged with less friction.

### Trivial Edits

Each incoming Pull Request needs to be reviewed, checked, and then merged.

While automation helps with this, each contribution also has an engineering cost.
Therefore it is appreciated if you do NOT make trivial edits and fixes, but instead focus on giving the entire file a review.

If you find one grammatical or spelling error, it is likely there are more in that file, you can really make your Pull Request count by checking the formatting, checking for broken links, and fixing errors and then submitting all the fixes at once to that file.
