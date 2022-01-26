# Boutique Ado walkthrough

Project created via Code Institute e-commerce walkthrough lessons.

### Commands for project setup:
<ol>
    <li>pip3 install Django==3.2</li>
    <li>django-admin startproject {project_name} .</li>
    <li>touch .gitignore</li>
    <li>python3 manage.py runserver (to check all the above worked)</li>
    <li>python3 manage.py migrate</li>
    <li>python3 manage.py createsuperuser</li>
    <li>Add files, commit and push</li>
</ol>
<br>

### Commands/steps for installing Django AllAuth:
<ol>
    <li>pip3 install django-allauth==0.41.0</li>
    <li>Add authentication backends section from allauth documentation <a href="https://django-allauth.readthedocs.io/en/latest/installation.html">HERE</a></li>
    <li>Add the all auth apps and contrib.sites app to settings.py apps sections</li>
    <li>Underneath the athentication backends section add: "SITE_ID = 1"</li>
    <li>In the project urls file add: "path('accounts/', include('allauth.urls'))," to urls and update imports with 'include'</li>
    <li>python3 manage.py migrate</li>
    <li>python3 manage.py runserver, navigate to the admin panel</li>
    <li>In 'sites' update the domain name to boutiqueado.example.com</li>
    <li>Save, close and stope the server</li>
    <li>Add the necessary email/account verification settings for email_backend in settings.py:<br>
         EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'<br>
         ACCOUNT_AUTHENTICATION_METHOD = 'username_email'<br>
         ACCOUNT_EMAIL_REQUIRED = True<br>
         ACCOUNT_EMAIL_VERIFICATION = 'mandatory'<br>
         ACCOUNT_SIGNUP_EMAIL_ENTER_TWICE = True<br>
         ACCOUNT_USERNAME_MIN_LENGTH = 4<br>
         LOGIN_URL = '/accounts/login'<br>
         LOGIN_REDIRECT_URL = '/success'<br>
    </li>
    <li>python3 manage.py runserver</li>
    <li>navigate to /accounts/login</li>
    <li>Sign in using the earlier created superuser to check the redirection to verification page works<br>
        *The automatic email won't be sent as superuser created before allauth installed    
    </li>
    <li>Navigate to the admin panel and open the 'email addresses' model</li>
    <li>Click 'add email address'</li>
    <li>Select username by clicking on the magnifying glass</li>
    <li>Enter the email address of the user, and select verify and primary tick boxes</li>
    <li>Save, log out of the admin panel and go back to the login page.</li>
    <li>Log in using the superuser again, you should be directed to 404 with url 'success'</li>
    <li>Back in settings.py change the redirect url from '/success' to '/'</li>
    <li>pip3 freeze > requirements.txt</li>
    <li>mkdir templates</li>
    <li>mkdir templates/allauth</li>
    <li>Add, commit and push changes</li>
</ol>
<br>

### Next steps
<ol>
    <li>cp -r ../.pip-modules/lib/python3.7/site-packages/allauth/templates/* ./templates/allauth/</li>
    <li>IF THE ABOVE DOESNT WORK, TRY: "cp -r /home/gitpod/.pyenv/versions/3.8.12/lib/python3.8/site-packages/allauth/templates/* ./templates/allauth"</li>
    <li>Delete the openid and tests folders from the allauth templates dir if you don't need them</li>
    <li>Create a base.html file in the top templates folder</li>
</ol>


2.7, 3, 3.8, 3.9