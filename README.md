# Parrot Order Management System

A web application for managing customer orders built with React and Django.

## Project Structure 

```
parrot/
├── backend/           # Django REST API
│   ├── src/
│   │   ├── api/
│   │   └── manage.py
│   └── requirements.txt
└── docker-compose.yml  # Docker configuration
```

## Features

- User Authentication
- Order Management
  - Create new orders
  - Add multiple products to orders
  - View order history


## Tech Stack

### Backend
- Django
- Django REST Framework
- Simple JWT Authentication


## Getting Started

### Prerequisites
- Docker
- Docker Compose

### Running the Application

1. Clone the repository 

2. Start the application
```bash
docker-compose up --build
```

The application will be available at:
- Backend API: http://localhost:8000

## Development

### Frontend Development
```bash
cd frontend
npm install
npm start
```

### Backend Development
```bash
cd backend
python -m venv env
source env/bin/activate  # On Windows: .\env\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

### Creating a Superuser

To create an admin user for accessing the Django admin interface and using the application:

```bash
# If using Docker
docker-compose exec backend python src/manage.py createsuperuser

# If running locally
cd backend
python src/manage.py createsuperuser
```

Follow the prompts to set:
- Username
- Password

You can then use these credentials to:
1. Log into the Django admin interface at `/admin`
2. Log into the main application

## API Endpoints

- `POST /api/login/` - User authentication
- `POST /api/orders/` - Create new order
- `GET /api/orders/recent/` - Get recent orders
