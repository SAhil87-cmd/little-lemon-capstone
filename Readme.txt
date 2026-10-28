LITTLE LEMON RESTAURANT - BACK-END DEVELOPER CAPSTONE
Django REST Framework API for menu and table bookings (MySQL, Djoser token auth)

=== API PATHS TO TEST ===
/api/menu/
/api/menu/<id>/
/api/bookings/
/api/bookings/<id>/
/auth/users/
/auth/token/login/
/auth/token/logout/
/                       (static HTML home page)

=== SETUP ===
1. git clone <repo-url> && cd little-lemon-capstone
2. python -m venv venv && source venv/bin/activate   (Windows: venv\Scripts\activate)
3. pip install -r requirements.txt
4. Create MySQL database:   CREATE DATABASE littlelemon;
5. Copy .env.example to .env and set DB_USER / DB_PASSWORD
   (no MySQL handy? set USE_SQLITE=1 in .env to run locally with SQLite)
6. python manage.py migrate
7. python manage.py runserver
8. Tests: python manage.py test

=== TESTING IN INSOMNIA ===
1. POST /auth/users/   body (JSON): {"username":"john","password":"StrongPass#123"}
2. POST /auth/token/login/   same body -> returns {"auth_token":"<token>"}
3. For every other request add header:  Authorization: Token <token>
4. POST /api/menu/      {"title":"Greek Salad","price":"12.50","inventory":30}
   GET  /api/menu/ , GET/PUT/DELETE /api/menu/1/
5. POST /api/bookings/  {"name":"John","no_of_guests":4,"booking_date":"2026-11-05T19:00:00Z"}
   GET  /api/bookings/ , GET/PUT/DELETE /api/bookings/1/

Note: all API endpoints except registration/login require the token header.
