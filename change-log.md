## 2023-06-19

**Brand new log viewer!**

The log viewer has been entirely rewritten:

- Searching and loading logs in the past works all the time now − if you had any frustration with logs in the Dashboard, that should be the big fix
- Search using **regex** if you want
- Loading the logs of a single Lambda invocation now works all the time (no more "Could not find the START line") thanks to a much better algorithm, and it will now even show logs from the cold start (before the START line)
- You can now clear the screen: super helpful when "Live tailing" and you want to only see the new logs
- Display up to 1,000 logs max, instead of 100 previously
- When there are more than 1,000 logs, you now get a warning (so you know you should filter down further)
-Lots of quality of life improvements:
    - dim out more boring logs (even those produced by PHP-FPM)
    - shorten the function names to give more room to
    - fixed many small bugs, e.g. when clicking a function name to
    - fix live tailing in some scenarios
    - the UI should be much more stable, especially when clicking lots of filters/buttons and re-loading logs before the first one wasn't finished loading
    - you can also stop the current query
    - the "Loading" indicator now shows how many logs are being parsed for long-running queries (so that you see some progress is happening)
- The downsides: loading logs is slightly slower (2-3s instead of 1-2s), and logs have a 60s delay unless you activate "Live tailing"

Let me know if you have any issues!

## 2023-06-12

**Cost analysis!**

In each application, you can now click the "Total costs" panel to view a detailed view of the costs for each service.

## 2023-06-08

You can now **retry all failed messages** of a SQS Dead Letter Queue.

Previously you had to retry each message manually. Now you can also retry all messages at once.

## 2023-05-31

You can now see the number of messages being processed (in-flight) in the **Queues** tab.

Additionally, the number of "messages queued" now includes messages that are delayed.

## 2023-05-25

Analyze your cold starts!

In a Lambda function, click the "Analyze cold starts" button. You will get an overview of cold starts duration and frequency.

## 2023-05-22

**SSO is now supported!** 🎉

If you use AWS SSO (aka IAM Identity Center) in your AWS profile, these are now supported! You will need to update the app (it will update automatically) and your SSO profiles will now work.

## 2023-05-17

Your desktop application should update itself (if not, [you can download the latest version here](https://download.dashboard.bref.sh/)). The new version includes a lot of security updates. Let me know if you have any trouble.

One unfortunate consequence of all the Electron updates is that you will have to log in again. Sorry about that!

The update also prepares the way for SSO support. I've been working on it for several days now, hopefully this shouldn't be long.

## 2023-05-11

Fixed a bug for users with an empty `default` profile.

## 2023-04-14

Fixed a bug when running CLI commands that run for more than 60 seconds (commands were retried).

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
