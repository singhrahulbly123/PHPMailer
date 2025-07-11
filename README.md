## 📄 Contact Form Code

```php
<?php
use PHPMailer\PHPMailer\PHPMailer;
use PHPMailer\PHPMailer\SMTP;
use PHPMailer\PHPMailer\Exception;

if (isset($_POST['submit'])) {
    $name   = $_POST['name'] ?? '';
    $email  = $_POST['email'] ?? '';
    $mobile = $_POST['mobile'] ?? '';

    send_email($name, $email, $mobile);
}

function send_email($name, $email, $mobile) {
    require 'vendor/autoload.php';

    $mail = new PHPMailer(true);

    try {
        $mail->isSMTP();
        $mail->Host = 'smtp.gmail.com';
        $mail->SMTPAuth = true;
        $mail->Username = 'your-gmail@example.com';
        $mail->Password = 'your-app-password';
        $mail->SMTPSecure = PHPMailer::ENCRYPTION_SMTPS;
        $mail->Port = 465;

        $mail->setFrom('your-gmail@example.com', 'Your Name');
        $mail->addAddress('receiver@example.com');

        $mail->isHTML(true);
        $mail->Subject = 'New Submission';
        $mail->Body    = "Name: $name <br>Email: $email <br>Mobile: $mobile";

        $mail->send();
        echo "Message sent";
    } catch (Exception $e) {
        echo "Error: {$mail->ErrorInfo}";
    }
}
?>
