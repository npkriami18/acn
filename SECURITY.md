# Security policy

ACN runs a network server on a member's laptop and hands out keys, so security reports matter a lot.

## Reporting a vulnerability

**Please don't open a public issue for security problems.**

Report it privately through GitHub instead: go to the repository's **Security** tab and click
**Report a vulnerability** ([direct link](https://github.com/npkriami18/acn/security/advisories/new)).

Please include:

- what an attacker can do, and what they need first (on the same network? knows the team code? is a member?)
- steps to reproduce, or a proof of concept
- your OS and Python version

You'll get a reply within a week. Once a fix is ready, we'll publish an advisory and credit you unless you'd rather
stay anonymous.

## Supported versions

Only the latest version on `main` gets security fixes.

## What's in scope

For example: joining without the team code, taking or reusing another member's key, sending as someone else,
reading messages meant for someone else, attacks through the shared page (XSS, CSRF), a fake hub stealing keys,
abusing `takeover` or `restore`, and crashing the hub remotely.

Not in scope: someone who already controls the host's laptop or a member's laptop, and problems on networks the team
chose to expose the hub to on purpose (for example, sharing the tunnel address and team code publicly).
