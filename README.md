# Enhanced Timetable System

A comprehensive Django-based timetable management system with AI-powered features for educational institutions.

## Features

### Authentication & User Management
- **Dual User System**: Students and Admins with separate registration flows
- **Secure Authentication**: Login using Roll Number (students) or Admin ID (admins)
- **OTP-based Password Reset**: Phone number verification for secure password recovery
- **User Profiles**: Extended profiles with academic and administrative information

### Student Features
- **AI-Powered Dashboard**: Personalized timetable summaries and insights
- **Smart Recommendations**: AI-generated study suggestions based on schedule and performance
- **Interactive Chatbot**: Academic queries, schedule changes, and syllabus help
- **Timetable Viewing**: Subject schedules with allocated teachers and rooms
- **Natural Language Search**: "Show my Friday classes" - get filtered results instantly

### Admin Features
- **Course Management**: Add, edit, delete courses and subjects
- **Teacher Assignment**: Assign subjects to teachers with conflict detection
- **Timetable Generation**: Upload or AI-assisted timetable creation
- **Student Management**: Add/remove students and manage enrollments
- **Password Reset**: Reset any user's password if needed
- **Announcements**: Post targeted announcements to specific groups
- **AI Analytics**: Performance insights, attendance trends, and optimization suggestions

### AI-Powered Features
- **Timetable Generator**: Automatic conflict-free schedule generation
- **Performance Insights**: Predictive analytics for student support needs
- **Chat Assistant**: Natural language processing for queries
- **Smart Notifications**: Context-aware alerts and reminders
- **Optimization Suggestions**: Schedule and resource allocation improvements

## Technology Stack

- **Backend**: Django 4.2.7 + Python 3.13
- **Database**: SQLite (development) / MySQL (production)
- **AI Integration**: OpenAI API for intelligent features
- **Communication**: Twilio for SMS/OTP services
- **Task Queue**: Celery + Redis for background processing
- **Frontend**: Django Templates (expandable to React/Vue)

## Project Structure

```
enhanced_timetable_system/
├── accounts/                 # User authentication and profiles
│   ├── models.py            # User, StudentProfile, AdminProfile, OTP
│   ├── views.py             # Authentication views
│   └── admin.py             # Admin interface
├── timetable/               # Core timetable functionality
│   ├── models.py            # Course, Subject, Teacher, TimetableEntry, etc.
│   ├── views.py             # Timetable management views
│   └── admin.py             # Admin interface
├── ai_features/             # AI-powered features
│   ├── models.py            # AIChat, StudyRecommendation, PerformanceInsight
│   ├── views.py             # AI feature views
│   └── services.py          # AI service integrations
├── enhanced_timetable_system/
│   ├── settings.py          # Django configuration
│   ├── urls.py              # URL routing
│   └── wsgi.py              # WSGI application
├── static/                  # Static files (CSS, JS, images)
├── templates/               # HTML templates
├── requirements.txt         # Python dependencies
└── manage.py               # Django management script
```

## Database Models

### Core Models
- **User**: Extended Django user with student/admin differentiation
- **StudentProfile**: Academic information (roll number, course, year, section)
- **AdminProfile**: Administrative information (admin ID, department)
- **Course**: Academic programs (B.Tech, BCA, B.Sc, etc.)
- **Subject**: Course subjects with year/semester mapping
- **Teacher**: Faculty information and subject assignments
- **TimetableEntry**: Individual class schedules
- **Room**: Classroom and laboratory information

### AI Models
- **AIChat**: Conversation sessions with the AI assistant
- **StudyRecommendation**: Personalized study suggestions
- **PerformanceInsight**: Analytics and performance predictions
- **SmartNotification**: Context-aware notifications

## Setup Instructions

### 1. Clone and Navigate
```bash
cd enhanced_timetable_system
```

### 2. Set Up Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Environment Configuration
```bash
cp .env.example .env
# Edit .env with your configuration
```

### 5. Database Setup
```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Create Superuser
```bash
python manage.py createsuperuser
```

### 7. Run Development Server
```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000` to access the application.

## Configuration

### Environment Variables
- `SECRET_KEY`: Django secret key
- `DEBUG`: Debug mode (True/False)
- `DB_*`: Database configuration
- `OPENAI_API_KEY`: OpenAI API key for AI features
- `TWILIO_*`: Twilio configuration for SMS/OTP
- `EMAIL_*`: Email configuration

### Database Migration to MySQL
To switch from SQLite to MySQL:

1. Install MySQL client:
```bash
pip install mysqlclient
```

2. Update `settings.py`:
```python
# Uncomment MySQL configuration in settings.py
# Update .env with MySQL credentials
```

3. Run migrations:
```bash
python manage.py migrate
```

## API Endpoints

### Authentication
- `POST /auth/register/student/` - Student registration
- `POST /auth/register/admin/` - Admin registration  
- `POST /auth/login/` - User login
- `POST /auth/forgot-password/` - Password reset request
- `POST /auth/verify-otp/` - OTP verification

### Student APIs
- `GET /student/dashboard/` - Student dashboard
- `GET /student/timetable/` - Personal timetable
- `POST /student/chat/` - AI chat interaction

### Admin APIs
- `GET /admin/dashboard/` - Admin dashboard
- `GET /admin/courses/` - Course management
- `POST /admin/timetable/generate/` - AI timetable generation

## Next Steps

1. **Frontend Enhancement**: Add React/Vue.js for better UX
2. **Mobile App**: React Native or Flutter mobile application
3. **Advanced AI**: More sophisticated recommendation algorithms
4. **Real-time Features**: WebSocket integration for live updates
5. **Analytics Dashboard**: Comprehensive reporting interface
6. **API Documentation**: OpenAPI/Swagger documentation
7. **Testing**: Comprehensive test coverage
8. **Docker**: Containerization for easy deployment

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch  
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions, please open an issue on GitHub or contact the development team.
# enhanced_timetable_system
