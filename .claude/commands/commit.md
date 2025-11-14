Create a git commit following Conventional Commits specification.

Review the current changes with git status and git diff, then create a commit using this format:

type(scope): description

Available types: feat, fix, build, chore, ci, docs, style, refactor, perf, test

Examples:
- feat: add user authentication
- fix(api): handle null responses
- chore(deps): update spring boot to 3.5.7

Instructions:
1. Check git status and git diff to see all changes
2. Stage relevant files with git add
3. Create commit with appropriate type and clear description
4. Include Claude Code signature in commit message
5. Use HEREDOC format for multi-line commit messages to avoid command injection issues

Do not push unless explicitly requested.
