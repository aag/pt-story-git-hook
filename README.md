Pivotal Tracker Git Commit Hook
===============================
This is a git commit-msg hook to require that commit messages always contain a Pivotal Tracker story number.  It checks for a line in each commit message that looks something like this:

```
[#283882]
```

[Pivotal Tracker](https://www.pivotaltracker.com/) is an agile project management website.  It offers [integration with git](https://www.pivotaltracker.com/help/api#scm_post_commit) through putting story numbers and keywords in commit messages.  The problem is that it's easy to forget to put the story number in your commit message when you're in the flow of coding.

This git hook makes sure that a PT story number is included in every commit message.  It is not intended as a validator, so it does not verify that valid Pivotal Tracker syntax has been used.  Instead, it just checks for something that looks like a PT story number and it's up to you to make sure it's formatted correctly.

Installation
------------
If you don't have any other commit-msg hooks in your repository yet, you can simply download the commit-msg file from this project to the `.git/hooks` directory in the repo.  If you have other commit-msg hooks, you can append the contents of the commit-msg file from this project to your existing `.git/hooks/commit-msg` file.


Skipping Verification
---------------------
Sometimes you want to make a commit that isn't attached to any particular Pivotal Tracker story.  There are two ways to skip the requirement.

You can skip running all commit-msg and pre-commit hooks by using the `--no-verify` or `-n` command line flags.  Your commit command would then look something like this:

```
git commit -n
```

Alternatively, instead of adding a PT story number to the commit message, you can add a line like this instead:

```
[no-pt-story]
```

License
-------
This code is free software licensed under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.
