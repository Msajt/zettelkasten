- O Sanctum é um pacote do Laravel que auxilia na questão da autenticação do usuário na página, armazena os tokens no banco de dados e autentica os requests por meio do header de _Authorization_ que contém o token válido.
- O Sanctum se baseia nos cookies do Laravel, verifica por um cookie de autorização, caso não houver verifica o header para um token válido
- Os arquivos referentes ao Sanctum já são gerados no momento que estou configurando a API
	-> `php artisan install:api`
- **Configuração do CORS:**
	-> `php artisan config:publish cors`
	-> _cors.php_: `'supports_credentials' => true`
	-> _.env:_ `SESSION_DOMAIN:localhost` ou o domínio que você está usando