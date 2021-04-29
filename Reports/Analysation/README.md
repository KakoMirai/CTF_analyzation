This report is part of a Haaga-Helia UAS security management course and is done by two students. This is a analyzation of a vulnerability used in a HackTheBox machine called "Laboratory". 
You can read the detailed write up about the now retired machine and see how this vulnerability could be used to attack a company. This report will take a closer look about the exploit named CVE-2020-10086.

# Analyzation of CVE-2020-10086
The exploit named CVE-2020-10086 is a arbitrary file read exploit in Gitlab that allows the attacker to read arbitrary files on the server. This includes tokens, private data, configs and etc.
This exploit is can be found on the Gitlab versions 10.4 through to 12.8.1 on the Community Edition (CE) and Enterprise Edition (EE).

## Exploit (unfinished)
The vulnerability was pinpointed to the UploadsRewriter. 
It had a exploit that allowed the attacker to use Gitlab to read arbitrary files on the host machine.
The UploadsRewriter didn't validate the file name, which allowed the copying of file via directory traversal when moving issues to another Gitlab project.
The same exploit also allows remote code execution by using the cookies_serializer. First attacker need to get the secret_key_base from /opt/gitlab/embedded/services/gitlab-rails/config/secret.yml. With the secret_key_base attacker can make a Marshalled payload to the experimentation_subject_id cookie. 
## Prevention (unfinished)
The most effecient way to prevent this is to update the Gitlab version to a newer version than 12.8.1. 

If updating the software is not possible it is advisable to take extra steps to harden and secure your system. 
In this case the security team should start by hardening the Gitlab environment.
Hardening should start from the user management. Signing up to the Gitlab should be disabled and all the users should be verified and approved before giving the access to the projects. 
After the user has been verified to access the Gitlab it should be also verified into the projects it is needed in. Users should also be required to use two-factor authentication to strengthen up the security of accounts.
This all is needed to be done so that the attacker does not have chances for example to sign up with a fake email and this way straight up have basic access to everything in the environment. Access to the Gitlab environment should be only given to right people. 
The actions in Gitlab should also be verified and logged for security purposes. 
In this exploit if the attacker can get into the system and start creating their own projects, they can get sensitive data from the system Gitlab is running on. If there were some more verifications before projects could be created or commented on, then all the moves you need to pull off would be sealed and make it difficult to do the exploits.
