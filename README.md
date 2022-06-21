# course-authoring-github-actions-prepare-node

A github action to prepare CI/CD process for building and testing a node-based application.

## Specifying Secrets

To use the Github access token stored within AWS Secrets Manager, you need to specify the following parameters:
- `aws-access-key-id`
- `aws-secret-access-key`
- `aws-region` (defaults to "us-west-2")
- `aws-role-arn`

## Other Action Inputs

There are other inputs for this action that help control its behavior:
- `create-env-file`. Whether build:env should be run to generate an env file or not. This is typically true in UIs, but false in libraries.

## Bumping the library version

The major and minor versions of the library must be manually changed by adding `#major` or `#minor` as part of the commit message. More information can be found here: https://github.com/anothrNick/github-tag-action
