- O Model representa a lógica e os dados de um negócio, um objeto Model é usado para gerenciar a entrada e saída de dados de uma tabela
- Migrations faz o controle de versionamento de um banco de dados, é uma boa alternativa para se usar em times, pois todos terão os mesmos conteúdos
- Factories gera dados

- Criando uma nova Model
	`php artisan make:model`
		-> Definir o nome e as opções disponíveis
		-> É gerado diversos arquivos conforme as opções escolhidas
- Na pasta `database>migrations` fica a parte da criação do _schema_ onde defino as colunas da minha tabela, dentro da função `up()` defino os elementos da minha tabela do banco de dados:
	==`$table->column_type('column_name')`==
- Lá no arquivo *ModelName*Factory é onde posso gerar dados para minha tabela, é um bom recurso para ser usado para testes, dentro dos parâmetros de retorno da função _definition()_ eu coloco:
	==`column_name => função de saida`==
	O uso da função `fake()` parece ser bem recorrente
- Na pasta `seeders` é onde é chamada a(s) função(ões) para gerar os dados, dentro da pasta `run()` fica o local que devo preencher com o código:
	==`ModelName::factory(data_amount)->create()`==
		**Não se esqueça de colocar `use\Models\ModelName`**
	Com tudo isso pronto, basta ir ao terminal e digitar:
		==`php artisan migrate --seed`==
	Que irá gerar os dados com a quantidade que você determinou

