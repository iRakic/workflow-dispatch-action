# Workflow dispatch action

This is a GitHub Action that will trigger a workflow from another workflow.

## Arguments

| Argument Name            | Required   | Default     | Description                                                                            |
|--------------------------|------------|-------------|----------------------------------------------------------------------------------------|
| `owner`                  | True       | N/A         | The account owner of the repository. The name is not case sensitive.                   |
| `repo`                   | True       | N/A         | The name of the repository without the .git extension. The name is not case sensitive. |
| `ref`                    | False      | main        | The ID of the workflow. You can also pass the workflow file name as a string.          |
| `workflow_id`            | True       | N/A         | GitHub Personal Access Token (PAT) that has Actions repositotry permissions.           |
| `pat`                    | True       | N/A         | GitHub Personal Access Token (PAT) that has Actions repositotry permissions.           |

## Example Usage

```yaml
steps:
  - name: Trigger another workflow
    uses: iRakic/workflow-dispatch-action@v1
    with:
      owner: target-owner
      repo: target-repo-name
      ref: main  # Optional, defaults to 'main'
      workflow_id: 'main.yml'  # Can be workflow filename
      pat: ${{ secrets.GH_PAT }}
```