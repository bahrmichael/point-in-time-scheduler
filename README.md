# point-in-time-scheduler

> Update: In November 2022 AWS has released the EventBridge Scheduler. It does what I expect from a serverless scheduler, and has a free tier of 14 million invocations per month. Therefore, I'm deprecating this project.

This repository holds public resources for the point in time scheduler. The source code is not open source.

## Documentation

[Go to the documentation](https://github.com/bahrmichael/point-in-time-scheduler/tree/main/docs).

## Upcoming

- Documentation Pages
- Control and Data Plane APIs

## Release Notes

You can get notifications about new release notes by clicking on the Watch button in the top right. If you'd rather get a mail into your inbox, I suggest you check out the [GitHub File Watcher](https://app.github-file-watcher.com/).

### 25.01.2022

The scheduler now supports SQS as a delivery target. With SQS the scheduler achieves higher time precision using the [`DelaySeconds` attribute](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-delay-queues.html). Messages will become visible at the time you specified when scheduling the message.

When you register an application, you can now choose between REST and Amazon SQS integration. You need an SQS queue which has the following resource policy.

```
PolicyDocument: {
  Statement: [{
    Action: ["sqs:SendMessage"],
    Effect: ["Allow"],
    Resource: ["<your-queue-arn>"],
    Principal: {
      AWS: ["710154449298"]
    }
  ]}
}
```

This resource policy allows the scheduler (AccountId 710154449298) to send messages to your queue.

### 17.01.2022

Based on customer feedback, the scheduler can now return messages without wrapping them in a payload field. You can now choose the mode when creating an application.

---

![Mode Choice Preview](https://github.com/bahrmichael/point-in-time-scheduler/blob/main/mode-choice-preview.png)

---

### 11.01.2022

You can now view message logs. This is helpful to understand why a message has not been delivered to your endpoint.

To view logs of a message, go to your application, then to messages, and then open a message by clicking on its ID.

### 10.01.2022

New quick start experience for the Point In Time Scheduler.

The quick start helps you to schedule your first message. Thanks to http://webhook.site you don't even need to set up your own endpoint.

### 06.01.2022

[Launch of the public preview](https://bahr.dev/2022/01/06/point-in-time-scheduler/)
