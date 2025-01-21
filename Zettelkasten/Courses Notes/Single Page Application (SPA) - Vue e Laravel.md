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

## Tela de perfil
- Método PUT
- Biblioteca do Laravel pra determinação de regras
- Sistema de migrações
	- #### Adicionando migração:
		- `php artisan make:migration add_image_table_users --table=users`
		- `php artisan migrate`
- Está um pouco bugado na questão de atualizar usuário
- Salvando a imagem
- Deu muitos problemas nessa parte do curso, não se é por conta da datação do curso ou algum erro que não estou percebendo

## Dados do usuário na Tela Principal
- Apenas pegando os dados salvos e colocando nos campos

## Controllers (organização da api)
- `php artisan make:controller UserController`
- Passar o que fiz dentro das funções em api e organizá-las dentro de UserController

## Configurando CORS no Laravel
- laravel-cors
- composer require barryvdh/laravel-cors:0.11.0
- php artisan vendor:publish --provider="Barryvdh\Cors\ServiceProvider"

## Modelando o banco de dados
- Users (já existe)
- Contents (id, user_id, title, text, image, link, date)
- Friends (user_id, friend_id)
- Likes (user_id, content_id)
- Comments (id, content_id, user_id, text, date)
- #### Modelos e migrações
	- php artisan make:model Content -m
	- php artisan make:model Comment -m
	- php artisan make:migration create_friends_table --create=friends
	- php artisan make:migration create_likes_table --create=likes
- $table->foreign('user_id')->references('id')->on('users')->onDelete('cascade');
- php artisan migrate - rodar tabelas criadas

#### Vue.prototype.$http
#### Vue.prototype.$urlAPI

## Refatorando os retornos da API no Laravel

## Formulário de publicação de conteúdo
- php artisan make:controller ContentController

## VueX
- Padrão de gerenciamento de estados, centralizando os registros
- `vue import Vuex from 'vuex'; Vue.use(Vuex)`

## Conteúdo dinâmico
- v-for
- No laravel Accessor (Getters) e Mutators (Setters)
```php
public function getImageAttribute($value){
	return asset($value);
}
```

## Corrigindo erro no cadastro do perfil
- Checar possíveis erros no código na parte da foto

## Listando conteúdo no vuex
- Métodos computados executam quando está carregando
- Métodos (methods) só quando o usuário for executar a função

## Paginação com Vue e Laravel
- next_page_url

## Diretiva para função de scroll infinito

## Deletando dados com o Tinker
```php
php artisan tinker

App\User::all();

$listContents = App\Contents::all()

App\Content::find(id)->delete();
```

## Rota da página de usuário
- this.$route.params.id

## Slug

## Amigos
id_user
id_friend

### watch
### dd()
### whereIn('id', [1, 2, 3])