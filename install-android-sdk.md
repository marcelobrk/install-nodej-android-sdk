# ANDROID SDKK
- Instalar JDK
- Configurar Android SDK
- Definir variáveis de ambiente.
- Testar


# JDK

Vamos começar instalando o JDk.

<code>$ sudo apt install openjdk-8-jre-headless</code>

Anote o caminho da Pasta onde foi instalado o JDK, geralmente fica localizado em 

<code>usr/lib/jvm/java-8-openjdk-amd64</code>
 - Confirme e anote esse caminho para utilizarmos mais tarde.

# ADICIONANDO JAVA_HOME NA VÁRIÁVEL $PATH

- Abra as configurações do terminal ~/.bashrc, ~./profile ou ~/.zsh conforme seu perfil de usuário.

- Adicione ao final do arquivo

<code>$ JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64</code>

Observe que o caminho é o mesmo utilizado anteriormente após a instalação do JDK.

# TESTANDO

Digita no terminal:

<code>$ java -version</code>

Se tudo ocorrer bem devemos ver a mensagem contendo a versão que instalamos da SDK.


# INSTALANDO ANDROID SDK
Neste passo vamos realizar o download da ferramenta Android SDK Tools.

- Acesse o site https://developer.android.com/studio.
- Procure no final da página <b>Command line tools only</b>

Abra o terminal:

- Navegue até o diretório que iremos instalar:

<code> cd ~ </code>

- Vamos criar a pasta
<code> mkdir Android </code>

<code> cd Android </code>

<code> sudo mkdir Sdk </code>

<code> cd Sdk </code>

- Em seguida vamos realizar o Download dos arquivos.
<code> wget https://dl.google.com/android/repository/commandlinetools-linux-6200805_latest.zip </code>

- Agora precisamos extrair
<code> sudo unzip commandlinetools-linux-6200805_latest.zip</code>

Agora já temos algo como  <b>~/Android/Sdk/tools</b>.

# VARIÁVEIS DE AMBIENTE.

Abra as configurações do terminal de acordo com seu perfil de usuário 
    <code> ~/.bashrc ou ~/.profile </code>
- Adicione ao final do arquivo

    <code> export ANDROID_HOME=~/Android/Sdk
    export PATH=$PATH:$ANDROID_HOME/emulator 
    export PATH=$PATH:$ANDROID_HOME/tools 
    export PATH=$PATH:$ANDROID_HOME/tools/bin 
    export PATH=$PATH:$ANDROID_HOME/platform-tools
    </code>

- Force o carregamento das configurações

    <code> . ~/.basrch</code>


# Adicionando SDK Packages

- Listando packages disponíveis.

    <code> $ sudo ~/Android/Sdk/tools/bin/sdkmanager --list</code>

- Instalando packages

    <code> $ sudo ~/Android/Sdk/tools/bin/sdkmanager "platform-tools" "platforms;android-28" "build-tools;28.0.3" "add-ons;addon-google_apis-google-24"</code>


Caso o JDK apresente alguma exceção, pode ser que ele não conseguiu determinar o local de instalação do <b>sdkmanager</b>.

<code>Warning: Could not create settings
java.lang.IllegalArgumentException</code>

.
# Resolvendo
- Tente executar os comandos usando o parâmetro --sdk_root

- Exemplos:

 <code>$ sudo ~/Android/Sdk/tools/bin/sdkmanager --sdk_root=$ANDROID_HOME --list
 </code>


