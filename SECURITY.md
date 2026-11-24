# Security policy

This policy covers every repository in the RSE skill suite.

## Supported versions

Only the latest release of each repository receives fixes. The current versions are listed on each
repository's Releases page.

## Reporting a vulnerability

Please do not open a public issue. Report it privately through GitHub instead: open the affected repository's
**Security** tab and choose **Report a vulnerability**. Include the skill or script, its version, the agent and
model you used, and the smallest steps or prompt that show the problem. Remove secrets and personal data first.

Reports are handled on a best-effort basis by the maintainer. You will get a reply in the advisory thread, and
fixed issues are credited in the release notes unless you prefer otherwise.

## Scope

In scope:

- Skill text that steers an agent into an unsafe action, such as touching production, exposing secrets,
  weakening a control, or editing code during a request that was only a review.
- The scripts shipped in the repositories: the task-pack validator, the refactoring check recorder, the skill
  linter and the eval runner and harness.

Out of scope:

- The eval runner's `--allow-exec` option runs agent-written code as your user. That is its documented purpose;
  use it only with the suite's own fixtures, ideally in a disposable VM or container.
- Vulnerabilities in Claude Code, Codex or other agents themselves. Report those to their vendors.
