# Cascading Merge3

This is a trial repository for testing cascading merge within a git repo. It uses the [Cascading Auto-Merge Action](https://github.com/marketplace/actions/cascading-auto-merge-action) to automatically merge changes from lower release branches into higher ones based on semantic versioning, similar to [Bitbucket's Automatic Branch Merging](https://confluence.atlassian.com/bitbucketserver/automatic-branch-merging-776639993.html).

## How it works

<test line added to release 1.0.0>
<release/2.0.0 test>
When a pull request is merged into a `release/` branch, the cascading merge action automatically opens pull requests to merge those changes into all subsequent release branches (ordered by semantic version), and finally into the `development` branch.

<test line added to release 2.0.0 branch>
<release/2.0.0 test>

<testing protected branches>

## Branch Structure

Branches should follow semantic versioning under the `release/` prefix:

- `release/1.0.0`
- `release/1.1.0`
- `release/2.0.0`
- `development`

## Setup

See `.github/workflows/cascading-merge.yml` for the workflow configuration.
