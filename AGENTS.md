# Contributing to Orbit

The Orbit project welcome community contributors.
To contribute to it, please follow guidelines here.

The codebase is hosted on Github at https://github.com/uber/orbit.

All code need to follow the [PEP8 style guide](https://www.python.org/dev/peps/pep-0008/) with a few exceptions listed
in [tox.ini](./tox.ini).

Before contributing, please review [outstanding issues](https://github.com/uber/orbit/issues).
If you'd like to contribute to something else, open an issue for discussion first.

# Set the OS, Python version and other tools you might need
build:
  os: ubuntu-22.04
  tools:
    python: "3.9"

# Build documentation in the docs/ directory with Sphinx
sphinx:
  configuration: docs/conf.py

# Optionally build your docs in additional formats such as PDF and ePub
formats: all

# Optionally set the version of Python and requirements required to build your docs
python:
  install:
    - requirements: requirements.txt
    - requirements: docs/requirements-docs.txt

## Testing

After your changes and before submitting a pull request, make sure the change to pass all tests and test coverage
to be at least 70%.

```bash
$ pytest -vs tests/ --cov orbit/
```

## Linting

You can run black linting to lint the code style.

### Linting one single file

```bash
$ black <file path>
```

### Linting every file under the current directory

```bash
$ black .
```

### Outputting the code change black would have done without actually making change

```bash
$ black --diff <file path>
```

# Submission

In your PR, please include:

- Changes made
- Links to related issues/PRs
- Tests
- Dependencies
- References

Please add the core Orbit contributors as reviewers.

## Merging and Releasing versions

We use squash and merge for changes onto `dev` branch. However, due to history comparison, from `dev` to `release`
and `master`, we use rebase and merge. For release details, please refer to [RELEASE.md](./RELEASE.md)