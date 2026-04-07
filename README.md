# E-Commerce Application

A full-stack web application built with **React** (frontend) and **FastAPI** (backend) for managing products.

## Tech Stack

- **Frontend**: React 18.2.0, Axios
- **Backend**: FastAPI, SQLAlchemy, Uvicorn
- **Database**: SQLite
- **Python Version**: 3.12+

## Project Structure

```
frontend/
├── src/                 # React components and styles
├── public/              # Static assets
├── build/               # Production build (generated)
├── myenv/               # Backend Python code
│   ├── main.py         # FastAPI application
│   └── models.py       # Database models
└── package.json         # Node.js dependencies
```

## Prerequisites

- Python 3.12+
- Node.js 18+
- npm

## Installation

### Backend

1. Create a Python virtual environment:
```bash
cd frontend
python -m venv py312env
```

2. Activate the environment:
```bash
# Windows
py312env\Scripts\activate

# macOS/Linux
source py312env/bin/activate
```

3. Install dependencies:
```bash
pip install fastapi uvicorn sqlalchemy psycopg2-binary pydantic
```

### Frontend

1. Install Node.js dependencies:
```bash
npm install
```

2. Build the frontend:
```bash
npm run build
```

## Running the Application

### Start Backend Server

```bash
py312env\Scripts\python.exe -m uvicorn myenv.main:app --reload --host 127.0.0.1 --port 8000
```

The API will be available at: `http://127.0.0.1:8000`

### API Documentation

- **Swagger UI**: `http://127.0.0.1:8000/docs`
- **ReDoc**: `http://127.0.0.1:8000/redoc`

### Start Development Frontend

```bash
npm start
```

The frontend will run on: `http://localhost:3000`

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | Welcome message |
| GET | `/Products` | Get all products |
| GET | `/Product/{product_id}` | Get product by ID |
| POST | `/product` | Add new product |
| PUT | `/product/{product_id}` | Update product |
| DELETE | `/product/{product_id}` | Delete product |

## Database

The application uses **SQLite** for data persistence. The database file (`products.db`) is automatically created when the backend starts.

### Switch to PostgreSQL

To use PostgreSQL instead, update `DATABASE_URL` in `myenv/main.py`:

```python
DATABASE_URL = "postgresql://username:password@localhost:5432/database_name"
```

## Available Scripts

### Frontend

- `npm start` - Run development server
- `npm run build` - Create production build
- `npm test` - Run tests

## Deployment

The frontend is built to the `build/` folder and can be served by any static server or integrated with a backend.

## License

MIT

## Author

Chaitanya
