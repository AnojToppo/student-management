### Student Management

## ✨ Features

- College, Student, Course Doctypes with relationships
- Student Courses(Child doctype)
- Auto enrollment numbers (COL-001, COL-002)
- permissions
           (System manager, College admin, All)
-                 System manager and College admin (read, write, create, delete)
-                 All ( read)
- 
College
├── college_name (Mandatory)
├── address
└── website
Course
├── course_name (Mandatory)
├── course_code
├── credits
└── college (Link → College)
Student
├── student_name (Mandatory)
├── email
├── enrollment_no
├── phone no
├── college (Link → College)
└── student_courses (Table → Student Courses Child Doctype)Student Courses (Child Table)
├── course (Link → Course)
└── Belongs to parent Student

## 🖥️ System Requirements

Before installing the Student Management System, ensure your system meets the following requirements:

### Operating System

- **Ubuntu, macOs**

### Software Dependencies

- **Python**: 3.10 or higher
- **MariaDB**: 10.6 or higher
- **Node.js**: 18.x or 20.x (24.x also supported)
- **Redis**: 6.0 or higher
- **Frappe Framework**: Version 15.0
- **Git**: Latest stable version

### System Resources

- **RAM**: Minimum 4GB (8GB recommended)
- **Disk Space**: At least 10GB free space
- **CPU**: Multi-core processor recommended

### Additional Requirements

- Frappe Bench installed and configured
- Proper network connectivity for package installation
- Administrative/sudo access for system configuration

## 🚀 Installation

Follow these steps to install the Student Management System on your Frappe site.

### Step 1: Prerequisites

Ensure you have Frappe Bench installed. If not, follow the official Frappe installation guide:

```bash
# Install Frappe Bench (if not already installed)
sudo apt update
sudo apt install python3-dev python3-pip python3-venv python3-setuptools
sudo apt install mariadb-server mariadb-client
sudo apt install redis-server
sudo apt install git curl

# Install Node.js (using nvm is recommended)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash
nvm install 18

# Install Bench
sudo pip3 install frappe-bench

# Initialize a new bench (if you don't have one)
bench init frappe-bench
cd frappe-bench
```

For detailed installation instructions, refer to the [Frappe Framework Documentation](https://frappeframework.com/docs/user/en/installation).

### Step 2: Get the Application

Clone or get the Student Management application into your Frappe bench:

```bash
# Navigate to your bench directory
cd ~/frappe-bench

# Get the app from GitHub
```bash
bench get-app https://github.com/AnojToppo/student-management
bench --site student.localhost install-app frappe_student_management
bench migrate
bench restart


student management system


### Contributing

This app uses `pre-commit` for code formatting and linting. Please [install pre-commit](https://pre-commit.com/#installation) and enable it for this repository:

```bash
cd apps/student_management
pre-commit install
```

Pre-commit is configured to use the following tools for checking and formatting your code:

- ruff
- eslint
- prettier
- pyupgrade

### CI

This app can use GitHub Actions for CI. The following workflows are configured:

- CI: Installs this app and runs unit tests on every push to `develop` branch.
- Linters: Runs [Frappe Semgrep Rules](https://github.com/frappe/semgrep-rules) and [pip-audit](https://pypi.org/project/pip-audit/) on every pull request.


### License

mit
