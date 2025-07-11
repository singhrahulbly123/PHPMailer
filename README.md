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

bash
Copy
Edit
composer require phpmailer/phpmailer
Configure your Gmail SMTP credentials inside the PHP code.

💻 Code Overview

<?php
// Bedhadak Rahul Singh Developer
//Import PHPMailer classes into the global namespace Bedhadak Rahul Singh Developer
//These must be at the top of your script, not inside a function Bedhadak Rahul Singh Developer
use PHPMailer\PHPMailer\PHPMailer;
use PHPMailer\PHPMailer\SMTP;
use PHPMailer\PHPMailer\Exception;

if(isset($_REQUEST['submit']))
   {

$name=$_REQUEST['name'];
$email=$_REQUEST['email'];
$mobile=$_REQUEST['mobile'];

send_email($name,$email,$mobile);

   }

   function send_email($name,$email,$mobile){



//Load Composer's autoloader
require 'vendor/autoload.php';

//Create an instance; passing `true` enables exceptions
$mail = new PHPMailer(true);

try {
    //Server settings
     $mail->SMTPDebug = SMTP::DEBUG_SERVER;                      //Enable verbose debug output
    $mail->isSMTP();                                            //Send using SMTP
    $mail->Host       = 'smtp.gmail.com';                     //Set the SMTP server to send through
    $mail->SMTPAuth   = true;                                   //Enable SMTP authentication
    $mail->Username   = 'SMTPusername Emalil Id';                     //SMTPusername
    $mail->Password   = 'SMTPpassword Emalil App Password';                               //SMTPpassword
    $mail->SMTPSecure = PHPMailer::ENCRYPTION_SMTPS;            //Enable implicit TLS encryption
    $mail->Port       = 465;                                    //TCP port to connect to; use 587 if you have set `SMTPSecure = PHPMailer::ENCRYPTION_STARTTLS`

    //Recipients
    $mail->setFrom('SMTPusername', 'Bedhadak Rahul Singh Developer');
    $mail->addAddress('example@gmail.com', 'Bedhadak Rahul Singh Developer');     //Add a recipient
     $mail->addAddress('example@gmail.com');
     $mail->addCC('');

    //Attachments
    // $mail->addAttachment('/var/tmp/file.tar.gz');         //Add attachments
    // $mail->addAttachment('/tmp/image.jpg', 'new.jpg');    //Optional name

    //Content
    $mail->isHTML(true);                                  //Set email format to HTML
    $mail->Subject = 'Bedhadak Rahul Singh Developer';
    $mail->Body    = "Name : $name <br> Email : $email <br> Mobile : $mobile";
    //$mail->AltBody = 'This is the body in plain text for non-HTML mail clients';
    
    $mail->send();
    // echo 'Message has been sent';
    $message="Message has been sent";
} catch (Exception $e) {
    echo "Message could not be sent. Mailer Error: {$mail->ErrorInfo}";
}
}
?>
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

