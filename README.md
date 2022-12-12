# Description of the project

API for the yatube project.

Done:

Viewsets used.

Authentication uses JWT tokens.

Unauthenticated users have read-only access to the API. The exception is the /follow/ endpoint.

Authenticated users are allowed to change and delete their content; otherwise, access is read-only.

# Installation

## 1) Clone Git Clone repository
## 2) Go to a new project folder and create and activate a virtual environment for the project

python -m venv venv

source venv/scripts/activate

## 3) Install dependencies
python pip install -r requirements.txt

## 4) Make migrations
python manage.py makemigrations
python manage.py migrate

## 5) Start the server
python manage.py runserver

# Examples

To access the API, you need to get a token:
You need to make a POST request to http://127.0.0.1:8000/api/v1/jwt/create/ passing the username and password fields.
The API will return a JWT token

Further, by passing the token, it will be possible to access methods, for example:

/api/v1/posts/ (GET, POST, PUT, PATCH, DELETE)

When sending a request, pass the token in the header Authorization: Bearer <token>

If you make a request to http://127.0.0.1:8000/redoc , you can get the project specification