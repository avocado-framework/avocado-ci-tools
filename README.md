This repo contains a action to run various CI scripts 
needed by various of avocado projects.

## Supported tools:
- avocado-static-checks
- avocado-project manipulation

## Input

```yaml
avocado-static-checks:
  description: |
    Runs avocado-static-checks on pull requests.
    Default is false.
  default: false
  avocado-project:
    description: |
      Mr. avocado configuration for manipulating with PR and issues.
      Default is false.
    default: false
  bot_app_id:
    description: |
      Bot app ID which is needed to generate access token for bot. It is required by avocado-project.
    default: ''
  bot_app_installation_id:
    description: |
      Bot app installation ID which is needed to generate access token for bot. It is required by avocado-project.
    default: ''
  bot_app_private_key:
    description: |
      Bot app private key which is needed to generate access token for bot. It is required by avocado-project.
    default: ''
```
## Usage

```yaml
name: Pull Request
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
  workflow_dispatch:

jobs:
  avocado-static-checks:
    runs-on: ubuntu-latest
    steps:
        uses: avocado/avocado-ci-tools
        with:
          avocado-static-checks: true
```
