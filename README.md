# FTP-Bash-Backup
A bash script that backups a directory and then uploads it to an external FTP server.
This script has been tested on debian and ubuntu. I cannot guartantee if it'll work on other distributions, but it might.
# Requirements
- The FTP package. This can be installed with `apt-get install ftp`<br/>
This script contains support for encrypting backups with AES-cbc 256 bit. In order to enable the encryption support, openssl must be installed. You can install openssl with `apt-get install openssl`

# Execution
To execute the script, type `bash backupScript.bash`
# Common Issues
<b>Help! I'm getting errors like this when executing the script:</b><br/>
`...$'\r': command not found...`<br/>
This error is caused by improper new line formatting. This can be fixed by installing the dos2unix and running it on the script, like so: `dos2unix backupScript.bash`<br/>
<b>How do I decrypt backups?</b><br/>
Run this command:<br/>
`openssl enc -d -aes-256-cbc -in <encrypted backup> -out backup.tar.gz -pass file:<AES password file>`
# I want to contribute!
That's great! Just make a pull request, and I'll review it soon.
