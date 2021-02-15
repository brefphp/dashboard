[< Back to the documentation](https://github.com/brefphp/dashboard)

# Permissions for the Bref Dashboard

The [Bref Dashboard](https://dashboard.bref.sh/) is an application that runs on your computer.

To show data from your AWS account, the application uses the official AWS SDK to query the AWS API. And to authenticate the AWS API, **it uses the IAM credentials that are set up on your computer.**

## AWS credentials

All AWS tools, like the `aws` CLI, [read credentials from the `~/.aws/credentials` file](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html).

Since the Bref Dashboard uses the official SDK, **it will automatically pick up those credentials**.

That means there are 2 scenarios:

- You have already set up AWS credentials on your computer: the Bref Dashboard will work out of the box.
- You haven't: you will need to configure AWS credentials

### Configuring credentials

First, create IAM access keys by following [the official AWS guide on setting up credentials](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html#cli-configure-quickstart-config). This [simpler guide](https://bref.sh/docs/installation/aws-keys.html) can also help.

Then, configure access keys by running `aws configure` or manually creating the `~/.aws/credentials` file:

```
[default]
aws_access_key_id = AKIAI44QH8DHBEXAMPLE
aws_secret_access_key = je7MtGbClwBF/2Zp9Utk/h3yCo8nvbEXAMPLEKEY
```

If you are struggling, [open a GitHub discussion](https://github.com/brefphp/dashboard/discussions) to get some help.

## Permissions

Since the Bref Dashboard uses the IAM credentials from `~/.aws/credentials`, it will have the permissions from those credentials.

This is a good thing: **AWS administrators do not have to think about creating new permissions**. The developers that already have access to some features of the AWS account will be able to use the Bref Dashboard with their current permissions.

Here is a concrete example: if a developer has read-only access to a specific Lambda function and S3 bucket, then they will be able to use the AWS Dashboard on those resources. The Dashboard will not be able to do anything else, because it uses the developer's credentials.

To summarize, grant access to AWS resources, and the Dashboard will reflect that. It is no different than the official AWS CLI.

## IAM profiles

The Bref Dashboard supports all IAM profiles configured in `~/.aws/credentials`. When selecting an application, you can easily change region and AWS profile:

![](https://i.imgur.com/ArseGsc.png)

[< Back to the documentation](https://github.com/brefphp/dashboard)
