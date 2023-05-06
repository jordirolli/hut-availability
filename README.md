<!--
title: 'Consell de Mallorca Hut availability'
description: 'This is an example of creating a function that runs as a cron job using the serverless ''schedule'' event.'
layout: Doc
framework: v3
platform: AWS
language: nodeJS
priority: 1
authorLink: 'https://github.com/jordirolli'
authorName: 'Jordi Roldán'
authorAvatar: 'https://avatars3.githubusercontent.com/u/5679763?v=4&s=140'
-->

# Hut availability

[Huts](https://caminsdepedra.conselldemallorca.cat/refugis) owned by 'Consell de Mallorca' can only be booked two months in advanced.
When the availability is extended is booked out in a couple of days. This project checks if there are new available dates on a daily basis and
notifies a given e-mail account when new dates are released.

## Usage

You need to set 

### Deployment

First you should [set up the credentials](https://www.serverless.com/framework/docs/providers/aws/guide/credentials#create-an-iam-user-and-access-key) in order to access to your AWS Account.

Then perform deployment with:

```
serverless deploy
```

After running deploy, you should see output similar to:

```bash
Deploying hut-availability to stage dev (us-east-1)

✔ Service deployed to stack hut-availability-dev (194s)

functions:
  hello: hut-availability-dev-hello (717 B)
```

There is no additional step required. Your defined schedules becomes active right away after deployment.

### Local invocation

In order to test out your functions locally, you can invoke them with the following command:

```
serverless invoke local --function hello
```

After invocation, you should see output similar to:

```bash
{
    "message": "Go Serverless v3! Your function executed successfully!",
    "input": ""
}
```