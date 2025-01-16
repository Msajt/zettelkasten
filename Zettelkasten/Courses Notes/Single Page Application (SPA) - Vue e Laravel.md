- **Início:** 13/01/2025
- **Fim**: --/--/2025
- **Tags:** #cursos #programação 

## Criação do ambiente de desenvolvimento
- `npm install -g @vue/cli`
- `npm i -g @vue/cli-init`
- `vue init <package> <name>` -> `vue init webpack social`
- `cd social`
- `npm run dev`
- Pelo curso ser um pouco antigo, a criação do ambiente de desenvolvimento está dessa forma, atualmente faz o uso do _vite_ para a inicialização desses projetos, além de serem mais simples, possuem uma melhor performance.

## Diretórios do projeto
- **build:** configurações do webpack
- **static:** configurações de estilos e frameworks externos
- **src:** conteúdo dos componentes
- **index.html:**
- `npm run build`
- Edição das pastas dentro de **src** para melhor organização e explicação da exibição dos componentes

## Gerando o projeto em produção (build)
- `npm run build`
- Gera um arquivo de distribuição com todos os arquivos minificados
- Posso rodar em qualquer servidor, no caso o instrutor utiliza um servidor PHP: `php -S localhost:8000`

## Materialize e AdminLTE
- São bibliotecas de estilização que já traz a formatação de alguns componentes gerais como, cartões, footers, navbar, etc. No caso a instalação foi bem tranquila, apesar de eu estar usando uma versão mais antiga, a forma de fazer ainda se mantém bem parecida, mudando apenas algumas coisas

## Montando a _navbar_
- o _@_ serve como atalho para a pasta _src_
- Os atributos html dentro de um componente, se for necessário usar de forma dinâmica, se utiliza o `v-bind:attribute` ou apenas `:attribute`
- Posso passar variáveis pela chamada do componente utilizando os _props_
	- **props:** ['var1', 'var2', ...]
- A importação do componente faço dentro do componente pai

## Montando o *footer*
- Conceito de slots
## Sistema de *grid*
- Conceito de grids

## Preparando o _menu lateral_ e o _cartão de conteúdo_
- Vemos que é possível reaproveitar uma parte dos componentes feitos para serem aproveitados de outras formas
- #### Detalhes do cartão de conteúdo
	- Uso do *v-if* para exibir ou não se caso houver uma imagem/texto

## Campo de texto para publicações
- Conceito de v-model

## Sistema de templates
- Divisão de páginas e rotas

## Organização de slots
`<slot name='nome_slot'>`

## Urls amigáveis

## Tela de cadastro
- Uso de aparição condicional com v-if e v-else
- Uso do v-on:click

## Instalação do Laravel
- Falar do processo de instalação utilizando o Docker
- ![[Pasted image 20250115171742.png]]
- ![[Pasted image 20250115172419.png]]
- ![[Pasted image 20250115171504.png]]
```php
sudo docker compose up --build // Iiicializar o docker com php 7
sudo docker exec -it laravel-app bash // Usar o terminal do docker
php artisan serve --host=0.0.0.0 --port=8000 // Inicializar o servidor local
// Instalando o laravel
composer create-project --prefer-dist laravel/laravel webservice "5.5.*"
composer require laravel/passport "4.0"
// Banco de dados
php artisan migrate
php artisan passport:install
// Em User
use Laravel\Passport\HasApiTokens;
use HasApiTokens, Notifiable;
// Em config/auth
'api' => [
	'driver' => 'passport',
	'provider' => 'users',
],
```

## Rotas da API no Postman
- Em `routes/api.php`
- Testando rotas GET e POST
	- `Route::method('/address', function)`

## Criação da rota de /cadastro
- Hash da senha
- Token de autenticação do usuário
- #### Exibir informações do usuário cadastrado
	- Headers -> **Key:** Authorization -> **Value:** Bearer $token
- #### Validação do cadastro
	- **Modelo:** _RegisterController.php_ -> _Validator_

## Criação da rota de /login
- `Auth::attempt(['user_data'])`

## Comunicação entre backend e frontend com _axios_
- Uso do v-model e v-on para controle das variáveis e botões
- Uso de variáveis em _data()_ e _methods_
- Filtrar possíveis erros de entrada
- Foi usando o axios@0.18

## Estilização dos responses do servidor
- Geração de uma *session*
- `sessionStorage.setItem('user', JSON.stringify(response.data))`
- método *created()* em *LoginTemplate* (ciclo de vida da aplicação)
- sessionStorage.getItem('user');
- sessionStorage.clear();