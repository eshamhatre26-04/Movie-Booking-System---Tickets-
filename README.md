💻 
Project Description: Movie Ticket Booking System

Developed a user-friendly GUI-based Movie Ticket Booking System using Python and Tkinter. The application is connected to a MySQL database to securely store and manage booking information such as movie titles, selected seats, ticket quantity, and total cost.

The system supports complete database operations (Create, View, Modify, and Delete records), allowing efficient management of booking data. An interactive seat selection interface enables users to choose seats dynamically, with selections being saved instantly to the database.

This Python-based application allows users to:

Select a movie from a drop-down list

Specify the number of tickets required

Pick seats through a visual seating arrangement

View booking details before confirming the reservation

Fetch saved bookings and search for specific reservation records

🎬 Movie Ticket Booking System



![Python](https://img.shields.io/badge/python-3.7+-blue.svg)
![Tkinter](https://img.shields.io/badge/GUI-Tkinter-green.svg)
![MySQL](https://img.shields.io/badge/Database-MySQL-orange.svg)

## 📋 Table of Contents
- [Features](#features)
- [Screenshots](#screenshots)
- [System Requirements](#system-requirements)
- [Installation](#installation)
- [Database Setup](#database-setup)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Technologies Used](#technologies-used)
- [Future Enhancements](#future-enhancements)

## ✨ Features

### User Features
- 🔐 **User Authentication**: Secure login and registration with password hashing
- 🎥 **Browse Movies**: View available movies with detailed information (genre, duration, rating, price)
- 📅 **Select Showtimes**: Choose from multiple available showtimes across different dates
- 💺 **Real-time Seat Selection**: Interactive 5x10 seat map with live availability updates
- 📋 **Booking Management**: View booking history and cancel bookings
- 🎨 **Modern UI**: Clean, professional interface with dark theme

### Admin Features
- ➕ **Movie Management**: Complete CRUD operations for movies
- ⏰ **Showtime Management**: Add and delete showtimes
- 👥 **User Management**: View and manage registered users
- 📊 **Booking Overview**: Monitor all bookings across the system

### Technical Features
- **Database**: MySQL with proper foreign keys and constraints
- **Security**: SHA-256 password hashing
- **Data Integrity**: Automatic seat availability updates
- **Validation**: Email, phone, and input validation
- **Error Handling**: Comprehensive exception handling
- **Scalable Design**: Modular architecture for easy expansion

## 🖥️ System Requirements

- **Python**: 3.7 or higher
- **MySQL**: 5.7 or higher
- **Operating System**: Windows, macOS, or Linux
- **Display**: 1200x700 minimum resolution

## 📦 Installation

### Step 1: Clone or Download the Project
```bash

git clone <repository-url>
cd movie_booking_system


```

### Step 2: Install Python Dependencies
```bash
pip install mysql-connector-python
```

### Step 3: Install MySQL
- Download MySQL from https://dev.mysql.com/downloads/
- Install and set up MySQL server
- Remember your root password

## 🗄️ Database Setup

### Method 1: Automatic Setup (Recommended)
1. Open `database.py`
2. Update the database credentials:
```python
self.host = "localhost"
self.user = "root"
self.password = "your_mysql_password"  # Change this
self.database = "movie_booking_db"
```

3. Run the main application:
```bash
python main.py
```
The database and tables will be created automatically with sample data.

### Method 2: Manual Setup
```sql
-- Create database
CREATE DATABASE movie_booking_db;
USE movie_booking_db;

-- Run the SQL schema from database.py
-- Tables: users, movies, showtimes, bookings
```

## 🚀 Usage

### Running the Application

#### For Regular Users:
```bash
python main.py
```

#### For Admin Panel:
```bash
python admin_panel.py
```

### User Workflow

1. **Register/Login**
   - First-time users: Click "Register here" and create an account
   - Existing users: Enter username and password to login

2. **Browse Movies**
   - View list of available movies
   - Click on a movie to see details (genre, duration, rating, description, price)

3. **Book Tickets**
   - Click "SELECT SHOWTIME" button
   - Choose your preferred date and time
   - Select seats from the interactive seat map
   - Click "CONFIRM BOOKING"

4. **Manage Bookings**
   - Go to "My Bookings" tab
   - View all your bookings
   - Cancel bookings if needed

### Admin Workflow

1. **Manage Movies**
   - Add new movies with all details
   - Update existing movie information
   - Delete movies (cascading deletes showtimes and bookings)
   - Toggle movie status (active/inactive)

2. **Manage Showtimes**
   - Create showtimes for movies
   - Set date, time, screen number, and capacity
   - Delete old or cancelled showtimes

3. **Monitor Users and Bookings**
   - View all registered users
   - Monitor all bookings in the system
   - Delete users if necessary

## 📁 Project Structure

```
movie_booking_system/
│
├── main.py                 # Application entry point
├── database.py             # Database configuration and setup
├── auth.py                 # Authentication (login/registration)
├── booking_app.py          # Main booking application
├── admin_panel.py          # Admin CRUD interface
├── requirements.txt        # Python dependencies
└── README.md              # This file
```

## 🛠️ Technologies Used

### Frontend
- **Tkinter**: Python's standard GUI library
- **ttk**: Themed widgets for modern look

### Backend
- **Python 3**: Core programming language
- **MySQL Connector**: Database connectivity

### Database
- **MySQL**: Relational database management
- **SQL**: Database queries and operations

### Security
- **hashlib**: SHA-256 password hashing
- **Regular expressions**: Input validation

## 📊 Database Schema

### Users Table
- user_id (PK)
- username (UNIQUE)
- password (hashed)
- email (UNIQUE)
- phone
- created_at

### Movies Table
- movie_id (PK)
- title
- genre
- duration
- rating
- description
- price
- image_path
- status

### Showtimes Table
- showtime_id (PK)
- movie_id (FK)
- show_date
- show_time
- screen_number
- total_seats
- available_seats

### Bookings Table
- booking_id (PK)
- user_id (FK)
- showtime_id (FK)
- seats
- total_amount
- booking_date
- status

## 🎨 Design Features

- **Color Scheme**: 
  - Background: #1a1a2e (Dark blue)
  - Accent: #16213e (Darker blue)
  - Primary Button: #e94560 (Red/Pink)
  - Success: #00d9ff (Cyan)

- **Typography**: Arial font family with varied weights
- **Layout**: Responsive frames with proper padding
- **User Experience**: Intuitive navigation and clear visual feedback

## 🔮 Future Enhancements

- [ ] Payment gateway integration
- [ ] Email notifications for bookings
- [ ] Movie poster images
- [ ] Advanced search and filters
- [ ] Discount codes and promotions
- [ ] PDF ticket generation
- [ ] Mobile app version
- [ ] Multi-language support
- [ ] Review and rating system
- [ ] Seat type selection (Regular, VIP, etc.)

## 🐛 Troubleshooting

### Common Issues

**Issue**: `mysql.connector not found`
```bash

pip install mysql-connector-python
```

**Issue**: `Access denied for user 'root'@'localhost'`
```python

self.password = "your_actual_mysql_password"
```

**Issue**: Database not created
```bash
CREATE DATABASE movie_booking_db;
USE movie_booking_db;
```


## 📝 Sample Login Credentials

After running the application for the first time, register a new account or use the database to insert a test user:

```sql
-- Sample user (password: test123)
INSERT INTO users (username, password, email, phone) 
VALUES ('testuser', 
        '8e1dcdd90b8a7fbb9f43f8b4d23cc33a7bb40e6dc4eb0eaa0e3fb79e56d2d77d',
        'test@example.com', 
        '1234567890');
```

## 👨‍💻 Development

### Adding New Features
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request


##  Acknowledgments

- Tkinter documentation
- MySQL documentation
- Python community

---


**Author**: Esha Mhatre 
**Date**: January 2026  
**Version**: 1.0.0
