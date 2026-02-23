 	====== Create App with full project 


1.	Create project ( django-admin startproject third)
2.	 Go to the  project  (Cd third)
3.	Create App (python manage.py startapp myapp)
Why App ( it is kind of features in your projects like User, Items, Courses, Products)
4.	Create templates name folder in myapp
And in templates ( index.html, home.html ……_
5.	Create static name folder in myapp
And in static (style.css , other css file and js files) 





---- In  (myapp/views.py )----
def Home(request):
    return render(request,"index.html")
---- in (third/urls.py)---
from django.contrib import admin
from django.urls import path
from myapp.views import Home

urlpatterns = [
    path('admin/', admin.site.urls),
    path('',Home)
]

---- in (third/setting.py )------------
Add in line 54 ( import os)
Add in line 59 ---( 'DIRS': [os.path.join(BASE_DIR, 'templates')], )
STATIC_URL = '/static/'

STATICFILES_DIRS = [
    os.path.join(BASE_DIR, 'static'),
]

And then run project 
Python manage.py run server 

