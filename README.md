# ppbuirestframewrkwebservdj_nt

### Declare Relationships with the Models
Original
```
DATABASES = {
  'default':{
    'ENGINE':django.db.backends.sqlite3',
    'NAME':os.path.join(BASE_DIR,'db.sqlite3'),
  }
}
```
TO
```
DATABASES = {
  'default':{
    'ENGINE':django.db.backends.postgresql',
    'NAME':'dbname',
    'USER':'rengokantai',
    'PASSWORD':'pass',
    'HOST':'127.0.0.1',
    'PORT':'5432'
  }
}
```
```
psql --username=test1 --dbname=games --command="\dt"
```

### Managing Serialization and Deserialization with Hyperlinks
Note:
- Uses hyperlinked relationship
- Represents relationship models with hyperlinks
- Generates a field named URL
- Create and update methods



### Creating Class-Based Views and Using Generic Classes
Note
- Use Generic and Serializer class
  - Return JSON representation for each HTTP request
- Specify query set to retrieve all objects
- Declare name attribute with string name


### 21 Taking Advantage of Pagination
```
REST_FRAMEWORK = {
  'DEFAULT_PAGINATION_CLASS':
  'rest_framework.pagination.LimitOffsetPagination',
  'PAGE_SIZE':5
}
```

### 22 Customizing pagination
pagination.py
```
from rest_framework.pagination import LimitOffsetPagination
class LimitOffsetPaginationWithMaxLimit(LimitOffsetPagination):
  max_limit=10     # when you specify limit=10000,still=10
```
settings.py
```
REST_FRAMEWORK = {
  'DEFAULT_PAGINATION_CLASS':
  'games.pagination.LimitOffsetPaginationWithMaxLimit',
  'PAGE_SIZE':5   //applid when no limit query applied
}
```
### 23 Understanding
```
REST_FRAMEWORK = {
  'DEFAULT_AUTHENTICATON_CLASSES':(
    'rest_framework.authentication.BasicAuthentication',
    'rest_framework.authentication.SessionAuthentication'
  )
}
```


