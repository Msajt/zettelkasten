- Nesse exemplo foi criado uma endpoint para um comando GET para exibir todas as _tasks_ salvas no banco de dados
- Primeiro organizou os arquivos da pasta Controllers.
	-> Organize uma pasta para a sua API e sua versão para então direcionar os seus Controllers feitos nessa pasta, o Laravel já faz a criação das funções do CRUD para seu controller, mas deixando as funções vazias.
- A função `index()` representa a função GET que vai pegar todas as tasks, dentro dela uso a função do Model que retorno todos os dados `ModelName::all()`
- ==É importante sempre se lembrar de colocar os _namespaces_ e os _use_==
- Para organizar a rota, nessa versão do Laravel ela precisa ser gerado a partir do comando `php artisan install:api`, assim, vai criar um arquivo `api.php`, é lá onde vou colocar os endereços da rota para realizar os comandos da API
	-> ```Route::prefix('v1')->group(function(){
		Route::apiResource('/tasks', TaskController::class);
	 });```
- Depois é só testar a endpoint no ThunderClient/Postman
	-> `http://localhost:8000/api/v1/tasks`  GET