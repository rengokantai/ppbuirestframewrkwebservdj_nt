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

```
REST_FRAMEWORK = {
  'rest_framework.authentication.BasicAuthentication',
  'rest_framework.authentication.SessionAuthentication'
}
```
