# Deployment on Elasticbeanstalk

## Sanity check

First you need to check if everything is configure or not by the command:

```text
eb.exe list
```

If the list shows `staging` and `production` environments, then you're good to go!

## Initialization

You might need to login first using `eb.exe login`.

If the list is NOT showing any enviornment, then you have to run first:

```text
eb.exe init
```

The region is us-east-2 \(Ohio\).

##  Creating the env

Super easy, just write

```text
eb.exe create staging --cfg staging-config -c academy-staging -i t2.micro
```

This will

1. Create a `staging` env from the config `staging-config`.
2. With the name `academy-staging`.
3. Using a t2.micro instance.

##  Updating the academy

Pushing into `develop` or `master` is simply gonna solve your problem, but in case you wanna update manually, you gotta build the image and push it into dockerhub first by:

```text
docker build . -t yaseralnajjar/academy_api_base -f production.api.base.dockerfile --no-cache
docker push yaseralnajjar/academy_api_base

docker build . -t yaseralnajjar/academy_api -f production.api.dockerfile --no-cache
docker push yaseralnajjar/academy_api

eb.exe deploy staging
```

##  Terminating

You can delete the environment by:

```text
eb.exe terminate staging
```

