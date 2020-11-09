# Overview

We use two labels `contributor/help-wanted` and `contributor/good-first-issue`
to identify issues that have been specially groomed for both existing and new contributors. 
The `contributor/good-first-issue` indicates that members have committed to providing extra assistance for new contributors.

We also have some suggestions for using these labels to help grow and improve our community.

## Help Wanted

Items marked with the `contributor/help-wanted` label need to ensure that they are:

- **Low Barrier to Entry**

    It should be tractable for new contributors.
    Documentation on how that type of change should be made should already exist.

- **Clear Task**

    The task is agreed upon and does not require further discussions in the community.
    Call out if that area of code is untested and requires new fixtures.

    API / CLI behavior is decided and included in the OP issue,
    for example: *"The new command syntax is `foo bar NAME [--unFoo] [--timeout 5m]`"*,
    with expected validations called out.

- **Goldilocks priority**

    Not too high that a core contributor should do it,
    but not too low that it isn't useful enough for a core contributor to spend time to review it,
    answer questions, help get it into a release, etc.

- **Up-To-Date**

    Often these issues become obsolete and have already been done,
    are no longer desired, no longer make sense, have changed priority or difficulty, etc.
    The maintainers of Traefik regularly groom and manage these issues to ensure they remain relevant.

## Good First Issue

Items marked with the `contributor/good-first-issue` label are intended for *first-time contributors*.
It indicates that maintainers will keep an eye out for these pull requests
and shepherd it through our processes.

**New contributors should not be left to find an approver, ping for reviews,
or identify that their build failed due to a flake.**

This makes new contributors feel welcome and valued,
further assuring them that they will have an extra level of help with their first contribution.

After a contributor has successfully completed 1-2 `contributor/good-first-issue`'s, 
they should be ready to move on to `contributor/help-wanted` items,
saving remaining `contributor/good-first-issue`'s for other new contributors.

These items need to ensure that they follow the guidelines for `contributor/good-first-issue` labels (above)
in addition to meeting the following criteria:

- **No Barrier to Entry**

    The task is something that a new contributor can tackle without advanced setup or domain knowledge.

- **Solution Explained**

    The recommended solution is clearly described in the issue.

- **Provides Context**

    If background knowledge is required, 
    this should be explicitly mentioned and a list of suggested readings included.

- **Gives Examples**

    Link to examples of similar implementations so new contributors have a reference guide for their changes.

- **Identifies Relevant Code**

    The relevant code and tests to be changed should be linked in the issue.

- **Ready to Test**

    There should be existing tests that can be modified, or existing test cases fit to be copied.
    If the area of code doesn't have tests, before labeling the issue, add a test fixture.
    This prep often makes a great `contributor/good-first-issue` task!

# Suggestions

We encourage our more experienced members to help new contributors
so that the Traefik community can continue to grow and maintain the kind,
inclusive community that we all enjoy today.

The following suggestions go a long way toward preventing "drive-by" PRs,
and ensure that our investment in new contributors is rewarded
by them coming back and becoming regulars.

Provide extra assistance during reviews on `contributor/good-first-issue` pull requests:

- Answer questions and identify useful docs.
- Offer advice such as *"One way to reproduce this in a cluster is to do X
and then you can use the GDB to poke around"*,
or *"Did you know that you can use fake clients to setup and test this easier?".*
- Help new contributors learn enough about the project, setting up their environment,
running tests, and navigating this area of the code
so that they can tackle a related `contributor/help-wanted` issue next time.

If you make someone feel like a part of our community, that it's safe to ask questions,
that people will let them know the rules/norms, that their contributions are helpful 
and appreciated... they will stick around! 🌈

- Encourage new contributors to seek help on the appropriate discussion forums,
introduce them, and include them in your conversations.
- Invite them to the officially join the Traefik Ambassador Program
and contributor meetings.
- Give credit to new contributors so that others get to know them,
*"Hey, would someone help give a second LGTM on @newperson's first PR on chocolate bunnies?"*.
Mention them in the Ambassador discord, thank them on twitter.
- Use all the emoji in your approve or lgtm comment. 💖 🚀
Also gifs, use gifs.  
- Let them know that their `contributor/good-first-issue` is getting extra attention
to make the first one easier and help them find a follow-up issue.
- Suggest a related `contributor/help-wanted` issue so that can build up experience in an area.
- People are more likely to continue contributing when they know what to expect,
what's the acceptable way to ask for people to review a PR,
nudge things along when a PR is stalled. Show them how we operate
by helping move their first PR along.
- If you have time, let the contributor know that they can DM you on the Ambassador discord
with questions that they aren't yet comfortable asking the wider group.
