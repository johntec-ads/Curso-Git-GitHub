# **Tutorial curso git / git hub.**
### Links úteis:
- [Sintax markdows.](https://www.markdownguide.org/getting-started/)
- [Exercícios Markdown.](https://www.markdowntutorial.com)

### Objetos fundamentais do Guit.
- **Blobs.**  "Bolha":
_Objeto que armazena metadados,detem o SHA1 do arquivo,ou seja, a 
"Criptografia"_.

- **Trees.**  "Arvores":
_As arvores também armazenam metadados , apontam para os Blobs , pode apontar para outra arvore e também guardam o nome do arquivo._

- **Commits.**
_Os commits são os objetos do texto, que dão significado às alterações, e eles apontam para uma arvore, apontam para um parente, apontam para o autor e apontam para mensagens ,além de textos, eles carregam metadados que armazenam também o horário de criação , altor e também carregam a Criptografia SHAR1_.



### **Comandos iniciais no terminal:**
###### **1- Criando ou deletando um diretório:**
> - _mkdir_: **Cria** uma pasta ou "diretório".Exemplo : mkdir _nome escolhido_.
-_rmdir_ : **Deleta** o diretório completo.**Exemplo:** rmdir /S /Q nome da pasta.

###### **2- Inciando o repositório com ,"_git init_" - Movendo arquivos e iniciando o versionamento com, _"git add"_- Criando o primeiro commit, usando o _"git commit"_**.
###### **a ) primeiro passo, inicialização do Git :**
> - Apos criar um diretório, e estando dentro do mesmo, use o comando **"git init"** , neste momento o diretório passa a ser um **repositório**,e uma pasta oculta **".git"** contendo os arquivos **_hooks, info, objetcts, refs_** é criada, em seguida receberá a mensagem que foi inicializado um repositório vazio dentro do respectivo diretório.
Entre com o comando **"_ls -a_"** ,onde a flag **"-a"** mostra a pasta oculta.
###### **b) segundo passo, criando um arquivo**:
> Use o comando **_echo:_**. Neste exemplo vamos criar um arquivo "Markdown" dentro do respectivo repositório .Exemplo: **_echo nome do arquivo_ ">" _nome do arquivo_.extensão** onde a extensão do markdown é a **.md** .

###### **c ) terceiro passo, movendo o arquivo dentro do Git**:
>- Dentro do diretório escolhido, o comando usado será o **"git add + (*)"** , onde a flag **(*)** engloba todos os arquivos não salvos,movendo o arquivo direto para **Staged** passando o arquivo de "untracked" para "tracked".

###### **d ) terceiro passo, criando o commit:**
>- O próximo passo será o **commit -m** seguido de uma **"String"**, onde a String será um título comentando a alteração feita.
Exemplo: **git commit -m "Salve de rep nº 1"**

###### **3- Cadastro de usuário no GIT**:
> No terminal Git digite o comando **git config --global user.email seuemail@etc.etal e finalize com Enter"**. Obs : Você pode setar de forma Global ou não o repositório , usando para isto a flag **global**.
Novamente no terminal, entre com o comando **git config --user.name _" nome de usuário"_ e finalize com Enter** .



###### **Alguns comandos básicos** :
> - _dir_ : **Lista** os diretórios *pastas* do local.
> - _ctrl_ + l : **Limpa** o terminal .
> - _cd nome da pasta_ : **Entra** no diretório escolhido .
> - _Seta para cima_ ^ : **Lista** os últimos comandos realizados.
> -  _del_ : **Deleta** um arquivo dentro do diretório.

 ## **Formas de autenticação:**
 ###### **1 - Chave SSH.**
 - **Atribuindo chave SSH**. Usando de chave primaria em sua maquina, e chave pública no servidor escolhido, a mesma garante a segurança de seus dados , desde que , sua chave primaria não caia em mãos erradas.
 **GitHub**. Para uso de chave SSH no servidor GitHub, os paço de acesso são :
 _Account Setings_ > _SSH and GPG Keys_.
 Dentro da opçao _SSH Key_ você escolherá  **New SSH Key**.
 No próximo campo vc entra com _Title_ , e logo abaixo , a _Key_ que será gerada no *Git Bash*.
 > **Git Bash:**
Dentro do terminal _Git_ , insira os seguintes comandos:
 - ssh-keygen -t ed25519 -C email@gmail.com , onde **ed** é o tipo de Criptografia , e o e-mail deverá ser o mesmo de sua conta do Git Hub.
 Após o **Enter** , o terminal lhe entregará respostas de que foram geradas às chaves pública e privada , e o local onde estão.
 - Em seguida **Enter** novamente, agora você deve cadastrar uma senha , que será confirmada no próximo passo, e finalizará confirmando que foram geradas as chaves.
 - Agora você mavegada no terminal do Git Bash até o diretório que foram salvas as chaves , e dentro do mesmo, dara o comanda **ls** que listará as chaves geradas ,_id_ed25519_ e _id_ed25519.pub_, esta última sendo a chave pública.
 - Agora com o comando **cat _id_ed25519.pub_** , teremos no terminal a chave pública , que será copiada e adicionada no servidor Git Hub.Em seguida para que a chave seja usada de forma automatica ,no terminal Git Bash e dentro do diretório das chaves , entraremos com o comando **eval $(ssh-agent -s)**, que dara início a chave SSH. Em seguida o terminal lhe mostra o agent _pid_ com o _número_ da inicialização ,e você entregará a chave privada ssh, para o agente pid com o seguinte comando **ssh-add _id_ed25519**, opós isto o terminal lhe pede a senha cadastrada anteriormente , e lhe imprimi no terminal a mensagem que identif added com o _id_ed25519_ e e-mail de cadastro do GitHub.

 ## Exemplo de uso de chave SSH.
 ### _Clonando Repositório Git Hub , com protocolo SSH._
> Obs: A clonagem de um repositório, só é possível sendo o mesmo "Público", pois se for um repositório privado , terá a necessidade de senha para a liberação.
 -  Dentro do servidor Git Hub , na área principal do repositório escolhido , você terá o campo de nome **Code**, nele você tem três opções para copiar o endereço do repositório , como se trata de chave SSH, então copiaremos o respectivo endereço do campo **SSH** .
 - Novamente no terminal do Git Bash , crie um diretório "pasta" para o armazenameto  do repositório, e dentro do mesmo, execute o comando: **Git clone** _"colar o endereço SSH copiado"_, em seguida será exibida uma mensagem e você escolherá **yes** , feito isto , o repositório terá seus dados clonados com sucesso.
 ### 2 - _Token:_
 - A chave token é exigida usando o endereço **HTTPS** copiado do campo **CODE**, é feito a entrada com seu nickname , seguido da entrada da chave tokem gerada neste processo.
 - Dentro do menu _Account Setings_ dentro do GitHub , deve escolher a opção _Developer Setings_ seguido da opção _Personal access tokens_, e deve clicar no botão _Generate new token_ .
 - Na janela aberta, no campo **_Note_** ,registre um nome para sua chave tokem , na próxima **Expiration** ,escolha um prazo de validade para sua chave, e marque na opção **Select scopes** a caixa **repo**.
 - Finalize acionando o botão no final da página , **Generate token**, e
 na próxima tela , terá exibido os caracteres gerados para seu token, que você copiará e salvará em uma pasta segura.
 ## Exemplo de uso de chave TOKEN.
  ### _Clonando Repositório Git Hub , com protocolo TOKEN.
> Obs: A clonagem de um repositório, só é possível sendo o mesmo "Público", pois se for um repositório privado , terá a necessidade de senha para a liberação.
 -  Dentro do servidor Git Hub , na área principal do repositório escolhido , você terá o campo de nome **Code**, nele você tem três opções para copiar o endereço do repositório , como se trata de chave **TOKEN**, então copiaremos o respectivo endereço do campo sugerido .
 - Novamente no terminal do Git Bash , crie um diretório "pasta" para o armazenameto  do repositório, e dentro do mesmo, execute o comando: **Git clone** _"colar o endereço HTTPS copiado"_ , no próximo passo o Git reconhecerá de maneira automática seu nickname , feito isto , o terminal vai pedir a chave **TOKEN** , após entrar com a chave , você terá seus dados clonados com sucesso.

# Conceitos e terminologias:
###### **Tracked and Untracked (Rastreado e Não rastreado).**
###### Modified , Unmodified e Staged.(Modificado , Não modificado e Encenado ou aguardando para o próximo estágio)
- Os arquivos **tracked e untracked** , arquivos que o Git já tem ciência ou não, são definidos por três estágios, **Unmodified, Modified e Staged**
###### **Situações hipotéticas.**
- **Untracked e Unmodified**.Após criar um arquivo com o comando **echo nomeArquivo > "nomeArquivo.extensão"** , o mesmo ainda não foi detectado pelo Git ,estando ele "untracked" e como não foi modificado, também esta Unmodified,sendo assim, usamos o comando "git add * " indo direto de Untracked  para  Staged.
- **Modified**. Ao abrir e alterar uma arquivo, o Git altera seu **SSH**,identificando que houve alterações, e mudando seu status para **Modified**.Se usarmos em seguida o comando **Add (*)**, o arquivo passa de modified para **Staged**.
- **Commit**. Quando após mudar o status dos arquivos para **Modified** ,usamos o **git commit** para encapsular todos os dados do arquivo,que em seguida terá o retorno dos arquivos encapsulados para o status de **Modified** novamente.
###### **Repositórios e Servidores.**
- REMOTE REPOSITORY.
- WORKING DIRECTORY -> STAGING AREA -> LOCAL REPOSITORY.
