> :warning: **This is a *public* repository** :warning:

Custom Github Actions must be in a public repository (Except when using Github Enterprise which allows private repositories)

### Github Action - Zitcha AWS Configure

This is a custom Github Action to configure AWS Credentials for some Zitcha Deployments.
Use this in situations that need to be aware of `ENVIRONMENT_AWS_MAPPINGS`. Otherwise, it might be more suitable
to just use https://github.com/aws-actions/configure-aws-credentials action directly.

#### Github Workflow Permissions

The Workflow which uses this action must have these permissions as a minimum:

```yaml
permissions:
  id-token: write
  contents: read
```

Further info:
* https://github.com/aws-actions/configure-aws-credentials?tab=readme-ov-file#oidc
* https://aws.amazon.com/blogs/security/use-iam-roles-to-connect-github-actions-to-actions-in-aws/

#### Usage

##### v1.1.0

```yaml
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Configure AWS credentials
        id: aws-configure
        uses: zitcha/github-action-aws-configure@v1.1.0
        with:
          env-name: ${{ inputs.env-name }}
          ENVIRONMENT_AWS_MAPPINGS: ${{ vars.ENVIRONMENT_AWS_MAPPINGS }}
```

##### v1.0.0 (Deprecated)

```yaml
    steps:
      - name: Checkout
        uses: actions/checkout@v4

      - name: Configure AWS credentials
        uses: zitcha/github-action-aws-configure@v1.0.0
        with:
          role-to-assume: arn:aws:iam::123456789999:role/my-iam-role
```
