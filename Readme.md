# 🐍 Python Gmail Automator

A lightweight, zero-dependency Python script for automating personalized emails and file attachments via Gmail's SMTP server.

Whether you need to send weekly PDF reports to clients, distribute customized newsletters, or automate internal team updates, this script provides a secure and scalable foundation using only Python's standard library.

## ✨ Features

* 📦 **Zero Third-Party Dependencies:** Built entirely with Python's native `smtplib`, `email`, and `os` modules.
* 🔒 **Secure Connection:** Connects to Gmail over a secure SSL layer (Port 465).
* 📝 **Dynamic Personalization:** Uses Python f-strings to inject recipient names, custom subjects, and specific data into each email.
* 📎 **Automated Attachments:** Maps specific files (like personalized PDF reports) to individual contacts on the fly.
* 🔐 **Credential Protection:** Ready-to-use environment variable integration to keep your App Passwords and emails out of your source code.

---

## 🚀 Quick Start

### 1. Prerequisites

* **Python 3.x** installed on your machine.
* A **Gmail account** with [2-Step Verification enabled](https://support.google.com/accounts/answer/185833).
* A generated **Google App Password**. *(Note: Not your usual Gmail password).*

### 2. Installation

Clone this repository to your local machine.


### 3. Security & Configuration (Recommended)

Never commit your passwords to GitHub. The safest way to provide your credentials to the script is via environment variables.

**For Linux/macOS/WSL:** Add these variables to your shell configuration file (e.g., `~/.bashrc` or `~/.zshrc`):

```bash
export FROM_EMAIL="your_email@gmail.com"
export APP_PASSWORD="your_google_app_password"

```

Reload your terminal (`source ~/.bashrc`), then open `app.py` and ensure the script is pulling from your environment:

```python
# Inside app.py
APP_PASSWORD = os.getenv("APP_PASSWORD")
FROM_EMAIL = os.getenv("FROM_EMAIL")

```

*(Note: If you are just testing locally and prefer to hardcode them, you can replace the placeholder strings in `app.py` directly, but **do not commit these changes**).*

### 4. Setup Your Contacts

Open `app.py` and modify the `business_contacts` list. You can define custom recipient addresses, names, custom body text, and assign specific PDF attachments for each individual in the loop.

```python
# Replace example addresses with ones you control
TO_EMAIL_1 = "Zuck@example.com"
TO_EMAIL_2 = "Elon@example.com"

```

### 5. Send Emails

Run the script from the root of the repository so it can locate the attached files:

```bash
python app.py

```

---

## 📁 Repository Structure

```text
send_emails/
├── app.py              # Core email automation engine
├── rick_report.pdf     # Sample attachment 1
├── batman_report.pdf   # Sample attachment 2
├── pickle.png          # Sample image (available for testing, unattached by default)
└── README.md           # Project documentation

```
### 🙏 Acknowledgments


Guided by [@MariyaSha](https://github.com/MariyaSha).


*Happy Automating! 🚀*
