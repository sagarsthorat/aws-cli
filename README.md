# Setup AWS CLI Action

This GitHub Action sets up the AWS Command Line Interface (CLI) in your workflow, allowing you to interact with AWS services.

## Inputs

- `aws-version` (optional): The version of the AWS CLI to install. Defaults to the latest version.
- `aws-access-key-id` (required): The AWS access key ID to authenticate with.
- `aws-secret-access-key` (required): The AWS secret access key to authenticate with.
- `aws-region` (required): The AWS region to configure the CLI with.

## Example Usage

```yaml
name: AWS CLI Workflow
on:
  push:
    branches:
      - main

jobs:
  setup-aws-cli:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4
      
      - name: Setup AWS CLI
        uses: ./.github/actions/setup-awscli
        with:
          region: 'us-east-1'
          aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
          aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
          
```
