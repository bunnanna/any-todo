## Submodule Setup (Reference Only)

This repository uses a Git submodule that is **tracked but not checked out by default**.
Only the submodule reference (commit + branch) is stored to avoid pulling the full codebase.

### Add submodule (track `main`)

    git submodule add -b <branch-name> <submodule-repo-url> <submodule-path>

Example:

    git submodule add -b main https://github.com/bunnanna/todo-api-test.git test/api

### Remove checked-out files (keep reference only)

    git submodule deinit -f <submodule-path>
    rm -rf <submodule-path>

Example:

    git submodule deinit -f test/api
    rm -rf test/api

---

### Restore submodule code (when needed)

    git submodule update --init --remote <submodule-path>

Example:

    git submodule update --init --remote test/api

---

### Notes

- The submodule tracks the `<branch-name>` branch (e.g. `main`)
- By default, the submodule directory is **not present**
- CI and developers must explicitly initialize the submodule if code is required
