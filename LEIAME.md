![ssh](https://user-images.githubusercontent.com/86272521/187820053-3978fbc1-f756-4c10-b790-5f3e3bf1dde5.png)

# SSH - ED25519 - Aumentando a Segurança Em Servidores
> Vídeo no YT: https://youtu.be/qgxupo8HJJw
---------
TUTORIAL:
---------
CRIE A CHAVE:
ssh-keygen -o -a 100 -t ed25519 -f ~/.ssh/id_ed25519 -C "usuarioaqui@servidoraqui"

HABILITE O AGENTE SSH:
----------------------
>eval "$(ssh-agent -s)"

ADICIONE A CHAVE AO AGENTE SSH:
-------------------------------
>ssh-add ~/.ssh/id_ed25519

ESPECIFIQUE A CHAVE PARA SEU SERVIDOR:
---------------------------------------
>ssh -i ~/.ssh/id_ed25519 usuarioaqui@servidoraqui

CUSTOMIZANDO:
--------------
>nano ~/.ssh/config

-----------------------------------------------
| COLE DENTRO DO ARQUIVO: |
 |---|
| Host seunomecustomizadoaqui   |              
 |HostName NOMEDOSEUSERVIDORCUSTOMIZADOAQUI  | 
 |Port SUAPORTADEACESSOAQUI  |                 
 |User NOMEDEUSUARIOAQUI      |                
 |IdentityFile ~/.ssh/id_ed25519 |             
 |IdentitiesOnly yes          |                

FECHE E SALVE: Ctrl + X (para fechar), Y (para salvar)
--------------------------------------------------
>Pronto!
Agora Para Acessar Seu Servidor Basta Rodar: ssh NOMEDOSEUSERVIDORCUSTOMIZADOAQUI

TUTORIAL (Em EN):
>https://medium.com/risan/upgrade-your-ssh-key-to-ed25519-c6e8d60d3c54

LEIA MAIS:
>https://ed25519.cr.yp.to/
