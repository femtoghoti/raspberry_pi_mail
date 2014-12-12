raspberry_pi_mail
=================

This is where I will publish notes for getting my Raspberry Pi to email me when it boots up on a network.

`sudo apt-get mailutils ssmtp`

Add a new line to /etc/ssmtp/revaliases like : `root:email.account.to.send.mail.from@somewhere.com:smtp.gmail.com:587`
where you change the email.account.to.send.mail@somewhere.com to the account where you want to recieve the email with your Raspberry Pis IP. 

Adjust your /etc/ssmtp/ssmpt.conf to look like the one in this repository.  Again you will need to change AuthUser and AuthPass to match the credentials of the account you would like to send the email from.

Finally drop the mailip file into /etc/network/if-up.d/ directory.  You will need to change the permissions so it can be executed.  You will also need to change the EMAIL variable to an address where you want to recieve the email.
