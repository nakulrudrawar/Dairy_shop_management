# Daily Expense Tracker

A simple web-based expense tracking application built with PHP and MySQL.

## Features

- User registration and login
- Add and manage expenses
- View expense reports by date, month, and year
- User profile management
- Dashboard with charts

## Requirements

- PHP 7.2+
- MySQL/MariaDB
- Apache/Nginx web server

## Installation

1. Create a database named `detsdb`
2. Import `detsdb.sql` file
3. Update database credentials in `includes/dbconnection.php`
4. Place files in your web server directory
5. Access via `http://localhost/project-path/`

## File Structure

- `index.php` - Login page
- `register.php` - User registration
- `dashboard.php` - Main dashboard
- `add-expense.php` - Add new expense
- `manage-expense.php` - Edit/delete expenses
- `expense-reports.php` - View reports
- `includes/` - Database and header files
- `css/` - Stylesheets
- `js/` - JavaScript files
- `assets/` - Images and plugins

## Usage

1. **Register**: Create a new account with email and password
2. **Login**: Use your credentials to log in
3. **Add Expense**: Click "Add Expense" and fill in details
4. **View Reports**: Check expense reports by date, month, or year
5. **Manage Profile**: Update your profile information

## Technologies

- PHP 7.2+
- MySQL/MariaDB
- Bootstrap 3
- jQuery
- Flot.js (Charts)

---

**Version**: 1.0  
**Last Updated**: November 2025
