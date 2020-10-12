# Review Guidelines

## Tips for code reviewers

If you're looking for tips for preparing your PR for review check out the Pull Requests page, this page is for reviewers.

## PR Review Workflow

Pull Requests are checked under the following conditions during the daily triage meeting:

- If the PR has been created since the last triage meeting
- If the PR has had activity (commits, comments, discussion) since the last triage meeting

### PR Review Process

All PRs should be labeled to help maintainers and contributors understand what actions are required to progress the PR to a resolved state.
All `status` labels indicate actions are required from the maintainer who is assigned to the PR.

- The `status/1-needs-design-review` should be assigned an owner for PRs whose scope of impact is considered significant, this is done to ensure the proposal meets the standards for quality and goals within each project.
  A senior maintainer should comment on the issue when it's ready for `2-needs-review` and relabel the issue accordingly.
- The `status/2-needs-review` indicates that a PR is awaiting code and documentation review.
  The PR must have 3 approvals by maintainers in order for the status to be changed to `3-needs-merge`.
- The `status/3-needs-merge` indicates to the merge bot that a PR is ready to be merged. This label is set by the latest maintainer that approve the PR.

## Managing time

### Block time off to review

Often it can be hard to find dedicated, uninterrupted time to review PRs.
If you can, allocate some time and block it off on your calendar to help stay on top of the incoming queue.

## Resolving the PR

### Loop in others when domain specific knowledge is needed

Traefik has sections that may require domain-specific knowledge.
If you are unsure or uncomfortable reviewing a portion of a PR, it is better to decline a review and reassign to an someone with more expertise in that area.

If you are brought in for your knowledge in a specific area, try and provide meaningful comments to serve as breadcrumbs in the future to help others gain a better understanding of that area.

### Asking questions

You are encouraged to ask questions and seek an understanding of what the PR is doing; however, your question might be answered further into the review.
You can stage your questions, and before you submit your review, revisit your own comments to see if they're still relevant or update them after gaining further context.

Often a question may turn into a request for further comments or changes to explain what is happening at that specific point.

In your questions, try to be empathetic when phrasing. Instead of:

*"Why did you do this?"*

try

*"Am I understanding this correctly? Can you explain why...?"*

Remember a review is a discussion, often with multiple parties -- be reasonable.
Try to focus and summarize in ways that constructively move the conversation forward.

### Asking for changes

It's okay to ask for changes to be made on a PR.
In your comments, you should be clear on what is a 'nit' or small thing to be improved and a **required** change needed to accept the PR.

Be clear and state upfront architectural or larger changes.
These should be resolved first before addressing any further nits.

It's also okay to say *"No"* to a PR.
As a community, we want to respect people's time and efforts, but sometimes things just don't make sense to accept.
As reviewers, you are the stewards of the code-base and sometimes that means pushing back on potential changes.

### Commit Hygiene

It can be seen as trivial, but you can ask the PR author to break apart their PR into smaller chunks, or change a commit message to be more informative.

### Be clear on progress and time

Be upfront with the PR author about where the state of their PR is and what needs to be completed for it to be accepted.

No one likes it if their PR misses a release, but it is a fact of life.
Try and be upfront about it.
Don't push a PR through out of guilt or deadlines.
