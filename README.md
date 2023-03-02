# django-mysql
Connecting Databases – Django MySQL settings
Django MySQLClient
MySQL API driver used to connect the MySQL database with your Django/Python Project. MySQLClient is basically an adapter used for interacting with Django ORM (Object Relational Management). Basically it is going to install Django code which is needed to connect with the database. We can install django install mysqlclient using pip.

<!-- pip install mysqlclient  -->

Change Database Settings in Django Application
Create Database in MySQL
First, we need to create a database in MySQL for the Django Project. Open your MySQL Command Line Client and use CREATE syntax to create a database in MySQL.

<!--  mysql> CREATE DATABASE sample;  -->

We believe that you have created your project without its migrations. So open your database setting code in settings.py file. You will similar code like bellow –

# settings.py
# Database
# https://docs.djangoproject.com/en/2.2/ref/settings/#databases

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': os.path.join(BASE_DIR, 'db.sqlite3'),
    }
} 

After going to database settings in your settings.py file. Replace the database configuration code with the bellow code.

# settings.py
# Database

DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'DB_name',
        'HOST': '127.0.0.1',
        'PORT': '3306',
        'USER': 'DB_user',
        'PASSWORD': 'DB_password',
    }
}

Note –
DB_name – is your database name created above
DB_user – is your MySQL Username
DB_password – is your MySQL password

Tip – In your database configuration, anyone can see your database username and password. So to protect sensitive

Once you replace the database configuration code, you need to make migrations.

python manage.py makemigrations 
python manage.py migrate
<!-- Done!. Now you are ready to use your Project. You can see your database fields in MySQL Database. -->
