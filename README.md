# 📬 PHP Contact Form using PHPMailer  
A lightweight and secure PHP contact form built using **PHPMailer** that sends messages through **Gmail SMTP**.  

Developed by **Bedhadak Rahul Singh Developer**

---

## 🚀 Features

✅ Send form data via **Gmail SMTP**  
✅ Collects **Name**, **Email**, and **Mobile Number**  
✅ Secure with **App Password support**  
✅ Uses PHPMailer's robust backend (used by WordPress, Drupal, Joomla, etc.)  
✅ Lightweight, fast, and easy to customize  
✅ Full HTML email support

---

## 🖼️ Demo Screenshot

*(Add a screenshot of your form or email here if available)*

---

## 📋 Requirements

- PHP 7.2 or higher
- Composer
- Gmail account with **App Password** enabled
- Internet connection

---

## 📥 Installation

1. **Clone the repository** or download:
   ```bash
   git clone https://github.com/your-username/phpmailer-contact-form.git
   cd phpmailer-contact-form
Install PHPMailer via Composer:
composer require phpmailer/phpmailer
Configure your Gmail SMTP credentials inside the PHP code.

💻 Code Overview
PHPMAILER CODE COPY 

<?php
// Bedhadak Rahul Singh Developer
use PHPMailer\PHPMailer\PHPMailer;
use PHPMailer\PHPMailer\SMTP;
use PHPMailer\PHPMailer\Exception;

// if (isset($_REQUEST['submit'])) {
    $name = $_REQUEST['name'];
    $email = $_REQUEST['email'];
    $mobile = $_REQUEST['mobile'];

    send_email($name, $email, $mobile);
}

// function send_email($name, $email, $mobile) {
    require 'vendor/autoload.php';

    $mail = new PHPMailer(true);

    try {
        $mail->SMTPDebug = SMTP::DEBUG_OFF; // Change to DEBUG_SERVER for verbose output
        $mail->isSMTP();
        $mail->Host = 'smtp.gmail.com';
        $mail->SMTPAuth = true;
        $mail->Username = 'your-gmail@example.com'; // Replace with your Gmail
        $mail->Password = 'your-app-password';       // Replace with your App Password
        $mail->SMTPSecure = PHPMailer::ENCRYPTION_SMTPS;
        $mail->Port = 465;

        $mail->setFrom('your-gmail@example.com', 'Bedhadak Rahul Singh Developer');
        $mail->addAddress('receiver@example.com', 'Receiver Name');
        $mail->addReplyTo($email, $name);

        $mail->isHTML(true);
        $mail->Subject = 'New Contact Form Submission';
        $mail->Body = "Name: $name <br> Email: $email <br> Mobile: $mobile";

        $mail->send();
        echo "Message has been sent";
    } catch (Exception $e) {
        echo "Message could not be sent. Mailer Error: {$mail->ErrorInfo}";
    }
}

<!DOCTYPE html>
<html>
<head>
    <title>Contact Form | Bedhadak Rahul Singh Developer</title>
</head>
<body>

    <h2>Contact Form</h2>
    <form method="POST" action="">
        <table cellpadding="10">
            <tr>
                <td><label for="name">Full Name:</label></td>
                <td><input type="text" name="name" id="name" required></td>
            </tr>

            <tr>
                <td><label for="email">Email Address:</label></td>
                <td><input type="email" name="email" id="email" required></td>
            </tr>

            <tr>
                <td><label for="mobile">Mobile Number:</label></td>
                <td><input type="text" name="mobile" id="mobile" required></td>
            </tr>

            <tr>
                <td></td>
                <td><button type="submit" name="submit">Send Message</button></td>
            </tr>
        </table>
    </form>

</body>
</html>

🔐 How to Set Up Gmail App Password
Enable 2-Step Verification in your Gmail account.

Visit Google App Passwords

Generate an App Password for "Mail".

Use that App Password in the $mail->Password field.

📄 License
This project is licensed under the MIT License — you’re free to use and modify it.

👨‍💻 Author
Bedhadak Rahul Singh Developer

📧 Reach out: your-email@example.com
🌐 Portfolio: your-website.com (optional)
🔗 LinkedIn / GitHub: Add your links

🙌 Support
If this project helped you, give it a ⭐️ star on GitHub!
Pull requests and suggestions are welcome.

🧪 Optional To-Do
 Add frontend HTML form

 Add field validation

 Add reCAPTCHA for spam protection

 Add success/error redirect

