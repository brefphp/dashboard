# Permissions for the Bref Dashboard

The [Bref Dashboard](https://dashboard.bref.sh/)is an application running on your computer.

To show data from your AWS account, the application uses the official AWS SDK to query the AWS API.

And to authenticate the AWS API, **it uses the IAM credentials that are set up on your computer.**

## AWS credentials

All AWS tools, like the `aws` CLI, [read credentials from the `~/.aws/credentials` file](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html).

Since the Bref Dashboard uses the official SDK, **it will automatically pick up those credentials**.

That means there are 2 scenarios:

- You have already set up AWS credentials on your computer: the Bref Dashboard will work out of the box.
- You haven't: you will need to configure AWS credentials

### Setting up credentials

You are welcome to follow [the official AWS guide on setting up credentials](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html#cli-configure-quickstart-config).

[This illustrated guide](https://bref.sh/docs/installation/aws-keys.html) can also help.

Then, configure access keys by running `aws configure` or manually creating the `~/.aws/credentials` file:

```
[default]
aws_access_key_id = AKIAI44QH8DHBEXAMPLE
aws_secret_access_key = je7MtGbClwBF/2Zp9Utk/h3yCo8nvbEXAMPLEKEY
```

If you are struggling, [open a GitHub discussion](https://github.com/brefphp/dashboard/discussions) to get some help.
