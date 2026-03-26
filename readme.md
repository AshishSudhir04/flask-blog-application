# Flask Blog Application

A full-featured blog web application built with Flask, featuring user authentication, post creation, and a responsive Bootstrap interface.

## Features

- **User Authentication**: Registration, login, logout with password hashing
- **Blog Posts**: Create, view, and manage blog posts
- **Responsive Design**: Bootstrap-based UI with modern styling
- **Database Integration**: SQLAlchemy with SQLite database
- **Session Management**: Flask-Login for user session handling
- **Form Validation**: WTForms for secure form handling and validation

## Technology Stack

- **Backend**: Flask (Python web framework)
- **Database**: SQLAlchemy ORM with SQLite
- **Authentication**: Flask-Login, Flask-Bcrypt
- **Forms**: Flask-WTF, WTForms
- **Frontend**: Bootstrap 4, HTML5, Jinja2 templates
- **Security**: CSRF protection, password hashing

## Project Structure

```
flask-blog-application/
├── app/
│   ├── __init__.py          # Flask app factory and configuration
│   ├── models.py            # SQLAlchemy database models (User, Post)
│   ├── forms.py             # WTForms classes (Registration, Login, Post)
│   ├── routes.py            # Flask route handlers
│   ├── templates/           # Jinja2 HTML templates
│   │   ├── layout.html      # Base template with navigation
│   │   ├── home.html        # Home page with blog posts
│   │   ├── register.html    # User registration form
│   │   ├── login.html       # User login form
│   │   ├── about.html       # About page
│   │   ├── account.html     # User account management
│   │   └── new_post.html    # Create new blog post
│   └── static/              # CSS, JS, and image files
├── instance/                # Instance-specific files
├── .venv/                   # Virtual environment
├── .gitignore               # Git ignore file
└── run.py                   # Application entry point
```

## Database Models

### User Model
- **Fields**: id, username, email, password (hashed), image_file
- **Relationships**: One-to-many with Post model
- **Features**: Unique username and email constraints

### Post Model  
- **Fields**: id, title, content, date_posted, user_id
- **Relationships**: Many-to-one with User model
- **Features**: Automatic timestamp generation

## Installation and Setup

### Prerequisites
- Python 3.7+
- pip (Python package manager)

### Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone https://github.com/AshishSudhir04/flask-blog-application.git
   cd flask-blog-application
   ```

2. **Create and activate virtual environment**:
   ```bash
   # Windows
   python -m venv .venv
   .venv\Scripts\activate
   
   # macOS/Linux
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. **Install dependencies**:
   ```bash
   pip install flask flask-sqlalchemy flask-wtf flask-bcrypt flask-login
   ```

4. **Run the application**:
   ```bash
   python run.py
   ```

5. **Access the application**:
   Open your browser and navigate to `http://127.0.0.1:5000`

## Application Routes

- **Home**: `/` or `/home` - Displays all blog posts
- **About**: `/about` - About page
- **Register**: `/register` - User registration (GET/POST)
- **Login**: `/login` - User login (GET/POST)
- **Logout**: `/logout` - User logout
- **Account**: `/account` - User account management
- **New Post**: `/post/new` - Create new blog post (protected)

## Security Features

- **Password Hashing**: Uses Flask-Bcrypt for secure password storage
- **CSRF Protection**: Automatic CSRF token generation for forms
- **Session Management**: Secure user session handling with Flask-Login
- **Input Validation**: WTForms validation for all user inputs
- **SQL Injection Prevention**: SQLAlchemy ORM protects against SQL injection

## Configuration

The application uses the following configuration:
- **Secret Key**: Used for session security and CSRF protection
- **Database**: SQLite database (`site.db`) stored in instance folder
- **Login View**: Redirects to login page for protected routes

## Usage

1. **Register a new account**: Visit `/register` to create a user account
2. **Login**: Use your credentials at `/login`
3. **Create posts**: After logging in, create blog posts via the navigation
4. **Manage account**: Update your profile and settings in `/account`

## Development

The application follows Flask best practices:
- **Application Factory Pattern**: Flask app created in `__init__.py`
- **Modular Structure**: Separated models, forms, and routes
- **Template Inheritance**: Base layout template for consistent UI
- **Environment Configuration**: Uses virtual environment for dependencies

## Future Enhancements

- Post editing and deletion functionality
- User profile pictures upload
- Comment system for blog posts
- Post categories and tags
- Search functionality
- Pagination for blog posts
- Email notifications
- Admin dashboard

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is for educational purposes. Feel free to use and modify as needed.

## Author

**Ashish Sudhir** - [GitHub Profile](https://github.com/AshishSudhir04)

---

**Note**: Make sure to keep your secret key secure in production environments and consider using environment variables for configuration management.
