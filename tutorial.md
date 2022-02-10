# Tutorial curso git / git hub.
### Links úteis:
- [Sintax markdows.](https://www.markdownguide.org/getting-started/)
- [Exercícios Markdown.](https://www.markdowntutorial.com)

### Objetos fundamentais do Guit.
- Blobs.  "Bolha":
_Objeto que armazena metadados,detem o SHA1 do arquivo,ou seja, a 
"Criptografia"_.

- Trees.  "Arvores":
_As arvores também armazenam metadados , apontam para os Blobs , pode apontar para outra arvore e também guardam o nome do arquivo._

- Commits:
_O commit aponta para uma arvore, aponta para um parente,aponta para o autor e para mensagem , ele também armazena o horário que foi criado,também detem um SHAR1_.



### Comandos iniciais no terminal:
###### **1º passo, criando ou deletando um diretório:**
> - _mkdir_: **Cria** uma pasta ou "diretório".Exemplo : mkdir _nome escolhido_.
_rmdir_ : **Deleta** o diretório completo.**Exemplo:** rmdir /S /Q nome da pasta.
###### **2º passo, inicialização do Git :**
> - Use o comando **"git init"** dentro do diretório criado.Uma pasta oculta **".git"** contendo os arquivos **_hooks, info, objetcts, refs_** é criada, em seguida receberá a mensagem que foi inicializado um repositório vazio dentro do respectivo diretório.
Entre com o comando **"_ls -a_"** ,onde a flag **"-a"** mostra a pasta oculta.

###### **3º passo, Cadastro de usuário no GIT**:
> No terminal GIT digite o comando **git config --global user.email seuemail@etc.etal e finalize com Enter"**. Obs : Você pode setar de forma Global ou não o repositório , usando para isto a flag **global**.
Novamente no terminal, entre com o comando **git config --user.name _" nome de usuário"_ e finalize com Enter** .

###### **Criando um arquivo Markdown**:
> Use o comando **_echo:_** para criar um arquivo dentro do respectivo diretório .Exemplo: **_echo nome do arquivo_ ">" _nome do arquivo_.extensão**.
###### **Comandos básicos** :
> - _dir_ : **Lista** os diretórios *pastas* do local.
> - _ctrl_ + L : **Limpa** o terminal 
> - _cd nome da pasta_ : **Entra** no diretório escolhido .
> - _Seta para cima_ ^ : **Lista** os últimos comandos realizados.
> -  _del_ : **Deleta** um arquivo dentro do diretório.

 ## Formas de autenticação:
 ### 1 - Chave SSH.
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

