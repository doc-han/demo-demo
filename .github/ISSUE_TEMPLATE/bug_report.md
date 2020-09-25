---
name: Bug report
about: Create a report to help us improve
title: ''
labels: bug
assignees: ''

---

**Describe the bug**
A clear and concise description of what the bug is.

**To Reproduce**
Steps to reproduce the behavior:
#### expression.js
Link to the job itself in Github

#### state.json

Either provide state directly, or link to a file. If sensitive information
should be in state, redact it and provide instructions for where it can be
found.

```json
{
  "configuration": { "username": "abc", "password": "REDACTED" },
  "data": { "a": 1 },
  "cursor": "2020-01-19 00:00:00"
}
```

```json
{
  "configuration": ["SEE LAST PASS: 'client cred'"],
  "data": { "a": 1 },
  "cursor": "2020-01-19 00:00:00"
}
```

**Expected behavior**
A clear and concise description of what you expected to happen.

**Screenshots**
If applicable, add screenshots to help explain your problem.

**Additional context**
