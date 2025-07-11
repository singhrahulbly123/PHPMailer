---
name: Php Mailer
about: Php Mailer 100% Working Code
title: Php Mailer 100% Working Code
labels: ''
assignees: ''

---

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
