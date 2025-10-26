# Django Chat Application

A real-time chat application built with Django that allows users to create and join chat rooms for instant messaging.

## Features

- 🚀 **Multiple Chat Rooms** - Create and join different chat rooms
- 👤 **User-friendly Interface** - Simple and intuitive chat interface
- 💬 **Real-time Messaging** - Send and receive messages instantly
- 📊 **Message History** - All messages are stored in the database
- 🎨 **Clean UI** - Modern and responsive chat interface
- ⚡ **AJAX-based** - Smooth message updates without page refresh

## Technology Stack

- **Backend**: Django 3.1.4
- **Database**: SQLite
- **Frontend**: HTML, CSS, JavaScript (jQuery)
- **Deployment**: WSGI (ASGI support available)

## Project Structure

```
django-chat-app/
├── chat/                    # Main chat application
│   ├── models.py           # Room and Message models
│   ├── views.py            # View functions for routing
│   ├── urls.py             # URL patterns for chat app
│   ├── admin.py            # Django admin configuration
│   └── migrations/         # Database migrations
├── djangochat/             # Django project settings
│   ├── settings.py         # Project settings
│   ├── urls.py             # Main URL configuration
│   ├── wsgi.py             # WSGI config
│   └── asgi.py             # ASGI config
├── templates/              # HTML templates
│   ├── home.html           # Home page (room selection)
│   └── room.html           # Chat room interface
├── db.sqlite3              # SQLite database
└── manage.py               # Django management script
```

## Installation

### Prerequisites

- Python 3.7 or higher
- pip (Python package manager)

### Setup Instructions

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd django-chat-app
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On Linux/Mac
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install django
   ```

4. **Run database migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. **Create a superuser (optional, for admin access)**
   ```bash
   python manage.py createsuperuser
   ```

6. **Start the development server**
   ```bash
   python manage.py runserver
   ```

7. **Open your browser**
   Navigate to `http://127.0.0.1:8000/`

## Usage

### Getting Started

1. **Access the application**
   - Open the application in your browser
   - You'll see a form asking for Room Name and Username

2. **Join a Chat Room**
   - Enter a room name (e.g., "general", "random")
   - Enter your username
   - Click "Enter Room"

3. **Start Chatting**
   - Type your message in the input field
   - Click "Send" or press Enter
   - Messages are updated automatically every second

4. **Multiple Users**
   - Multiple users can join the same room
   - All messages are visible to everyone in the room
   - Messages are stored in the database

### Features

- **Room Creation**: Rooms are created automatically when first accessed
- **Message Persistence**: All messages are saved in the database
- **Real-time Updates**: Messages refresh every second using AJAX
- **User Identification**: Messages are tagged with usernames and timestamps

## Database Models

### Room Model
- `name`: CharField - The name of the chat room (max 1000 characters)

### Message Model
- `value`: CharField - The message content (max 1,000,000 characters)
- `user`: CharField - The username of the sender (max 1,000,000 characters)
- `room`: CharField - The room ID (max 1,000,000 characters)
- `date`: DateTimeField - Timestamp of when the message was sent

## API Endpoints

- `GET /` - Home page with room entry form
- `GET /<room>/` - Access a specific chat room
- `POST /checkview` - Check if room exists, create if doesn't exist
- `POST /send` - Send a message to a room
- `GET /getMessages/<room>/` - Fetch all messages for a room (JSON)

## Configuration

The application uses default Django settings:
- Debug mode is enabled for development
- SQLite database for easy setup
- Default timezone is UTC
- Secret key is set in settings (change for production)

## Production Deployment

⚠️ **Important**: Before deploying to production, make sure to:

1. **Change the SECRET_KEY** in `djangochat/settings.py`
2. **Set DEBUG = False** in production
3. **Configure ALLOWED_HOSTS** with your domain
4. **Use a production database** (PostgreSQL, MySQL, etc.)
5. **Collect static files**: `python manage.py collectstatic`
6. **Use a proper web server** (Nginx + Gunicorn or uWSGI)
7. **Enable HTTPS** for secure connections

## Contributing

Contributions are welcome! Feel free to:
- Report bugs
- Suggest new features
- Submit pull requests

## License

This project is open source and available for educational purposes.

## Author

Created as a Django learning project.

## Acknowledgments

- Django framework for the excellent web framework
- jQuery for simplifying JavaScript operations

---

**Note**: This is a simple chat application suitable for learning purposes. For production use, consider implementing:
- User authentication
- WebSocket support for true real-time messaging
- Message encryption
- Rate limiting
- Spam protection
- File upload support
- Private messaging
- Emoji support
