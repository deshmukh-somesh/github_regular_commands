# Common Branch Naming Conventions

## Feature Branches
For new features or enhancements:
* `feature/user-authentication`
* `feature/payment-gateway`
* `feature/search-optimization`
* `feat/user-profile`

## Bug Fix Branches
For fixing issues or bugs:
* `bugfix/header-display`
* `fix/login-error`
* `bug/payment-calculation`
* `hotfix/security-vulnerability` (for urgent fixes to production)

## Release Branches
For preparing releases:
* `release/1.0.0`
* `release/v2.3.1`
* `release/2023-Q2`

## Other Common Branch Types
* `docs/update-readme` (documentation changes)
* `refactor/authentication-flow` (code refactoring with no feature changes)
* `test/payment-integration` (adding or updating tests)
* `chore/update-dependencies` (maintenance tasks)
* `style/format-css` (formatting, no code change)

## Branch Naming Best Practices
1. **Use prefixes** to categorize branches (`feature/`, `bugfix/`, etc.)
2. **Use lowercase** letters for consistency
3. **Use hyphens or underscores** to separate words (be consistent)
4. **Be descriptive but concise** - aim for 2-4 words
5. **Include ticket/issue numbers** when applicable (`feature/user-auth-JIRA-123`)
6. **Avoid special characters** other than hyphens and underscores

## GitFlow Specific Conventions
If your team uses GitFlow, you'll typically have these permanent branches:
* `main` or `master` (production code)
* `develop` (development code)

And these temporary branches:
* `feature/*` (for new features)
* `release/*` (for release preparation)
* `hotfix/*` (for urgent production fixes)
* `bugfix/*` (for fixing bugs in development)