Placeholder WIP for now

ManageIt is a gameified 'to-do' app, built using Django and React.
Django provides a backend and API, and React provides the frontend and UI/UX

Setup:
The following instructions are for Debian-basd Linux environments -- you may have to adjust commands for other OSes.
After forking code, run the following to set up your development environment for both Django and React:

Django Steps:
1) Create a virtual environment (venv is my preference) at the top level manageit/ directory
python -m venv [env-name] && source [env-name]/bin/activate

2) Install dependencies with pip
pip install -r requirements.txt

3) Create a .env file with a dummy secret key
echo "SECRET_KEY=dummykey" > .env

4) Create the database
python manage.py migrate

5) Generate a unique secret key using django's shell and replace dummy key with output
echo "SECRET_KEY="$(python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())') > .env

6) Create Django Admin Superuser
python manage.py createsuperuser

7) Run Django portion of the app
cd backend && python manage.py runserver

React (and Node.js) Steps (you will need a new tab/terminal):

1) Ensure nodeenv is installed, manually add it if not
nodeenv -v
pip install nodeenv
nodeenv -p

2) Run React App
cd frontend && npm start