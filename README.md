# Description

It is only repo to simple simulate backend api ensure jwt authenticate through Django.

* This tutorial is based on [djangorestframework_simplejwt.](https://django-rest-framework-simplejwt.readthedocs.io/en/latest/getting_started.html#installation)

# How to run 

* If first run type: `. firstrun.sh`
* `python manage.py runserver  0:8000`


# Example using

```python
curl \
  -X POST \
  -H "Content-Type: application/json" \
  -d '{"username": "admin", "password": "admin"}' \
  http://localhost:8000/api/token/
```

You should receive response like this:
```python
{
  "access":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX3BrIjoxLCJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiY29sZF9zdHVmZiI6IuKYgyIsImV4cCI6MTIzNDU2LCJqdGkiOiJmZDJmOWQ1ZTFhN2M0MmU4OTQ5MzVlMzYyYmNhOGJjYSJ9.NHlztMGER7UADHZJlxNG0WSi22a2KaYSfd1S-AuT7lU",
  "refresh":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyX3BrIjoxLCJ0b2tlbl90eXBlIjoicmVmcmVzaCIsImNvbGRfc3R1ZmYiOiLimIMiLCJleHAiOjIzNDU2NywianRpIjoiZGUxMmY0ZTY3MDY4NDI3ODg5ZjE1YWMyNzcwZGEwNTEifQ.aEoAYkSJjoWH1boshQAaTkf8G3yn0kapko6HFRt7Rh4"
}
```

# What was done

* `python3 -m venv env`
* `. env/bin/activate`
* `pip install djangorestframework_simplejwt`
* `django-admin startproject authApp .`
* `python manage.py makemigrations`
* `python manage.py migrate`
* `python manage.py createsuperuser` - username and password etc. `admin`.
* Added `"*"` to `ALLOWED_HOSTS` in `settings.py` file.
* Modify  `urls.py` by [djangorestframework_simplejwt.](https://django-rest-framework-simplejwt.readthedocs.io/en/latest/getting_started.html#installation)
*  Add CORS - allows in-browser requests to your Django application from other origins. [Link here.](https://github.com/adamchainz/django-cors-headers)


