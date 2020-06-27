# INSTALAÇÃO NODEJS ATRAVÉS DOS BINÁRIOS.

- Navegue até o diretório

<code>
$ cd /usr/local/lib
</code>

- Crie uma pasta onde os arquivos do Node.Js irão ficar.

<code>
$ sudo mkdir nodejs
</code>

- Entre no diretório que você acabou de criar.

<code>
$ cd nodejs
</code>

- Faça o download do binário

<code>
$ wget https://nodejs.org/dist/v12.16.2/node-v12.16.2-linux-x64.tar.xz
</code>

- Descompacte o binário

<code>
$  sudo tar -xJvf node-v12.16.2-linux-x64.tar.xz -C /usr/local/lib/nodejs
</code>


- Vamos Alterar o dono do diretório.

<code>
$ sudo chown -Rv root.root node-v12.16.2-linux-x64
</code>


# VARIÁVEL DE AMBIENTE $PATH
- Agora devemos incluir o caminho da instalação nas variáveis de ambiente conforme seu perfil de usuário. 
( ~/.bashrc ou ~/.profile).

- Abra o arquivo de configuração do bash.

<code>
$ nano ~/.bashrc
</code>

- Adicione no final do arquivo.

<code>
$   export NODEJS_HOME=/usr/local/lib/nodejs/node-v12.16.2-linux-x64
    export PATH=$NODEJS_HOME/bin:$PATH
</code>

- Em seguida recarregue o arquivo digitando:

<code>
$ . ~/.bashrc
</code>

Pronto, o Node.Js já está instalado em seu Linux.

# TESTANDO A INSTALAÇÃO.
Feche o Terminal e abra-o novamente, e em seguida digite.

<code>
$   node -v
</code>

- Isso deve mostrar a versão que acabamos de instalar.
<code>
$ npm version
</code>

- deverá imprimir informações relacionadas ao NPM.



