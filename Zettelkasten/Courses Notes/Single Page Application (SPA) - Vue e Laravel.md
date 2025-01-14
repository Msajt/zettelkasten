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
- escrever do @, os v-bind, props, importando o componente