# File Converter Project

This is just a basic scratchpad for the file converter service we're building. I've set up the core stuff with Django and Celery so we don't have to start from zero.

## How to get it running

First, make sure you have Redis running on your machine. Then, follow these steps:

1. **Set up the virtual env:**
   ```
   python3 -m venv venv 
   .\venv\Scripts\activate # On Windows
   source venv/bin/activate # On Linux/Mac
   pip install -r requirements.txt
   ```

2. **Database stuff:**
   Just run the migrations to get the sqlite db ready, we might be using postgresql later:
   ```
   python manage.py migrate
   ```

3. **Running the sparks:**
   You'll need two terminals open.
   - One for the web server: `python manage.py runserver`
   - One for Celery (the background worker): `celery -A file_converter_project worker --loglevel=info`

## What's inside

- I added a `.env` file for the keys and stuff. We'll most likely be updating it later.
- The `converter` folder is where we'll put the actual logic for the file exports.
- I left the models and views pretty empty for now so we can decide how we want to structure the upload part together.


## What the table is going have 
- 	Email
-	Original file 
-	Converted file
-	Status = {pending, processing, completed, failed}
-	Created_at 
-	Error message

Well done sir! 🫡
