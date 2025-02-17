# Deploying web application to AWS: Django, Django Channels

Deploying your project to AWS can be difficult and frustrating, if you are new to deploying a project. Neither is AWS user-interface easy to work with nor is their documentation easy to understand.

I recently had to deploy django application which also makes use of websockets and it took me around 8 days to get it properly up and running. Most of the errors occurred because I didn't understand their system well.

In this blog I wish not only help you deploy your django project but also to help you understand AWS better. I will also talk some of the commonly errors that I faced during the deployment.

While I'll be using django, most of the steps followed will remain same accross different frameworks and programming languages.

>Note: If think some steps are missing or is incorrect please create a new issue on this github repository or create a new pull request.

### Table of contents:

1. [Introduction to AWS interface](https://github.com/PaulleDemon/AWS-deployment/blob/master/AWS_Interface.md)

    1. Introduction
    2. Commonly used services
    3. Some abbreviation you should know
    4. Navigating in AWS Console
        <br>
        1. Search
        2. Elastic beanstalk
        3. EC2
        4. RDS 
        5. S3

2. [Deploying our django application](https://github.com/PaulleDemon/AWS-deployment/blob/master/deploying_django.md)
    
    1. Deployment flow
    2. Multiple ways to deploy an application
    3. Setup
    4. Creating application using the aws console.
    5. Using EB CLI to deploy application
        <br>
        1. Creating an application
        2. Creating an environment
    6. Debugging errors


3. [Using RDS to create database](https://github.com/PaulleDemon/AWS-deployment/blob/master/connecting_RDS.md)

    1. Introduction
    2. setting up RDS
    3. Connecting to pgAdmin
    4. Setting up RDS in our project
    5. Testing connection on EC2 instance (DEBUGGING)
    6. Migrations


4. [Using Environment variables to hide our sensitive info's](https://github.com/PaulleDemon/AWS-deployment/blob/master/UsingEnvironment.md)

    1. Introduction.
    2. Hiding your sensitive information in development
    3. Setting environment variables in production:


5. [Using S3 storage to store static and media files.](https://github.com/PaulleDemon/AWS-deployment/blob/master/s3buckets.md)
    1. Introduction.
    2. setting up project for S3 and creating bucket.
    3. Creating IAM Role


6. [Redirecting Http to Https](https://github.com/PaulleDemon/AWS-deployment/blob/master/redirectHttps.md)

7. [Deploying django channels application](https://github.com/PaulleDemon/AWS-deployment/blob/master/django-channels.md)

    1. setup
    2. Connecting Redis:


8. [some debugging tips](https://github.com/PaulleDemon/AWS-deployment/blob/master/debugging-tips.md)
    1. Introuction
    2. check list
    3. debugging tips
    4. Commonly used commands.
        1. Eb cli commands
        2. Linux commands

### Extra:

1. [Security Groups](https://github.com/PaulleDemon/AWS-deployment/blob/master/SecurityGroups.md)
2. [IAM](https://github.com/PaulleDemon/AWS-deployment/blob/master/IAM.md) 

References:
1. https://docs.aws.amazon.com/
2. StackOverflow answers
3. https://blog.zishanahmad.dev/how-to-deploy-django-channels-2x-on-aws-elastic-beanstalk-amazon-linux-2#comments-list
4. https://medium.com/@elspanishgeek/how-to-deploy-django-channels-2-x-on-aws-elastic-beanstalk-8621771d4ff0
