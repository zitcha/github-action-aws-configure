> :warning: **This is a *public* repository** :warning:

Custom Github Actions must be in a public repository (Except when using Github Enterprise which allows private repositories)

### Github Action - AWS Configure

This is a custom Github Action to configure AWS Credentials for a Github Workflow. 

#### Example

##### v1.1.0

```yaml
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Configure AWS credentials
        id: aws-configure
        uses: zitcha/github-action-aws-configure@v1.1.0
        with:
          env-name: ${{ inputs.env-name }}
          ENVIRONMENT_AWS_MAPPINGS: ${{ vars.ENVIRONMENT_AWS_MAPPINGS }}
```

##### v1.0.0

```yaml
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Configure AWS credentials
        uses: zitcha/github-action-aws-configure@v1.0.0
        with:
          role-to-assume: arn:aws:iam::123456789999:role/my-iam-role
```
