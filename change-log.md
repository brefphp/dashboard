## 2023-03-27

You can now **disable regions** in the region selector!

Useful if you are working in 1-2 regions and dislike having 15 regions showing up.

## 2023-03-07

New "**Terminal**" feature to run CLI commands in AWS Lambda 🎉

Works with Laravel Artisan, Symfony Console, and any function you deployed with the [Bref `console` layer](https://bref.sh/docs/runtimes/console.html).

To use it, open the Lambda function in the dashboard. You should see a new "Terminal" section.

## 2023-02-24

Multiple bugfixes in logs:

- Fixed older logs not being cleared when refreshing
- Improved log tailing (sometimes logs were duplicated)
- Fixed logs hidden behind the top menu bar

## 2023-02-11

AWS profiles using MFA (multi-factor authentication) are now supported!

## 2023-01-24

The Bref Dashboard is now out of beta 🎉

## 2023-01-11

The Bref Dashboard will soon come out of beta, read more about [the v1.0 launch here](https://github.com/brefphp/dashboard/blob/main/Launch.md).

## 2023-01-02

You can now read the changelog in the app!

## 2022-12-03

You can now search secrets.

When there are no databases in the application (i.e. the current stack), the "databases" page now shows all databases of the same region.

Added a button to reload AWS credentials, e.g. when SSO tokens have expired.

## 2022-12-02

Logs for a single invocation were broken in some situations. This should now be fixed!

Regions were also re-organized in the home view to put the most popular regions first.

## 2021-04-13

Users do not have to be allowed to list CloudFormation stacks anymore. In that case, [they will be prompted to add stacks by name](https://twitter.com/matthieunapoli/status/1382017987939553280). This is great for teams that don't want to give broad permissions to everyone.

## 2021-03-08

Queues: you can now send messages to a SQS queue.

## 2021-03-04

Various bug fixes and improvements in the Logs tab.

## 2021-02-10

New databases screen: it now shows DB metrics, and supports RDS DB instances as well as clusters (for example for RDS serverless).

## 2021-02-04

New onboarding panel for users that have no AWS credentials configured.

## 2021-02-03

New **Deployments** panel that shows CloudFormation deployments in real-time.

## 2021-01-27

View detailed metrics for API Gateway.

## 2021-01-22

View detailed metrics for Lambda functions.
