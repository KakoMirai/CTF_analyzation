# Analyzation of CVE-2020-10086
The exploit named CVE-2020-10086 is a arbitrary file read exploit in Gitlab that allows the attacker to read arbitrary files on the server. This includes tokens, private data, configs and etc.
This exploit is can be found on the Gitlab versions 10.4 through to 12.8.1 on the Community Edition (CE) and Enterprise Edition (EE).

## Exploit
The vulnerability was pinpointed to the UploadsRewriter. 
It had a exploit that allowed the attacker to use Gitlab to read arbitrary files on the host machine.
The UploadsRewriter didn't validate the file name, which allowed the copying of file via directory traversal when moving issues to another Gitlab project.
The same exploit also allows remote code execution by using the cookies_serializer. First attacker need to get the secret_key_base from /opt/gitlab/embedded/services/gitlab-rails/config/secret.yml. With the secret_key_base attacker can make a Marshalled payload to the experimentation_subject_id cookie. 
## Prevention
The most effecient way to prevent this is to update the Gitlab version to a newer version than 12.8.1. 
