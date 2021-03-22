### How to configure XAMPP to send mail from localhost using PHP ?


To configure XAMPP server to send mail from localhost first
we have to **stop all the server(like apache,mysql)** then we have
to make **changes** to two files sendmail.ini and php.ini. Open the
xampp folder.By the name of **sendmail.ini** is present in sendmail 
file and **php.ini** is present in php file in the xampp folder.

- For making change in file "php.ini" which may be present in folder PHP inside XAMPP
  - Step1:  comment SMTP=localhost by putting semicolon infront of it like-;SMTP=localhost
  - Step2:  comment smtp_port=25 by putting semicolon infront of it like-;smtp_port=25
  - Step3:  comment sendmail_from= by putting semicolon infront of it like-;sendmail_from=specify path of
  - Step4:  file in sendmail_path to sendmail_path=C:\xampp\sendmail\sendmail.exe(This path is set where the sendmail.exe lies)
  - Step5:  check if extension=php_openssl.dll is enabled or not If there is semicolon in front then
 un-comment it by removing that semicolon.


- For making change in file "sendmail.ini" which may be present in folder sendmail inside XAMPP
  - Step1:  change smtp_server=mail.yourdomain.com to smtp_server=smtp.gmail.com
  - Step2:  change smtp_port to smtp_port=587
  - Step3:  change smtp_ssl=auto to smtp_ssl=tls
  - Step4:  uncomment ;error_logfile=error.log to error_logfile=error.log
  - Step5:  uncomment ;debug_logfile=debug.log to debug_logfile=debug.log
  - Step6:  write your gmail id in auth_username: auth_username=*****@gmail.com
  - Step7:  write your gmail and password in auth_password: auth_password=*****
  - Step8:  write your gmail id in force_sender: *****@gmail.com
  - Step9:  change hostname to hostname=localhost

Thats the configure for mail sent from localhost using php.

HERE IS THE SIMPLE PHP CODE FOR SENDING MAIL.

        <?php

          $to = "******10@gmail.com";(TO whom you want to send)

          $subject = "This is first email";(subject of mail)

          $message = "hello world!";(Message you want to send)

          $headers = "From: *****************@gmail.com";(from where you are sending)

          if(mail($to, $subject,$message,$headers)){

            echo "mail send successfuly";
          }else{

            echo "cannot send mail"	;
          }


        ?>
        
**NOTE:-**

	You need to restart apache in order for php.ini to reload.
	You need to activate Google Less secure app access in https://myaccount.google.com/u/1/security
	It might help to run Xampp with Admin permission

Hopefuly you may send mail to your friends.
