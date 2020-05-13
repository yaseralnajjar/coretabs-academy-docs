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

