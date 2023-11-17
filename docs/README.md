# Documentation for Point In Time Scheduler

> Update: In November 2022 AWS has released the EventBridge Scheduler. It does what I expect from a serverless scheduler, and has a free tier of 14 million invocations per month. Therefore, I'm deprecating this project.

This is the documenation for the Point In Time Scheduler, a serverless primitive for ad hoc scheduling.

If you don't know about the Point In Time Scheduler yet, [please read the announcement blog post](https://bahr.dev/2022/01/06/point-in-time-scheduler/).

## Table of Contents

Below are the topics that this documentation covers. If there's no link yet, then we're still writing the section.

* High Level Overview
* Core Concepts
  * [Authorization](https://github.com/bahrmichael/point-in-time-scheduler/tree/main/docs/concepts/authorization)
  * Scheduling
  * Receiving
* Getting Started
  * REST integration
  * SQS integration
* API Reference
