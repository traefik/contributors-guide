# Issue Triage

## Scope

These guidelines serve as a primary document for triaging incoming issues from contributors to the Traefik project.
Projects are welcome to use this guidance as a starting point and customize to address specific triaging needs.

## What Is Triaging?

Issue triage is a process by which a project intakes and reviews new GitHub issues and requests, and organizes them to be actioned — usually by its own members.
Triaging involves categorizing issues and PRs based on factors such as priority/severity, ownership of the issue, and the issue kind (bug, feature, etc.)

- Each project is responsible for handling their own issues or pull requests

Triaging occurs in regularly scheduled meetings and may occur asynchronously depending on the severity of the issue or PR

## Why Is Triaging Beneficial?

OSS maintainers who triage regularly say it:

- speeds up issue management
- keeps contributors engaged by shortening response times
- prevents work from lingering endlessly
- replaces "special requests" and one-offs with a neutral process that acts like a boundary
- leads to greater transparency, interesting discussions, and more collaborative, informed decision-making
- it helps build prioritization, negotiation and decision-making skills, which are critical to most tech roles
- it reinforces community and culture

Triaging empowers projects to maintain a steady, continuous flow of work that is assessed and prioritized based on feedback and value.
The community benefits from this work by feeling their contributions and feedback is handled in a timely and professional manner.

## How to Triage: A Step-by-Step Flow

This aims to walk you through a standard triaging process, first covering tools and tips.

### Permissions and the Bot

Traefik utilizes many different automation tools to handle various tasks across our open source projects.
In almost all cases, these bots take action based on certain activities being performed on our repositories such as commits, labels being applied, issues, and PRs being opened, and closed.

- [Myrmica Aloba](https://github.com/containous/aloba) 🐜: Add labels and milestone on pull requests and issues.
- [Myrmica Lobicornis](https://github.com/containous/lobicornis) 🐜: Update and Merge Pull Request
- [Myrmica Bibikoffi](https://github.com/containous/bibikoffi) 🐜: Closes stale issues
- `Traefiker Bot` 🐜: Internal bot used to interact with Issues and PRs

## Review Newly Created Open Issues

Project issues and labels are listed for each project here:

- [Traefik issues](https://github.com/containous/traefik/issues)
- [Labels](https://github.com/containous/traefik/labels) and their [description](./labels.md)

New, untriaged issues are assigned the label `status/0-needs-triage` automatically.
During the issue triage meeting, project leads could identify at least one team member to serve as the individual responsible for applying labels and assigning ownership for incoming issues that require any action.

Labels are the primary tools for triaging.

Depending on your permissions, either close or comment on any issues that are identified as support requests, duplicates, or not-reproducible bugs or that lack enough information from the reporter.

### Support Requests

Some people mistakenly use GitHub issues to file support requests.
Usually, they're asking for help in troubleshooting their configuration.
In most cases, our bot will automatically respond to these issues, but not always.
It is important we validate instances where the bot steps in and confirm the author is in fact asking a question.

In cases where it's been confirmed the author is asking a question and the bot did not intercede, direct the author to use our [community forums](https://community.containo.us), our documentation, or provide an answer directly.
Then apply the `kind/question` label and close the issue.

### Wrongly Placed Issues

In some instances, issues that belong in another project are incorrectly opened by a reporter.
These issues should either be closed or moved to the appropriate project.

### Needs More Information

The `contributor/waiting-for-feedback` label indicates an issue that needs more information in order to work on it; comment on or close it.

### Bugs

Do a quick duplicate search to see if the issue has been reported already.
If a duplicate is found, let the issue reporter know, reference the original issue, set the label `resolution/duplicate`, and close the duplicate.

If a reported issue is potentially a bug it should be labeled `kind/bug/possible` and depending on the potential severity of the issue assigned to a maintainer for investigation.
Maintainers will validate if the problem is a bug by trying to reproduce it.

If the bug can be reproduced:

- Change the label to `kind/bug/confirmed`
- Define its priority

If you can't reproduce it:

- Contact the issue reporter with your findings
- Close the issue if both the parties agree that it could not be reproduced

If you need additional information to continue working on the issue:

- Let the reporter know it by adding an issue comment followed by the label `contributor/waiting-for-feedback`
- Issues are automatically closed after 60 days if they receive no feedback from the contributor

### Kind Labels

Once triaged, issues should be assigned one of the following `kind` labels:

- `kind/bug/possible` or `kind/bug/confirmed`
- `kind/enhancement`
- `kind/proposal` see [Proposals](./proposals.md)
- `kind/question`

## Define Priority

We use GitHub labels for prioritization.

We aim for consistency across the entire project.
However, if you notice an issue that you believe to be incorrectly prioritized, please leave a comment offering your counter-proposal and we will evaluate it.

| Priority label | What it means                                                                                                                                                                                                                                                                                                             | What that might include                                                                 |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------|
| `priority/P0`  | Team leaders are responsible for making sure that these issues (in their area) are being actively worked on—i.e., drop what you're doing. Stuff is burning. These should be fixed before the next release.                                                                                                                | user-visible bugs in core features, broken builds / tests, and critical security issues |
| `priority/P1`  | Must be staffed and worked on either currently or very soon—ideally in time for the next release. Important, but wouldn't block a release.                                                                                                                                                                                | third-party systems and dependencies, bumping ...                                       |
| `priority/P2`  | Important over the long term, but may not be currently staffed and/or may require multiple releases to complete. Wouldn't block a release.                                                                                                                                                                                | new providers, components, and enhancements to existing systems                         |
| `priority/P3`  | General agreement that this is can be a nice-to-have. Community contributions would be most welcome in the meantime, though it might take a while to get them reviewed if reviewers are fully occupied with higher-priority issue.                                                                                        | less requested features                                                                 |

## Find and Set the Right Owner

Issues that are prioritized at `P1` or above should be assigned an owner who is responsible for completing the task and closing the issue.

### Self-Assigning

If you think you can fix the issue, discuss the issue with the team, and only assign it to yourself after discussion.
If you cannot self-assign for permissions-related reasons, ask a maintainer who has permissions for assignment and then work on creating a PR.

## Follow Up

Any issue which is assigned an owner should be followed up on in a timely manner.
If the issue requires action by another maintainer or requires feedback from another contributor ping them in the issue with a `@mention`.

### If an Issue has no activity

Based on the labels applied to the issue, it may be closed for the following reasons:

- `contributor/waiting-for-feedback` or `contributor/need-more-information` are automatically closed after 60 days of no activity
- `kind/question` are automatically closed after 8 days with no activity
- closed issues have `status/5-frozen-due-to-age` applied automatically after 30 days of no activity

## Abuse reports

According to our [Code of Conduct](https://github.com/traefik/traefik/blob/master/CODE_OF_CONDUCT.md), [abuse reports](https://github.com/traefik/traefik/reported_content) should be handled during the triage process as well.

## Footnotes

### Support Requests: Channels

These should be directed to the following:

- [User documentation](https://doc.traefik.io/)
- [Discussion Forums](https://community.containo.us)
