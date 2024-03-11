# actions_python_ruff
A Github action for python linting with ruff.


<br/>

## How to use
In your .github/workflows directory, create a yaml file (such as main.yaml). Add a job for each desired workflow with the `uses` keyword. Use the `with` keyword to pass any desired variables.

Examples:

```
on: [push]

jobs:
  ruff:
    runs-on: ubuntu-latest
    name: "ruff"
    steps:
      - uses: davidslusser/actions_python_ruff@v1.0.1
```
<br/>

```
on: [push]

jobs:
  ruff:
    runs-on: ubuntu-latest
    name: "ruff"
    steps:
      - uses: davidslusser/actions_python_ruff@v1.0.1
        with:
          src: "src"
          options: "--cov=src"
          pip_install_command: "pip install -e .[dev]"
          python_version: "3.9"
```


<br/>

## Inputs
  - **src:** source directory of code to check (defaults to "`.`")
  - **options:** optional flags/parameters used in ruff command
  - **pip_install_command:** pip install command (defaults to "`pip install ruff`")
   - **python_version:** version of python to run workflow with (defaults to "`3.x`")


<br/>

## References
 - https://beta.ruff.rs/docs/
 - https://pypi.org/project/ruff/0.0.47/
