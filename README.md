# banco-api-tests

## Objetivo

Projeto de automação de testes de API REST responsável por validar o comportamento da API REST do projeto [banco-api](https://github.com/juliodelimas/banco-api). Os testes cobrem os principais endpoints da aplicação, garantindo que as regras de negócio e os contratos da API sejam respeitados a cada execução.

## Stack utilizada

- **[Node.js](https://nodejs.org/)** — ambiente de execução JavaScript
- **[Mocha](https://mochajs.org/)** — framework de testes
- **[Chai](https://www.chaijs.com/)** — biblioteca de asserções
- **[Supertest](https://github.com/ladjs/supertest)** — biblioteca para testes de requisições HTTP
- **[Mochawesome](https://github.com/adamgruber/mochawesome)** — gerador de relatórios HTML dos testes
- **[dotenv](https://github.com/motdotla/dotenv)** — carregamento de variáveis de ambiente a partir de um arquivo `.env`

## Estrutura de diretórios

```
banco-api-tests/
├── fixtures/     # Massas de dados utilizadas nos testes
├── helpers/      # Funções auxiliares e utilitários compartilhados entre os testes
├── test/         # Casos de teste (specs) da API
├── .env          # Variáveis de ambiente (não versionado — deve ser criado pelo usuário)
├── .gitignore
├── package.json
└── package-lock.json
```

Após a execução dos testes, também é gerado o diretório `mochawesome-report/`, contendo o relatório HTML dos resultados. Esse diretório não está versionado no repositório.

## Configuração do arquivo `.env`

O projeto requer um arquivo `.env` na raiz, criado pelo usuário, contendo a URL base da API a ser testada:

```env
BASE_URL=http://localhost:3000
```

> Ajuste o valor de `BASE_URL` de acordo com o endereço onde a API [banco-api](https://github.com/juliodelimas/banco-api) estiver disponível.

## Instalação

```bash
git clone https://github.com/glyciane/banco-api-tests.git
cd banco-api-tests
npm install
```

## Execução dos testes

Com o arquivo `.env` devidamente configurado e a API [banco-api](https://github.com/juliodelimas/banco-api) em execução, rode:

```bash
npm test
```

Esse comando executa os arquivos de teste localizados em `test/**/*.test.js` via Mocha, com timeout de 200000ms, e gera o relatório através do reporter `mochawesome`.

## Obtenção dos relatórios

Após a execução, o Mochawesome gera automaticamente um relatório em HTML no diretório `mochawesome-report/`. Para visualizá-lo, basta abrir o arquivo `mochawesome-report/mochawesome.html` em um navegador.

## Documentação das dependências

- Mocha: https://mochajs.org/
- Chai: https://www.chaijs.com/
- Supertest: https://github.com/ladjs/supertest
- Mochawesome: https://github.com/adamgruber/mochawesome
- dotenv: https://github.com/motdotla/dotenv