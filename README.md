# ShopNest — Flask E-Commerce Starter

A complete Flask e-commerce starter with user authentication, cart, and address management.

## Features
- User registration & login (with hashed passwords)
- Persistent cart per user (stored in SQLite)
- Save/delete delivery addresses
- Account dashboard
- Session persistence ("Remember me")
- Flash notifications
- Protected routes with @login_required

## Setup & Run

### 1. Create a virtual environment
```bash
python -m venv venv
source venv/bin/activate        # Mac/Linux
venv\Scripts\activate           # Windows
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the app
```bash
python app.py
```

### 4. Open in browser
Visit: http://127.0.0.1:5000

The SQLite database (`ecommerce.db`) is created automatically on first run.

## Project Structure
```
ecommerce/
├── app.py                  # Main app, routes, models
├── requirements.txt
├── ecommerce.db            # Auto-created SQLite DB
└── templates/
    ├── base.html           # Shared layout + nav
    ├── login.html
    ├── register.html
    ├── shop.html
    ├── cart.html
    └── dashboard.html
```

## Switching to PostgreSQL (Production)
Replace the SQLite URI in app.py:
```python
app.config['SQLALCHEMY_DATABASE_URI'] = 'postgresql://user:password@localhost/shopnest'
```
And install: `pip install psycopg2-binary`

## Secret Key
Change `SECRET_KEY` in app.py to a long random string before deploying:
```python
app.config['SECRET_KEY'] = 'your-very-long-random-secret-key-here'
```
