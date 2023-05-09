# Reusable Github actions

To provide a more unified approach to a complex project we can use *reusable* GitHub actions. More on that can be read
here: [Reusing workflows - GitHub Docs](https://docs.github.com/en/actions/using-workflows/reusing-workflows).

This repo consists of many workflows which can be used by calling them with:

```yml
uses: DataScienceClubPG/sairn-github-actions/.github/workflows/workflows.yml@main
```

in the local workflow file. It is also needed to provide secrets and inputs to the call.

```yml
jobs:
  some-workflow-call:
    uses: DataScienceClubPG/sairn-github-actions/.github/workflows/workflows.yml@main
    secrets:
      envPAT: ${{ secrets.envPAT }}
```

or simply (if we use the workflow in the same organization):

```yml
jobs:
  some-workflow-call:
    uses: DataScienceClubPG/sairn-github-actions/.github/workflows/workflows.yml@main
    secrets: inherit
```

GitHub Workflow from [terraform-databricks.yml](.github%2Fworkflows%2Fterraform-databricks.yml) is
used [in this repo](https://github.com/DataScienceClubPG/sairn-databricks).
