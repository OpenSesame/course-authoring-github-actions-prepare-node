# course-authoring-github-actions-prepare-node

A github action to prepare CI/CD process for building and testing a node-based application.

## Specifying Secrets

There are two ways that secrets can be provided to this action, based on which mechanism the user repos is using (e.g. AWS Secrets Manager, or DevOps-provided Github secret).

To use the Github access token stored within AWS Secrets Manager, you need to specify the following parameters:
- `aws-access-key-id`
- `aws-secret-access-key`
- `aws-region` (defaults to "us-west-2")
- `aws-role-arn`

To use the Github access token provided by DevOps, use the input parameter `org-auth-token`.

## Other Action Inputs

There are a couple of other inputs for this action that help control its behavior:
- `create-env-file`. Whether build:env should be run to generate an env file or not. This is typically true in UIs, but false in libraries.
- `node-version`. The version of Node to install and pass into to actions/setup-node. "16.x" for example.

## Bumping the library version

The major and minor versions of the library must be manually changed by adding `#major` or `#minor` as part of the commit message. More information can be found here: https://github.com/anothrNick/github-tag-action