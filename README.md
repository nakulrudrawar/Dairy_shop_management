# Daily Expense Tracker

A web-based expense tracking application built with PHP and MySQL that allows users to manage and monitor their daily expenses efficiently.

## Features

- **User Authentication**
  - User registration with email verification
  - Secure login system with password encryption (MD5)
  - Password recovery and reset functionality
  - User profile management

- **Expense Management**
  - Add new expenses with date, item description, and cost
  - Edit and manage existing expenses
  - Delete expenses
  - Organize expenses by date

- **Reporting & Analytics**
  - View expenses by date range
  - Monthly expense reports
  - Yearly expense reports
  - Detailed expense breakdowns
  - Visual charts and graphs using Flot.js

- **Dashboard**
  - Quick overview of expenses
  - Chart visualizations
  - User-friendly interface with Bootstrap styling

## System Requirements

- **Web Server**: Apache or Nginx
- **PHP Version**: 7.2 or higher
- **Database**: MySQL/MariaDB 5.7+
- **Browser**: Modern web browser (Chrome, Firefox, Safari, Edge)

## Installation

### Step 1: Database Setup

1. Create a MySQL database named `detsdb`
2. Import the `detsdb.sql` file:
   ```bash
   mysql -u root -p detsdb < detsdb.sql
   ```

### Step 2: Configure Database Connection

Edit `includes/dbconnection.php` and update your database credentials:
```php
$con = mysqli_connect("localhost", "root", "your_password", "detsdb");
```

### Step 3: Deploy Application

1. Copy all project files to your web server directory (htdocs for XAMPP, www for WAMP)
2. Ensure proper folder permissions for the `assets/images/users/` directory

### Step 4: Access the Application

Open your browser and navigate to:
```
http://localhost/Daily-Expense-tracker-using-PHP-and-Msql-main/
```

## Project Structure

```
daily-expense-tracker/
├── index.php                          # Login page
├── register.php                       # User registration
├── dashboard.php                      # Main dashboard
├── add-expense.php                    # Add new expense
├── manage-expense.php                 # Edit/manage expenses
├── logout.php                         # Logout functionality
├── user-profile.php                   # User profile management
├── change-password.php                # Change password
├── forgot-password.php                # Password recovery
├── reset-password.php                 # Reset password
│
├── expense-reports.php                # General expense reports
├── expense-reports-detailed.php       # Detailed expense reports
├── expense-datewise-reports.php       # Date-wise reports
├── expense-datewise-reports-detailed.php
├── expense-monthwise-reports.php      # Monthly reports
├── expense-monthwise-reports-detailed.php
├── expense-yearwise-reports.php       # Yearly reports
├── expense-yearwise-reports-detailed.php
│
├── includes/
│   ├── dbconnection.php              # Database connection
│   ├── header.php                    # Page header
│   ├── footer.php                    # Page footer
│   └── sidebar.php                   # Sidebar navigation
│
├── assets/
│   ├── images/
│   │   ├── background/               # Background images
│   │   ├── big/                      # Large images
│   │   └── users/                    # User profile pictures
│   └── plugins/
│       ├── bootstrap/                # Bootstrap framework
│       ├── flot/                     # Chart library
│       ├── flot.tooltip/             # Chart tooltips
│       ├── gmaps/                    # Google Maps
│       ├── jquery/                   # jQuery library
│       ├── sticky-kit-master/        # Sticky elements
│       └── styleswitcher/            # Theme switcher
│
├── css/
│   ├── bootstrap.min.css
│   ├── bootstrap-theme.min.css
│   ├── datepicker.css
│   ├── font-awesome.min.css
│   └── styles.css                    # Custom styles
│
├── js/
│   ├── bootstrap.min.js
│   ├── bootstrap-datepicker.js
│   ├── chart.min.js
│   ├── chart-data.js
│   ├── custom.js
│   ├── easypiechart.js
│   └── jquery-1.11.1.min.js
│
├── sass/
│   └── styles.scss                   # SASS source files
│
├── tables/
│   ├── data1.json
│   └── data2.json
│
├── detsdb.sql                         # Database schema
└── README.md                          # This file
```

## Database Schema

### Users Table (tbluser)
| Column | Type | Description |
|--------|------|-------------|
| ID | INT(10) | Primary Key, Auto Increment |
| FullName | VARCHAR(150) | User's full name |
| Email | VARCHAR(200) | User's email (unique) |
| MobileNumber | BIGINT(10) | User's phone number |
| Password | VARCHAR(200) | Encrypted password (MD5) |
| RegDate | TIMESTAMP | Registration date |

### Expenses Table (tblexpense)
| Column | Type | Description |
|--------|------|-------------|
| ID | INT(10) | Primary Key, Auto Increment |
| UserId | INT(10) | Foreign key to tbluser |
| ExpenseDate | DATE | Date of expense |
| ExpenseItem | VARCHAR(200) | Description of expense |
| ExpenseCost | VARCHAR(200) | Amount spent |
| NoteDate | TIMESTAMP | When record was created |

## Usage

### For New Users

1. Click on "Register" link on the login page
2. Enter your full name, email, mobile number, and password
3. Click "Register" button
4. Login with your credentials

### Adding an Expense

1. Login to your account
2. Click "Add Expense" from the dashboard
3. Fill in:
   - Expense Date
   - Expense Item (description)
   - Expense Cost (amount)
4. Click "Submit"

### Viewing Reports

1. Navigate to the Reports section from the sidebar
2. Choose report type:
   - Date-wise reports
   - Monthly reports
   - Yearly reports
3. Select date range and view detailed breakdowns

### Managing Profile

1. Click on "User Profile" from the sidebar
2. Update your information
3. Use "Change Password" to update your password

## Security Features

- Password encryption using MD5 (Consider upgrading to bcrypt for production)
- Session management for user authentication
- Email validation for user registration
- Mobile number format validation (10 digits)

## Browser Compatibility

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- IE 11 (partial support)

## Technologies Used

- **Frontend**: HTML5, CSS3, Bootstrap 3, JavaScript, jQuery
- **Backend**: PHP 7.2+
- **Database**: MySQL/MariaDB
- **Charts**: Flot.js, Chart.js
- **Icons**: Font Awesome
- **Data Picker**: Bootstrap Datepicker

## Known Issues & Improvements

### Current Limitations
- MD5 password hashing is deprecated; should use bcrypt/password_hash()
- No prepared statements (vulnerable to SQL injection)
- No CSRF token protection
- Limited input validation on server-side
- No rate limiting on login attempts

### Recommended Improvements
1. Implement prepared statements with parameterized queries
2. Switch to bcrypt for password hashing
3. Add CSRF token protection
4. Implement input sanitization and validation
5. Add email verification during registration
6. Implement proper error handling and logging
7. Add user roles and permissions
8. Implement pagination for large datasets
9. Add export functionality (PDF, Excel)
10. Implement dark mode option

## Future Enhancements

- Mobile app version
- Category-based expense tracking
- Budget planning and alerts
- Recurring expense management
- Multi-currency support
- Data backup and restore
- Expense sharing between users
- Advanced analytics and predictions

## Troubleshooting

### Database Connection Error
- Check if MySQL server is running
- Verify credentials in `includes/dbconnection.php`
- Ensure database `detsdb` exists

### Login Issues
- Verify email and password are correct
- Check if user is registered
- Clear browser cookies and try again

### Chart Not Displaying
- Verify Flot.js plugin is loaded
- Check browser console for JavaScript errors
- Ensure chart data is properly formatted

## Support & Contact

For issues, questions, or suggestions, please create an issue in the project repository.

## License

This project is provided as-is for educational purposes.

## Changelog

### Version 1.0
- Initial release
- User authentication system
- Basic expense management
- Expense reporting features
- Dashboard with charts

---

**Last Updated**: November 2025

