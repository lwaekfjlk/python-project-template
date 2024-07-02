# Open-Source Research Project in Python: A Template

[![Python 3.10](https://img.shields.io/badge/python-3.10-blue.svg)](https://www.python.org/downloads/release/python-3109/)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://pre-commit.com/)
<a href="https://github.com/psf/black"><img alt="Code style: black" src="https://img.shields.io/badge/code%20style-black-000000.svg"></a>
[![Checked with mypy](https://www.mypy-lang.org/static/mypy_badge.svg)](https://mypy-lang.org/)
[![bear-ified](https://raw.githubusercontent.com/beartype/beartype-assets/main/badge/bear-ified.svg)](https://beartype.readthedocs.io)
[![Github Action](https://github.com/lwaekfjlk/python-project-template/actions/workflows/tests.yml/badge.svg?branch=main)]()
[![Github Action](https://github.com/lwaekfjlk/python-project-template/actions/workflows/pre-commit.yml/badge.svg?branch=main)]()

> [!NOTE]
> This repo is continously updating with more tools. Any contribution is welcome.

## ✨ Motivation

To ensure high standards in engineering projects, we offer a standardized template specifically designed for open-source Python research projects. This template is an excellent choice if you:

1. Want to facilitate seamless collaboration and extension of your project by other researchers.
2. Aim to bridge communication gaps among collaborators effectively.
3. Seek to make rapid iterations with assurance that small code modifications won’t disrupt the overall project.
4. Wish to reduce the frequency of frustrating runtime errors during experiments.

## 🔨 Continuous Integration (CI) Workflow

Here's a clearer and more straightforward guideline of the steps for working with your codebase. If working in a small group or working on a simple project, some of the steps can be skipped.

1. **Create Issue**

   Before starting, open a new issue in the repository detailing what you plan to implement. Assign the issue to yourself.

2. **Sync Repo**

   Update your local repository to match the latest version of the remote repository.

3. **Create Branch**

   Create a new branch for your task. Name it appropriately based on the type of task, such as `feature/feature-name`, `bug/bug-name`, or `exp/exp-name`.

4. **Implement Code**

   Work on your task and make necessary changes to the codebase.

5. **Test Locally**

   Run tests using tools like mypy, pytest, and pre-commit. Ensure all tests pass before proceeding.

6. **Change Commit**

   Add and commit your changes to the branch, then push the branch to the repository.

7. **Create PR**

   Open a Pull Request (PR) for the branch you've pushed.

8. **Link PR to Issue**

   In your PR, include "Closes #ISSUE_NUM" to link it to the original issue.

9. **Pass Continuous Integration**

   Ensure all GitHub Actions checks pass. If they fail, revise your code based on the errors reported.

10. **Review PR Checklist**

    Verify that all items in the PR checklist are completed, such as updating documentation or adding package requirements.

11. **Ask for Code Review**

    Invite a colleague to review your PR. One approved, Use the "Squash and Merge" option to merge your PR, ensuring a clean commit history.

12. **Troubleshooting**

    If you break down the commit history or main branch, contact the repository owner for assistance with `rebase` or other needed actions.

## 💼 Template Structure

The current project template supports the final package release of our codebase.

```
Template/
│
├── .github/                  # Contains GitHub related files like workflows
├── docs/                     # Documentation for the project
├── src/                      # Main package directory
├── stubs/                    # Type stubs for static typing (for mypy strict mode)
├── tests/                    # Test scripts and resources
│
├── .gitignore                # Specifies untracked files to ignore
├── .pre-commit-config.yaml   # Configurations for pre-commit hooks
├── poetry.lock               # Lock file generated by poetry for dependencies
├── pyproject.toml            # Project metadata and tool configurations
```

## ❓ Issue & Pull Request

An issue typically describes a new feature (`feature`), fixing an old bug (`bug`), launching a group of experiments (`exp`), or refactoring part of the code (`refactor`). Using different issue templates for different issues.

A PR typically implements the content mentioned in one issue.

Notice about the development:

1. When creating an issue, assign the responsible member for fixing that if possible
2. When creating a PR, make sure you uses `feature/feature-name`, `bug/bug-name`, `exp/exp-name` for its branch
3. When finishing one PR, make sure all the github action is passed and all the checks are done.
4. When merging one PR, make sure using `squash and merge` instead of `merge a pull request`.
5. Avoid making any direct commit to the `main` branch and try to avoid any `--force` push to any branch unless you are pretty sure about that.

## 👷 Type Checking

* Tools

  * static type checking (`mypy`)

  * dynamic type checking (`beartype`)

* Guidelines
  * Run `mypy --strict ./` under the root of the current repo to test the static type.

## 🏅️ Unit Testing

* Tools
  * testing code components based on testing function (`pytest`)

* Guidelines
  * Run `pytest` under the root of the current repo to check unit test results.

## 🧐 Code Spell Checking

* Tools
  * code spell checking (`codespell`)

* Guidelines
  * Commonly need to ignore part of the files in the repository like `/data`.

## 🪝 Pre-commit Hook

* Tools

  * code formatting (`prettier`)

  * import package sorting (`isort`)

  * ipynb output clear (`nbstripout`)

  * code bug checking and formatting (`ruff`)

* Guidelines

  * Run `python -m pip install pre-commit` to install `pre-commit`

  * Run `pre-commit install` to allow hooking pre-commit with any `git commit` commands.

## 🧑‍💼 Dependency Management

* Tools
  * We utilize `poetry` to support the dependency requirements. Dependency for different usage of the repo can be defined separately in `pyproject.toml`.

* Guidelines

  * Run `pip install poetry` to finish the installation of poetry.

  * Create `conda environment` with a specified Python version

  * Run `poetry install` to install required dependencies.

## ❤️ Contribution

I welcome all kinds of contributions, e.g. adding more tools, better practices, and discussion on trade-offs.
