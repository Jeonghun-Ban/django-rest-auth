django-rest-auth
===

로그인 및 패스워드 찾기 api센터

discription
---

### /password/reset

parameter: email
return: success/fail message

### /password/reset/confirm

parameter: token, uid, new_password1, new_password2
return: success/fail message

### /password/change

parameter: new_password1, new_password2
return: success/fail message

### /login/

parameter: username, password
return: REST Framework Token Object's key.

### /logout/

Calls Django logout method and delete the Token object
assigned to the current User object.

Accepts/Returns nothing.

### /user/

Default accepted fields: username, first_name, last_name
Default display fields: pk, username, email, first_name, last_name
Read-only fields: pk, email

Returns UserModel fields.