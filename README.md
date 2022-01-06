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
    # Google credentials json
    credentials-json: ""

    # Google cloud project id
    project-id: ""

    # Python package name
    package-name: ""

    # Version to publish
    # Default: ${{ github.event.release.tag_name }}
    version: ""

    # Artifact registry scope
    # Default: @unsupervised
    scope: ""

    # Artifact registry repository name
    # Default: python
    repository: ""

    # Artifact registry location
    # Default: us-central1
    location: ""

    # Location of package
    # Default: dist/*
    dist-directory: ""
```

<!-- end usage -->
   <!-- start inputs -->

| **Input**              | **Description**                   |              **Default**               | **Required** |
| :--------------------- | :-------------------------------- | :------------------------------------: | :----------: |
| **`credentials-json`** | Google credentials json           |                                        |   **true**   |
| **`project-id`**       | Google cloud project id           |                                        |   **true**   |
| **`package-name`**     | Python package name               |                                        |   **true**   |
| **`version`**          | Version to publish                | `${{ github.event.release.tag_name }}` |  **false**   |
| **`scope`**            | Artifact registry scope           |            `@unsupervised`             |  **false**   |
| **`repository`**       | Artifact registry repository name |                `python`                |  **false**   |
| **`location`**         | Artifact registry location        |             `us-central1`              |  **false**   |
| **`dist-directory`**   | Location of package               |                `dist/*`                |  **false**   |

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
