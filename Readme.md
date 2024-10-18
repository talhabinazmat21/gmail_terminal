In your ubunutu terminal type in these commands

	sudo apt update
	sudo apt install msmtp mailutils
 	sudo apt install mutt


Important: To create an app password, you need 2-Step Verification on your Google Account.

To turn on 2 step verification follow these steps
	1. Open your Google Account.
	2. In the navigation panel, select Security.
	3. Under “How you sign in to Google,” select 2-Step Verification and then Get started.
	4. Follow the on-screen steps.

Now to make a app password just search for "App password" in the search bar of your google account settings. Then click the app password and make a new app password and give it a name. After that just copy your app password and paste it to the .msmtp file. 


After that do the following steps

	chmod 600 ~/.msmtprc

And finally to send an email you can write the following command

 	(
	echo "Subject: Subject of the Email"
	echo "To: <recipient_email>"
	echo "MIME-Version: 1.0"
	echo "Content-Type: multipart/mixed; boundary=\"sep\""
	echo ""
	echo "--sep"
	echo "Content-Type: text/plain; charset=utf-8"
	echo "Content-Transfer-Encoding: 7bit"
	echo ""
	echo "<content of email>"
	echo ""
	echo "--sep"
	echo "Content-Type: application/octet-stream; name=\"<name of file>\""
	echo "Content-Transfer-Encoding: base64"
	echo "Content-Disposition: attachment; filename=\"<name of file>\""
	echo ""
	base64 /path/to/file
	echo "--sep--"
	) | msmtp <recipient_email>


	
