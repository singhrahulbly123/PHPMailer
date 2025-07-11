📧 PHP Contact Form using PHPMailer
A simple and fully functional PHP contact form using PHPMailer to send emails via Gmail SMTP.

Developed by Bedhadak Rahul Singh Developer

🚀 Features
Collects user Name, Email, and Mobile Number

Sends form data via SMTP using Gmail

Uses PHPMailer for secure and reliable email sending

Built with HTML + Core PHP

Easy to configure and deploy

🛠 Requirements
PHP 7.x or higher

Composer

Gmail account with App Passwords enabled

Internet connection (SMTP uses Gmail servers)

📦 Installation
Clone or download this repository:

bash
Copy
Edit
git clone https://github.com/your-username/your-repo.git
cd your-repo
Install PHPMailer using Composer:

bash
Copy
Edit
composer require phpmailer/phpmailer
Update your SMTP credentials in the send_email() function:

php
Copy
Edit
$mail->Username = 'your-gmail@example.com'; // Your Gmail
$mail->Password = 'your-app-password';      // Your Gmail App Password
Customize the recipient email:

php
Copy
Edit
$mail->addAddress('your-receiving-email@example.com');
📋 How to Use
Open the contact form in a browser.

Fill in your Name, Email, and Mobile Number.

Click Submit.

You’ll receive an email with the form details.

🔒 Gmail App Password Setup
Enable 2-Step Verification on your Gmail account.

Go to Google App Passwords

Generate an App Password for "Mail".

Use that password in the $mail->Password field.

🧑‍💻 Author
Bedhadak Rahul Singh Developer

📜 License
This project is open-source and free to use. Add your preferred license if needed.
