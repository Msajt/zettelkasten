
# Git & Github Crash Course For Beginners
---
- **Data:** 08-04-2024
- **Keywords:** #programação #manual #git
- **Notas Permanentes:**
- **Notas de Literatura:**
---
- #### O que é Git?
	-> É um sistema de controle de versionamento
- #### Comandos básicos
	-> `git init` - Inicializa um repósitório local
	-> `git add <file>` - Adiciona um arquivo ao repositório ('.' para colocar tudo)
	-> `git rm <file>` - Remove o arquivo adicionado ao repositório
	-> `git status` - Checa o estado dos arquivos se foram adicionados, modificados, excluídos, commitados, etc..
	-> `git commit` - Insere as mudanças feitas
		- `-m "message"` - Insere descrição dos arquivos que sofreram commit
	-> `git push` - Envia as mudanças feitas para o repositório remoto (Github, Gitlab, Bitbucket, ...)
	-> `git branch`
	-> `git checkout`
	-> `git merge`
	-> `git pull` - Coleta as informações do repositório remoto
	-> `git clone` - Cria uma cópia local do repositório remoto

- #### Extras
	-> A pasta .git inicialmente aparece escondida para o usuário, basta definir que o computador exiba os ícones ocultos para poder ver as informações desse arquivo
	-> As mudanças do seu repositório local são salvas apenas quando eu faço o `commit` dos arquivos definidos
	-> O arquivo `.gitignore` é composto de uma lista de arquivos do qual eu não quero que seja salvo para o repositório, é uma boa alternativa no caso de precisar proteger arquivos que precisam de um segurança a mais ou do caso de serem arquivos que vão consumir muita memória e que podem ser recarregados, como exemplo, temos o caso da pasta de módulos npm (Javascript) ou do composer (PHP).

---
## Referências

Traversy Media. 2017. **Git & Github Crash Course For Beginners**. Disponível em:  <https://www.youtube.com/watch?v=SWYqp7iY_Tc>
