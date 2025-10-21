# Bypass Authentication Demo

This project demonstrates a brute-force login bypass on a local website using a simple Flask-based web application. It is designed for educational and testing purposes only.


## Features

- **User Registration & Login:**
  - Register new users and securely log in.
  - Admin login with separate credentials.
  - Default admin username and password are hardcoded in the application (`admin` / `password`). You can create your own set of usernames and passwords through the registration panel.

- **Admin Dashboard:**
  - View details for Students, Teachers, Schools, and Income.
  - Recent payments and new students sections.


- **Products Page:**
  - Browse available courses and services.

- **Brute-force Demonstration:**
  - Simulates login bypass scenarios for learning and security testing.


## How to Run

1. Install dependencies:
  ```bash
  pip install flask
  ```
2. Start the server:
  ```bash
  python main.py
  ```


## Steps to Carry Out the Attack

1. First, clone this repository and start the Flask app on your local machine.
2. Open Burp Suite and use the Burp Browser to visit the login panel of the app.
3. Make sure Burp Suite's intercept is turned on, then try logging in with any random credentials.
4. Capture the login request and send it to Burp Repeater. Set the attack type to "Sniper" and mark the username field as the payload position.
5. Now, grab the `usernames.txt` file from this repository and load it as your payload list. Start the attack.
6. Watch the responses: you'll notice that one of the status codes is different from the rest. That's your valid username!
7. Once you've identified "admin" as the correct username, repeat the process—this time, set the payload position to the password field and use a password list.
8. When you spot a different status code, you've found the correct password. Use these credentials to log in to the admin panel.
9. You should now have access to the admin dashboard.

### Sample Brute-force Attack on Username
Use Burp Suite's Sniper attack with the username payload list. Look for a unique status code in the responses to identify the valid username.

### Recommended Browsers
- Chromium or Firefox are recommended for best compatibility with Burp Suite and this demo.

## Security Note
This project is for demonstration only. Do not use this code in production environments. Passwords are stored in plain text for simplicity.

