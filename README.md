# github-actions-workflow-study
Repo for examples of GitHub Actions workflow 

## Background Step Sample

Workflow file:

- `.github/workflows/background-hello.yml`

Trigger:

- `workflow_dispatch`

What it does:

1. Starts two background steps (`hello1`, `hello2`) with different sleep times.
2. Runs a normal foreground step while background steps are still active.
3. Uses `wait: [hello1, hello2]` to wait for both background steps.

## Wait Step Sample

Workflow file:

- `.github/workflows/parallel-hello.yml`

Trigger:

- `workflow_dispatch`

What it does:

1. Starts three background steps with ids `hello1`, `hello2`, `hello3`.
2. Uses `wait: [hello1, hello2, hello3]` to join those steps.
3. Runs a final `Done` step after all hello steps finish.
