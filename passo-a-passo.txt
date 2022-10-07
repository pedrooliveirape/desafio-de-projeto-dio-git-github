# Passo a passo da integração do Git e GitHub

### Configurando chave SSH para o GitHub no Git Bash
	- digite o comando:
		ssh-keygen -t ed25519 -C email@email.com
	de preferência utilizar o mesmo email que você utiliza na sua conta no GitHub.
	Será solicitado que você digite uma senha e posteriormente confirme a senha. Mensagem: "Enter passphrase (empty for no passphrase)".
	- Vá até o local onde foi foi instalada as chaves pública e a privada. Exemplo do caminho(/c/Users/Usuario/.ssh/)
	Use o comando:
		ls
	para exibir as chaves. (id_ed25519 id_ed25519.pub)
	- Digite o comando com o nome da chave pública como a baixo:
		cat id_ed25519.pub
	copie o código que irá aparecer da tela.
	- Vá ao GitHub e em Title digite um nome para a sua máquina e em Key copie a chave eposteriormente digite a senha.

	#### Inicializar o ssh agent
		- Digite o código:
			eval $(ssh-agent -s)
		- Digite o código e a chave privada(id_ed25519) (caso você já esteja dentro da pasta .ssh não precisará digitar o caminho, apenas o nome da chave).
			ssh-add id_ed25519
		Será que solicitado que você digite a senha que foi criada para a chave.

### Configurando o Git pelo Git Bash
	- Crie uma pasta de trabalho.
		Após usar o comando:
			git init
		dentro da pasta. Isso criará uma pasta oculta com as configurações necessárias.

	- Configuração inicial do git, caso ele ainda não tenha sido configurado:
		usar os comandos:
			git --global user.email "email@email.com"
			git --global user.name usuario
		Vale ressaltar que caso o usuário já possua uma conta no Github é indicado usar o mesmo e-mail e nome de usuário da conta do GitHub, para que quando o der um push o GitHub reconheça o usuário e organize os commits melhor.
	
### Realizando um commit
	- utilizar o comando:
		git add *
	- Para a mover todas os arquivos e diretorios criados ou modificados para o status staged.
	utilizar o comando:
		git commit -m "descrição do commit"
	- Isso 'commitará' os arquivos que estão no status staged.

### Git status
	- Para acompanhar o status(de untracked, unmodified, stage ou nothing to commit) dos arquivos e diretórios no git use o comando:
		git status

### Apontando repositório local para o GitHub
	- Com um novo diretório criado no GitHub, copie o endereço que aparece ao selecionar a opção SSH.
	- No Git Dash dentro da pasta do repositório local digite o seguinte código com o endereço:
		git remote add origin endereço_link_copiado

	- Dê um comando:
		git status
	para verificar se a algo a ser commitado. Caso esteja tudo certo prossiga.
	- Digite o comando:
		git push origin master
	- Assim os diretórios e arquivos serão eempurrados(push) para o diretório remoto. Caso você entre no repositório do GitHub você revá que os códigos já etaram lá.
	

