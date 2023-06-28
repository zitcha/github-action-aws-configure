> :warning: **This is a *public* repository** :warning:

Custom Github Actions must be in a public repository (Except when using Github Enterprise which allows private repositories)

### Github Action - AWS Configure

This is a custom Github Action to configure AWS Credentials for a Github Workflow. 

#### Example

```yaml
    steps:
      - name: Checkout
        uses: actions/checkout@v3

      - name: Configure AWS credentials
        uses: the-pistol/github-action-aws-configure@main
        with:
          role-to-assume: arn:aws:iam::123456789999:role/my-iam-role
```
