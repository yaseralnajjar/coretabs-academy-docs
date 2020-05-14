# Manage Environment Variables

## Managing Environment Variables

We manage env vars in ElasticBeanstalk

#### 1. Go to AWS with your account

Provided you have your login link, such as \(username is your first name\):

[https://SOME-NUMBER.signin.aws.amazon.com/console](https://619000622287.signin.aws.amazon.com/console)

#### 2. Go to AWS ElasticBeanstalk

#### 3. Choose Environment \(staging/production\)

#### 4. Edit Software Configuration and Make The Changes

![](../.gitbook/assets/image%20%282%29.png)

#### 5. Delete Previous Configuration

![](../.gitbook/assets/image%20%284%29.png)

#### 6. Save New Configuration

Please, **do NOT forget to save with original name of the config** \(if saved under different name, it will break future build\).

![](../.gitbook/assets/image%20%283%29.png)



## Extra Steps for Frontend Build Arguments

#### 1. gitlab-ci.yml

Add the build arg when you build the docker image

![](../.gitbook/assets/image%20%285%29.png)

#### 2. production.spa.dockerfile

![](../.gitbook/assets/image%20%286%29.png)







