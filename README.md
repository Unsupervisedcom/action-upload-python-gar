<!-- start title -->

# GitHub Action:Upload Python Package to GAR

<!-- end title -->
<!-- start description -->

Extracts a Python package and uploads to Google Artifact Registry

<!-- end description -->
<!-- start contents -->
<!-- end contents -->
<!-- start usage -->

```yaml
- uses: Unsupervisedcom/action-upload-python-gar@undefined
  with:
    # Github token to use
    # Default: ${{ github.token }}
    token: ""

    # Release tag to fetch chart from
    # Default: ${{ github.event.release.tag_name }}
    tag: ""

    # Artifact registry scope
    # Default: @unsupervised
    scope: ""

    # gcloud service account credentials json
    credentials-json: ""

    # gcloud project id
    project-id: ""

    # the asset name containing the package, must be a tar file
    release-asset-name: ""

    # artifact registry region
    # Default: us-central1
    region: ""

    # artifact registry repository
    # Default: python
    repository: ""

    # the version of python to build with
    # Default: 3.10
    python-version: ""
```

<!-- end usage -->
   <!-- start inputs -->

| **Input**                | **Description**                                           |              **Default**               | **Required** |
| :----------------------- | :-------------------------------------------------------- | :------------------------------------: | :----------: |
| **`token`**              | Github token to use                                       |         `${{ github.token }}`          |  **false**   |
| **`tag`**                | Release tag to fetch chart from                           | `${{ github.event.release.tag_name }}` |  **false**   |
| **`scope`**              | Artifact registry scope                                   |            `@unsupervised`             |  **false**   |
| **`credentials-json`**   | gcloud service account credentials json                   |                                        |   **true**   |
| **`project-id`**         | gcloud project id                                         |                                        |   **true**   |
| **`release-asset-name`** | the asset name containing the package, must be a tar file |                                        |   **true**   |
| **`region`**             | artifact registry region                                  |             `us-central1`              |  **false**   |
| **`repository`**         | artifact registry repository                              |                `python`                |  **false**   |
| **`python-version`**     | the version of python to build with                       |                 `3.10`                 |  **false**   |

<!-- end inputs -->
   <!-- start outputs -->

| **Output**      | **Description** | **Default** | **Required** |
| :-------------- | :-------------- | ----------- | ------------ |
| `random-number` | Random number   |             |              |

<!-- end outputs -->
   <!-- start examples -->

### Example usage

```yaml
on: [push]

jobs:
  hello_world_job:
    runs-on: ubuntu-latest
    name: A job to say hello
    steps:
      - uses: actions/checkout@v2
      - id: foo
        uses: actions/hello-world-composite-action@v1
        with:
          who-to-greet: "Mona the Octocat"
      - run: echo random-number ${{ steps.foo.outputs.random-number }}
        shell: bash
```

<!-- end examples -->
<!-- start [.github/ghdocs/examples/] -->
<!-- end [.github/ghdocs/examples/] -->
