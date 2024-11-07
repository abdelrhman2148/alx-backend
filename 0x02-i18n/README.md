# Project: 0x02. i18n - Internationalization for Flask Application

## Table of Contents
- [Project Overview](#project-overview)
- [Learning Objectives](#learning-objectives)
- [Requirements](#requirements)
- [Setup Instructions](#setup-instructions)
- [Tasks](#tasks)
  - [Task 0: Basic Flask App](#task-0-basic-flask-app)
  - [Task 1: Basic Babel Setup](#task-1-basic-babel-setup)
  - [Task 2: Get Locale from Request](#task-2-get-locale-from-request)
  - [Task 3: Parametrize Templates](#task-3-parametrize-templates)
  - [Task 4: Force Locale with URL Parameter](#task-4-force-locale-with-url-parameter)
  - [Task 5: Mock Logging In](#task-5-mock-logging-in)
  - [Task 6: Use User Locale](#task-6-use-user-locale)
  - [Task 7: Infer Appropriate Time Zone](#task-7-infer-appropriate-time-zone)
  - [Task 8: Display the Current Time](#task-8-display-the-current-time)
- [Usage](#usage)
- [Project Directory Structure](#project-directory-structure)
- [Conclusion](#conclusion)

## Project Overview
This project focuses on implementing internationalization (i18n) for a Flask web application. By incorporating Flask-Babel, the project enables multi-language support, automatic locale selection, and timezone management based on user preferences, URL parameters, and HTTP request headers.

## Learning Objectives
- Set up multi-language support in Flask.
- Infer the appropriate locale from URL parameters, user settings, or request headers.
- Localize timestamps to display in user-preferred time zones.

## Requirements
- **Python Version**: 3.7
- **OS**: Ubuntu 18.04 LTS
- **Coding Style**: Follow `pycodestyle` guidelines (version 2.5)
- **Dependencies**: Flask, Flask-Babel, pytz

## Setup Instructions
1. Clone this repository and navigate to the project directory.
2. Install required packages:
   ```bash
   pip3 install flask flask_babel==2.0.0 pytz
   ```
3. Start the Flask app:
   ```bash
   python3 app.py
   ```
4. Visit `http://127.0.0.1:5000/` to view the application.

## Tasks

### Task 0: Basic Flask App
Create a basic Flask app in `0-app.py` with a single `/` route that renders an `index.html` template, displaying "Welcome to Holberton" as the page title and "Hello world" as the main heading.

### Task 1: Basic Babel Setup
1. Install Flask-Babel.
   ```bash
   pip3 install flask_babel==2.0.0
   ```
2. Configure the app to support English and French by setting `LANGUAGES = ["en", "fr"]`.
3. Set the default locale to English (`"en"`) and timezone to UTC (`"UTC"`).

### Task 2: Get Locale from Request
Implement a `get_locale` function to determine the preferred language based on the `Accept-Language` header.

### Task 3: Parametrize Templates
1. Add `_` or `gettext` functions in templates for language parameters.
2. Create `babel.cfg` and initialize translations:
   ```bash
   pybabel extract -F babel.cfg -o messages.pot .
   pybabel init -i messages.pot -d translations -l en
   pybabel init -i messages.pot -d translations -l fr
   ```
3. Compile the translations:
   ```bash
   pybabel compile -d translations
   ```
4. Verify that both English and French messages display correctly on the page.

### Task 4: Force Locale with URL Parameter
Modify `get_locale` to check for a `locale` parameter in the URL and use it if valid. Otherwise, default to the best match from the request headers.

### Task 5: Mock Logging In
1. Create a `get_user` function to emulate user login using a mock `users` table.
2. Use the `login_as` URL parameter to set a global user in `g.user`.
3. Display user-specific messages based on login status.

### Task 6: Use User Locale
In `get_locale`, set the locale priority:
1. URL `locale` parameter
2. User's preferred locale
3. Request headers
4. Default locale

### Task 7: Infer Appropriate Time Zone
1. Create a `get_timezone` function to determine the user's timezone.
2. Check for timezone in:
   - URL parameter
   - User settings
   - Default to UTC

### Task 8: Display the Current Time
Display the current time based on the inferred time zone. Use the following messages for translation:

| msgid          | English                         | French                           |
|----------------|---------------------------------|----------------------------------|
| current_time_is| "The current time is %(current_time)s." | "Nous sommes le %(current_time)s." |

## Usage
- Access the app at `http://127.0.0.1:5000/`.
- Change the language by adding `?locale=en` or `?locale=fr` to the URL.
- To test user-specific features, append `?login_as=<user_id>` to the URL.

## Project Directory Structure
```plaintext
.
├── app.py                    # Main application file
├── babel.cfg                 # Configuration for translations
├── templates
│   ├── index.html            # Main HTML template
│   └── translations
│       ├── en
│       │   └── LC_MESSAGES
│       │       ├── messages.po
│       │       └── messages.mo
│       └── fr
│           └── LC_MESSAGES
│               ├── messages.po
│               └── messages.mo
└── README.md                 # Project documentation
```

## Conclusion
This project demonstrates how to integrate multi-language support, localization, and timezone management into a Flask application using Flask-Babel. The resulting application can serve users with customized content based on language and time preferences, enriching user experience across different regions.
