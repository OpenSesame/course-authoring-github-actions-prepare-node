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

## Reving major (LTS) version of Node

As specified in section above, to increase the major version of Node setup by this action, you can create a commit with `#major` in the git commit message as specified above and change the version installed by the actions/setup-node@v3.3.0 to use the new LTS version of Node. This then allows users of this action to upgrade to newer Node (or other dependency) versions when possible.
