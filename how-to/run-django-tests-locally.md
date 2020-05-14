# Run Django Tests Locally

### Activate Your Virtual Environment

It's pretty simple to get up and running with Django tests, first make sure you activated your venv:

```text
call venv/Scripts/activate # Windows
script venv/bin/activate # Linux
```

### Run All Tests

Then, simply run the command:

```text
python manage.py test -v 1 --settings coretabs.settings.test
```

This will run tests verbosity with level 1 \(normal output / print statements\), and it will use the test settings to not run the migrations which take lots of time.

### Run One Test

If you want to test a specific function, specify it by adding **app\_module\_name.tests.class\_name.function\_name**, for example:

```text
python manage.py test profiles.tests.ProfileTestCase.test_get_user_xp -v 1 --settings coretabs.settings.test
```

### Celery Tests

1. Add your AWS SQS settings as explained here in [Mighty dev\_secrets.py, Connect SQS](https://kasseryasser.gitbook.io/coretabs-academy/how-to/mighty-dev_secrets.py#connect-sqs).
2. On another terminal, activate your venv `call venv/Scripts/activate`
3. Run a local celery worker `celery worker --loglevel=INFO --pool=solo -A coretabs`

#### Celery Testing Caveats

* If you wanna test the function without async behavior \(without running a celery worker\), just add to your test the decorator:

```text
@override_settings(CELERY_TASK_ALWAYS_EAGER=True)
```

* If you want to test the async behavior, remove the decorator and add such code to wait till celery function finishes:

```text
import time
time.sleep(10) # wait 10 seconds
```

* We wrap the functions with `@call_asynchronously_if_production` decorator to let us call the function normally, it calls the function using `func.delay()`
* For local testing purposes, you can simply both decorators `@call_asynchronously_if_production`and `@app.task`and run your test just fine.

### Mailgun Tests

Add your Mailgun settings as explained here in [Mighty dev\_secrets.py, Connect Mailgun](https://kasseryasser.gitbook.io/coretabs-academy/how-to/mighty-dev_secrets.py#connect-mailgun).



