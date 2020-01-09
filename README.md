django-rest-auth
===

Django-rest auth api center

API endpoints
---

- /login/ (POST)
  - username
  - email
  - password
  Returns Token key

- /logout/ (POST)
  - Calls Django logout method and delete the Token object
  - assigned to the current User object.
  > `ACCOUNT_LOGOUT_ON_GET = True` to allow logout using GET - this is the exact same configuration from allauth. NOT recommended, see: http://django-allauth.readthedocs.io/en/latest/views.html#logout

- /password/reset (POST)
  - email
  Returns success/fail message

- /password/reset/confirm (POST)
  - uid
  - token
  - new_password1
  - new_password2
  Returns success/fail message
  > uid and token are sent in email after calling /rest-auth/password/reset/

- /password/change (POST)
  - new_password1
  - new_password2
  - old_password
  > `OLD_PASSWORD_FIELD_ENABLED = True` to use old_password.
  > `LOGOUT_ON_PASSWORD_CHANGE = False` to keep the user logged in after password change

- /user/ (GET, PUT, PATCH)
  - username
  - first_name
  - last_name
  Returns pk, username, email, first_name, last_name