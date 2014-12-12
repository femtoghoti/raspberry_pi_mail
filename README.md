raspberry_pi_mail
=================

This documents how to get a Raspberry Pi to email its IP address when it boots up on a network.

These are my notes on getting a Raspberry Pi to email me its address when connected to a network.  I wanted to be able to plug the Pi into a netowrk and then ssh into it and do what I needed.  After some digging, and piecing together, and trying things that didn't work, arrived in the following place.  This is not to say this is the easiest, or simplest way to do this, it is just the what I found.  I welcome feedback on this matter.

`sudo apt-get mailutils ssmtp`

Add a new line to /etc/ssmtp/revaliases like : `root:email.account.to.send.mail.from@somewhere.com:smtp.gmail.com:587`
where you change the `email.account.to.send.mail@somewhere.com` to the account where you want to recieve the email with your Raspberry Pis IP. 

Adjust your /etc/ssmtp/ssmpt.conf to look like the one in this repository.  Again you will need to change AuthUser and AuthPass to match the credentials of the account you would like to send the email from.

Finally drop the mailip file into /etc/network/if-up.d/ directory.  You will need to change the permissions so it can be executed.  You will also need to change the EMAIL variable to an address where you want to recieve the email.

Now you should be able to plug the Raspberry Pi into a network and it will email you its IP address :)
