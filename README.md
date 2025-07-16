# 🚀 **DevOps Project: Train-food-delivery Application Deployment**

**This is my own Devops Project. Developer only push the project code to github and all other files like dockerfile ,jenkinsfile and requirements.txt are created by me.**


**This is a Python Django project. so first we wnat to install Python**

**Step 1: Install Python**


```bash
sudo apt update
sudo apt install python3 python3-pip python3-venv -y
```

**step 2: Clone the repository**

```bash
git cone https://github.com/didin2003/Train-food-delivery.git
```

```bash
cd project-name
```
**step 3: Create and Activate virtual environment**

```bash
python3 -m venv venv
source venv/bin/activate
```

**step 4: Identify the dependency**

In this Project  django, pillow, djangorestframework, requests, psycopg2-binary are the dependency.

```bash
pip install django
python -m pip install Pillow
pip install django djangorestframework Pillow requests psycopg2-binary
```


```bash
python3 manage.py collectstatic # is used in Django to gather all your static files (CSS, JS, images, etc.) from your apps into a single directory so they can be served efficiently in production (usually by Nginx or a CDN).
```

**step 5: Install Gunicorn and nginx**

```bash
pip install gunicorn
gunicorn --bind 0.0.0.0:8000 Train_food_delivery.wsgi:application


sudo apt install nginx
```



**step 6: Edit some files**


```bash
nano train_food_delivery/settings.py
```

At the middle of the file. You can edit the `ALLOWED_HOSTS`


**`ALLOWED_HOSTS = ['127.0.0.1', 'localhost', '::1', '172.31.20.5', '51.21.235.2']`**


On the Bottom of the file


```bash
STATIC_URL = '/static/'
STATIC_ROOT = BASE_DIR / 'staticfiles'

STATICFILES_DIRS = [
    BASE_DIR / "static",
]
```


-----------------------------------------------------------------------------------------



```bash
nano train_food_delivery/urls.py
```


```bash
urlpatterns = [
    #path
] + static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)`
```
**step 7: Runs the Commands**

```bash
python3 manage.py makemigrations
python3 manage.py migrate
python3 manage.py createsuperuser
```


**step 8:Test it locally**


```bash
python3 manage.py runserver 0.0.0.0:8000
```

It will generate an ip copy ip and paste it on the terminal.

`<16.16.201.21:8000>`

**IF any error occurs edit these files** 


### **Deploy the Application on Docker** 


Deploying on docker is shown on [Train-food-delivery](https://github.com/didin8080/Train-food-delivery.git) 

All the documents are there in the Github repository.



