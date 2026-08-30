# Notes Project

A REST API for managing notes, built with **Django** and **Django REST Framework**.

## Tech Stack

- Python 3.14
- Django 6.0
- Django REST Framework 3.17
- PostgreSQL
- django-cors-headers
- django-filter
- python-decouple (environment variables)

## Project Structure

```
backend/
├── apps/
│   └── notes/            # Note app (models, serializers, views)
├── notes_project/        # Django project config
├── manage.py
├── requirements.txt
├── .env.example          # Template for environment variables
└── .gitignore
```

## Getting Started

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd <repo>/backend
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Copy `.env.example` to `.env` and fill in your values:

```bash
cp .env.example .env
```

Required variables:

| Variable          | Description                    |
| ----------------- | ------------------------------ |
| `SECRET_KEY`      | Django secret key              |
| `DEBUG`           | Debug mode (`True`/`False`)    |
| `ALLOWED_HOSTS`   | Comma-separated allowed hosts  |
| `POSTGRES_DB`     | Database name                  |
| `POSTGRES_USER`   | Database user                  |
| `POSTGRES_PASSWORD` | Database password            |
| `POSTGRES_HOST`   | Database host (default `localhost`) |
| `POSTGRES_PORT`   | Database port (default `5432`) |

### 5. Run database migrations

```bash
python manage.py migrate
```

### 6. Start the development server

```bash
python manage.py runserver
```

The API will be available at `http://127.0.0.1:8000/`.

## API Endpoints

All endpoints are prefixed with `/api/v1/`.

| Method | Endpoint      | Description              |
| ------ | ------------- | ------------------------ |
| GET    | `/notes/`     | List all notes           |
| POST   | `/notes/`     | Create a new note        |
| GET    | `/notes/<id>/` | Retrieve a single note  |
| PUT    | `/notes/<id>/` | Update a note           |
| DELETE | `/notes/<id>/` | Delete a note          |

### Example

Create a note:

```bash
curl -X POST http://127.0.0.1:8000/api/v1/notes/ \
  -H "Content-Type: application/json" \
  -d '{"title": "My first note", "content": "Hello world!"}'
```

## License

This project is for educational purposes.
