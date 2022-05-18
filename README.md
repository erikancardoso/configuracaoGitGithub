# Introdução ao Git e GitHub usando terminal Linux
### Para preparar o ambiente de desenvolvimento local é preciso alguns passos antes de iniciar o git.
O Git é um sistema de versionamento de controle distribuido
## 1º fazer o Download do Git
 https://git-scm.com/downloads
 
## 2º Gerar par de chaves local para poder usar o repositório remoto
  >$ ssh-keygen -t -C <email do GitHub>
### entrar na pasta das chaves
  >$ cd / .ssh/
### listar as chaves
  >$ ls
##### o resultado será dois id_<valor>(privado) e um id_<valor>.pub (publico)
### visualizar o conteúdo do id_<valor>.pub copiar (obs deve copiar da chave pública)
  >$ cat id_<valor>.pub 
### abrir na aba do perfil do GitHub e selecionar o Setting > Access > SSH and GPG keys
##### clicar em ssh key, dar um titulo e colar a chave no espaço key.
### No terminal: Inicializar o SSH agent
  >$ eval $(ssh-agent -s)
##### mostratá o agent pid<valor>
### Entregar a chave SSH privada para o agent
  >$ ssh-add id_<valor>
##### mostrará identify added: id_<valor> (email github) // concluido com sucesso

 ## 3º Logar no repositório remoto
### Gerando o token no github acesando a aba do perfil setting > Developer settings > token de acesso pessoal 
 Botão Generate new token (Gerar novo token)
##### obs: Deve copiar o token e guardar em um local seguro pois ele servirá como senha de acesso quando precisar logar no repositório remoto para fazer os commits. Marque as caixas( de acordo com a necessidade) para gerar o token e dê um nome para ele.
 ### login repositorio remoto, use o link url la do botão verde do github
  >$ git remote "link url github"
##### pedirá o usuario github e a senha que é o token de acesso
### para consultar os repositórios remotos
  >$ git remote -v
### caso queira renomear o repositório 
  >$ git remote rename origin destination
### copiar o https do code do github
  >$ git remote add origin https://github.com.git
 
## 4º Inicializar o Git em um repositorioGit local
   >$ git init
### configurar o usuário e email, lembrando que deve ser igual ao do GitHub para na hora de fazer o commit o usuário seja sua conta pessoal do github
   >$ git config --global user.name "usuário github"
   >$ git config --global user.email "email do github"
 
## 5.1º clonar um repositório do GitHub no seu ambiente de desenvolvimento local para fazer a modificação, se o repositorio for privado é necessario entrar com usuário e senha.
##### na pasta tem um botão verde com o nome code, lá tem um link https, click em copiar, e vá para a o repositório local pelo terminal
  >$ git clone "link url https......"
 
## 5.2º criar um diretório no repositório para criar arquivos para subir para o repositório remoto
#### criar um diretório
  >$ mkdir LivroDeReceitas
#### criar um arquivo dentro do diretório criado anteriormente
  >~LivroDeReceitas $ echo "Lazanha" > READMI.md
 

## 6º tracked(unmodified, modified, staged) = ciclo de vida do arquivo
  >$ git status
##### verificar o status para saber qual a situação dos documentos
 
###### arquivo.txt baixado/criado = unmodifield // após a modificação no git status aparecerá escrito modified(vermelho), pedirá para usar
  >$ git add *
 
###### arquivo.txt = modified // git status aparecerá escrito modifiel (verde) - staged 
  >$ git commit -m "Meu primeiro Commit"
 
###### arquivo.txt = staged // git status apos o commit não aparecerá nada para ser commitado ou sejá volta a ser unmodifield
 
 ### 7º subindo para o repositorio remoto
  >$ git push origin master
 ##### pedirá para digitar o usuário github e a senha que será o token de acesso //sucessfull ou erro de merge 
### 8º Corrigindo erro de merge 
 
 
 
 
 
 
 
 

 
 
 
 
  
  
  

