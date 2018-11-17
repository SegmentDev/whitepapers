
# Job Monitor


With so many automated processes and tasks occurring on a daily basis, today’s enterprise requires durable job scheduling and, more importantly, job monitoring. Simple monitoring schemes include email alerts, logging, and dashboards. Generally speaking, there are two major alert schemes: alerting on everything and alerting on failures. Both of these schemes have their advantages and disadvantages. This paper will discuss those and propose a new framework for enterprise job monitoring and alerting.

If an alerting scheme based on success based alerts is used, the end recipients often suffer from alert fatigue. Its nearly impossible to actively monitor incoming email/alerts when a majority of messages are ignored. Sooner or later the information biased will lead to a broad disregarding of alerts.

However, if we adopt a "notify on failure" strategy we lack transparency that the job has run at all. Or if it has started but not completed. Because we never see an alert explicitly saying "FAILURE" we assume everything has worked as expected.

One approach to this would be to have a dashboard that would show the status of all jobs. For example, a simple color scheme might be:
* Grey: Not Run
* Yellow: Running
* Green: Success
* Red: Failure

This would allow a user to quickly gauge the processes that have either not run or currently in progress (past which a certain elapsed time might be cause for investigation). The JobMonitor that I am proposing would leverage this basic idea and provide a dashboard like interface described above. Most importantly, however, it would solve the issue of monitor for incompletes programmatically.

As part of running a job we want a negative alerting context, meaning, we want an alert to go out when something *isn't* there or *doesn't* happen. This will ensure that if a job doesn't run or doesn't complete within an allotted window we will be notified. There is still a point of failure in the process to check and send the alert, however as this is a much more simple process, we can mitigate failure by decentralizing this component and adding fault tolerance.

To illustrate this system, lets look at a quick heartbeat example. A traditional system might run a job to ping a remote server parse the results and send out an email if the ping response is not success. Vigilant would approach this by setting an expiring key (redis for all further examples):

```bash
SETX MY_HEARTBEAT_JOB 5 "ALIVE"
```

This key will expire every 5 seconds. So we can run a distributed process to check for the presence of this key and alert if its present. If the server goes offline the process will simply fail to renew the key and when the decentralized workers detect its lack of precense they will take the appropriate action.

The same could be used for any normal daily job:

```bash
SETX MY_DAILY_PROCESS 86400 "OK"
```

In the case of long running jobs or multi-step jobs we can also post updates aliong the way:

```bash
HSET LONG_RUNNING_JOB STARTED "true"
EXPIRE LONG_RUNNING_JOB 3600
```

Currently Redis does not support expiring an individual hash field as opposed to the top level key itself. In some instances this behaviour would be desireable, but it's conceivable this would not be adequate in some implementations as it would mean a loss of data regarding all the previous updates made to this hash key.

Decentralized workers

Similar to smart contracts on the blockchain, the workers for Vigilant are decentralized as we do not want to rely on a single point of failure for alerting. The workers can implement a specialized form of smart contracts which allow them to execute on a scheuled or continuous basis checking for key values, applying threshold or tolerance logic, and alerting if necessary to one or more mediums.

A simple form of this might be to run an AWS lambda function on a scheduled basis to perform these same tasks. Another possibility might be to make use of Redis' built in Keyspace notifications, which provide a callback

We could provide a CRON like expression for the workers to understand the chronological component. So whereas a typical CRON process uses an expression to determine when to run a process, we can use the same CRON expression to understand when a process *should have run*.
