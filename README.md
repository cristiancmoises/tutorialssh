![ssh](https://user-images.githubusercontent.com/86272521/187820053-3978fbc1-f756-4c10-b790-5f3e3bf1dde5.png)

# SSH - ED25519 - Increasing Security on Servers
> Video on YT (PT-BR): https://youtu.be/qgxupo8HJJw
> Para a versão em português deste readme clique [aqui](https://github.com/cristiancmoises/tutorialssh/blob/main/LEIAME.md)
---------
TUTORIAL:
---------
CREATE KEY:
ssh-keygen -o -a 100 -t ed25519 -f ~/.ssh/id_ed25519 -C "hereuser@hereserver"

ENABLE THE SSH AGENT:
----------------------
>eval "$(ssh-agent -s)"

ADD KEY TO SSH AGENT:
-------------------------------
>ssh-add ~/.ssh/id_ed25519

SPECIFY THE KEY FOR YOUR SERVER:
---------------------------------------
>ssh -i ~/.ssh/id_ed25519 -p YOURPORTHERE usuarioaqui@servidoraqui

CUSTOMIZING:
--------------
>nano ~/.ssh/config

| PASTE INSIDE THE FILE: |
|---|
| Host yourcustomnamehere  |
| HostName YOURSERVERNAME CUSTOMIZED HERE  |
| User USERNAME HERE  |
| IdentityFile ~/.ssh/id_ed25519  |
| IdentitiesOnly yes  |

 

CLOSE AND SAVE: Ctrl + X (to close), Y (to save)
--------------------------------------------------
>Ready!
Now To Access Your Server Just Run: ssh YOURSERVERNAME CUSTOMIZED HERE

TUTORIAL (In EN):
>https://medium.com/risan/upgrade-your-ssh-key-to-ed25519-c6e8d60d3c54

READ MORE:
>https://ed25519.cr.yp.to/

