# Contributing to ACN

Thanks for helping. Bug reports, fixes, docs and ideas are all welcome.

## Ground rules

ACN's whole promise is "one file, nothing to install". Changes have to keep it that way:

1. **Standard library only.** No third-party packages, in `acn.py` or in the tests.
2. **One file.** All the code lives in `skills/acn/acn.py`; `skills/acn/SKILL.md` is what teaches an agent to use it.
3. **Python 3.9+.** Don't use syntax or library features newer than 3.9.
4. **Windows, macOS and Linux.** Members run ACN on all three. Avoid platform-only calls, or guard them.
5. **Every change comes with a test** in `tests/test_acn.py`, and existing tests keep passing.
6. **Security first.** ACN is a network server that hands out keys. Anything touching joining, keys, the shared page
   or takeover needs a test showing it can't be abused. Found a vulnerability? Don't open an issue: see
   [SECURITY.md](SECURITY.md).

If you're planning something big (a new command, a protocol change), open an issue first so we can agree on the
approach before you spend time on it.

## Running the tests

```bash
python3 -m unittest discover -s tests
```

The suite starts real hubs on local ports and takes a few minutes. Each test uses its own temporary `ACN_HOME`, so it
won't touch your real ACN membership.

The tunnel test is skipped by default. To run it you need [`cloudflared`](https://github.com/cloudflare/cloudflared)
and internet access:

```bash
ACN_TEST_TUNNEL=1 python3 -m unittest tests.test_acn.TunnelTest
```

CI runs the suite on Windows, macOS and Linux for every pull request.

## Making a pull request

1. Fork the repo and create a branch from `main`.
2. Make your change, with a test.
3. If you changed a command or how something behaves, update `README.md` and `skills/acn/SKILL.md` to match.
4. Run the tests.
5. Open a pull request and fill in the template.

Keep pull requests focused: one fix or feature each is much easier to review.

## Style

Follow what's already in `acn.py`: short functions, plain names, comments that explain *why*. Test names describe
the behaviour in plain words, like `test_leaving_cancels_your_key`.

## Code of conduct

Everyone taking part is expected to follow the [Code of Conduct](CODE_OF_CONDUCT.md).

By contributing, you agree that your contributions are licensed under the [MIT License](LICENSE).
