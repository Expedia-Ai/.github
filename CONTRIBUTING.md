# CONTRIBUTING

Contributions are always welcome, no matter how large or small. 

Some thoughts to help you contribute to this project

## Recommended Communication Style

1. Always leave screenshots for visuals changes
2. Always leave a detailed description in the Pull Request. Leave nothing ambiguous for the reviewer.
3. Always review your code first. Do this by leaving comments in your coding noting questions, or interesting things for the reviewer.
4. Always communicate. Whether it is in the issue or the pull request, keeping the lines of communication helps everyone around you.

## Setup

Our repositories are private: work on a branch in the repository itself, not on a fork.

Clone the repo using the docs over at [cloning a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository).

Most of our repositories will use one of [Node.js](https://nodejs.org/en), [Python](https://www.python.org), or [Go](https://golang.org) for development. Please ensure you have the correct version of the language installed.

Each programming language will have a package manager, we will be generally using the one that is most supported and deterministic. Here's an example using [npm](https://docs.npmjs.com/getting-started) for package management: 

```shell
# use either of ssh or gh cli to clone the repo 
git clone git@github.com:Expedia-Ai/<repository-name>.git
gh repo clone Expedia-Ai/<repository-name>

# change directory into the repo and install dependencies the deterministic way
cd <repository-name>
npm ci

# start the local development server
npm run dev
```

## Testing

For running the test suite, use the following command. Since the tests run in watch mode by default, some users may encounter errors about too many files being open. In this case, it may be beneficial to [install watchman](https://facebook.github.io/watchman/docs/install.html).

```shell
# the tests will run in watch mode by default
npm test

# optionally, you can lint and format most projects
npm run lint
npm run format
```

## Pull Requests

### _We actively welcome your pull requests; each one links its Linear issue._

1. Create your branch from `beta` or DEFAULT branch if different, in the repository (no forks). `beta` is the pull request target; `main` is production.
2. Name your branch after the Linear issue, i.e. `eai-42-adds-new-thing`.
3. If you've added code that should be tested, add tests.
4. If you've changed APIs, update the documentation.
5. If you make visual changes, screenshots are welcome.
6. Ensure the test suite passes.
7. Make sure you address any lint warnings.
8. If you make the existing code better, please let us know in your PR description.
9. A PR description and title are required. The title is required to begin with one of: "feat:", "fix:", "docs:", "style:", "refactor:", "perf:", "test:", "build:", "ci:" or "revert:" ("chore:" is reserved for automation)
10. Link the Linear issue (`EAI-…`) in the PR description and end the PR title and your commit messages with its key. An issue is required to announce your intentions. PR's without a linked issue will be marked invalid and closed.

### PR Validation

Examples for valid PR titles:

- `fix: Correct typo (EAI-42)`
- `feat: Add support for Node 21 (EAI-42)`
- `refactor!: Drop support for Node 6 (EAI-42)`

_Note that since PR titles only have a single line, you have to use the ! syntax for breaking changes._

See [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) for more examples.

### Work in progress
GitHub has support for draft pull requests, which will disable the merge button until the PR is marked as ready for merge.
