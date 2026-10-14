# step by step for the django setup

## Startuo or install of venv
```
py -m venv venv
```

# Activate Venv
## For CMD
```
.\venv\scripts\activate
```

## For Powershell
```
venv/scripts/activate
```

## install django
```
pip install django djangoforestframework djangoforestframework-simplejwt django-cors-header pillo
```

## Start the admin
```
django-admin startproject core .
```
# Add requirements using this
```
py freeze > requirements.txt
```

## Type this in the Middleware
```

```

## Put this in installed for rest-framework 
```py
'corsheaders',
'rest_framework',
'rest_framework_simplejwt',
```

## Import this the timedata
```py
SIMPLE_JWT = (
    'ACCESS_TOKEN_LIFETIME': timedelta(days=1),
)
```

## Go to the url.py
```py
from rest_framework_simplejwts.view import TokenObtainPaireview, TokenfreshView 
TokenVerifyView
```

## Create this pattern 
```py  

#bonus api still work even you dont put them but they are on standard
#if you understand or able to write the api one path you can just duplicate iot and just change the endpoint
#The name is extra aka the name aka optional

urlpatterns = [
    path('admin/', admin.site.urls),
    
    # Auth
    path('api/token/', TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('api/token/refresh/', TokenRefreshView.as_view(), name='token_refresh'),
    path('api/token/verify/', TokenVerifyView.as_view(), name='token_verify'),
]
```

## Everything stand in /

## Set time zone
```py
TIME_ZONE = 'Asia/Manila'
```

## Create app
```py
py manage.py startapp ( name of the folder )
```
```py
py ,\manage.py startapp ( name of the files) ts apps/(Name of the files)
```

## Modify the default user models
# write this DEPENDS ON YOU 
```py
from django.contrib.auth.models import AbstractUser
```
## Create User   
```py
class user(AbstractUser):
    avatar = models.ImageField(upload_to='user/avatar/',default='(Paths name)')
```
```py
GENDER_CHOICES = [{'M','Male',},{'F','Female',}]
```

### sAMPLES 
```py
class user(AbstractUser):
    avatar = models.ImageField(upload_to='user/avatar/',default='users/avatar/default.webp')
    gender = models.Charfield(max_length=50, choices=GENDER_CHOICES)
```
#### GEF Compose of images 

### Create a gender cases in the upper part
```py
GENDER_CHOICES = [{'M','Male',},{'F','Female',}]
```

```py
def_str_(self):
```

## Go to Setting
### Find the Internilzations
# Put it on the last one
## defined it 
```py
AUTH_USER_MODEL = 'apps.clients'
#apps.client.clients.user
```

## Head to apps to give specific

Class 

## go to setting and put it on apps



### Go to terminal for event
```py
py .\manage.py makemigrations
```
### Migrates the file
```py
py .\manage.py migrate
```

### you cant create superuser if theres no avatar required thats why you need default as it was required

## Run the server
```py
py .\manage.py runserver
```

### if the user doest exist go to the Admin.py
```py
from .model import user
```
## put the user or definition on them
```py
admin.site
```

### Go to the model.py go to the def __stry part and include the definition of compilion or condition
```py
{self.first_name if self.first_name else ""}
```

## Proceed to Serilizer
# main job of serilizer 
- The one who defined their fields 

#### Steps now
- Create folder for the Serializer
- start putting the locations

```py
from rest_framework import serializers
```
```py
from .model import User
```
#
```py
class UserSerializer(Serializer.ModelSerializer)
    class Meta:
        model = User
        fields = ['id','username','last_name','first_name']
```

### Go to Views.py
```py
from django.shortcut import render
```
#
```py
from rest_framework.view import APIVIEW
```
#
```py
from rest_framework.view import response
```
#
```py
from rest_framework import status
```
```py
from .model import user
```
```py
from .serializer import userSerializers 
```

```py
# Create your own views here 

class UserlistCreateAPIView(APIVIEW):
    def get(self, request)
        users - User.objects.all()
        serializer = UserSerializer(Users, many=True)

        return Response(data=seriazlizer.data, status=status.HTTP_200_OK)

    def post(self,request):
        pass
```       