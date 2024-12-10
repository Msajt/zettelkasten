# 090720242151 Inicializando um ambiente com Laravel
---
- **Data:** 09-07-2024
- **Keywords:** #programação #fullstack #php #laravel #web 
- **Notas Permanentes:**
- **Notas de Literatura:**
---
- Inicializo com o comando no terminal:
	==`laravel new project_name`==
		-> No starter kit
		-> Pest
		-> No
		-> Choose DB
		-> Yes
		-> Yes
- Percebi que dá um problema ao criar o banco de dados no Laravel, depois que é criado o ambiente tenho que usar, não sei se quando for usar outros bancos de dados acontece a mesma coisa, nesse caso aqui, estou usando o MariaDB:
	==`php artisan migrate`==
- Inicializando o servidor local
	==`php artisan serve`== - Na pasta do onde está o projeto
		_localhost:8000_
		_project_name.test_
---
## Referências
https://www.udemy.com/course/laravel-vuejs-fullstack-web-development/learn/lecture/36619242#content