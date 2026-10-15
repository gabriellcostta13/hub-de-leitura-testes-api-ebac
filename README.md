# Testes de API - Hub de Leitura

Projeto desenvolvido durante o curso de QA da EBAC para praticar testes de API utilizando Postman.

## Cenários testados

- Login de administrador e usuário comum
- Listagem e busca de livros
- Cadastro, atualização e exclusão de livros
- Testes positivos e negativos
- Validação de status HTTP e respostas da API

## Tecnologias

- Postman
- API REST
- HTTP e JSON
- JavaScript

## Como executar os testes

### 1. Iniciar a API

É necessário ter o Node.js 18 ou superior instalado.

Baixe o projeto da API:

https://github.com/EBAC-QE/hub-de-leitura-api

Abra a pasta do projeto no terminal e execute:

```bash
npm install
npm run db
npm start
```

Após iniciar o servidor, a API estará disponível em:

`http://localhost:3000`

A documentação dos endpoints pode ser acessada em:

`http://localhost:3000/api-docs`

Mantenha o servidor em execução enquanto realiza os testes.

### 2. Importar a collection no Postman

1. Baixe o arquivo `Hub-de-Leitura-Testes-API-EBAC-Revisada.postman_collection.json` deste repositório.
2. Abra o Postman e clique em **Import**.
3. Selecione o arquivo baixado.
4. Abra a collection **Hub de Leitura - Testes API EBAC**.

### 3. Configurar o ambiente

Crie ou selecione um ambiente no Postman e configure as variáveis:

| Variável | Valor inicial |
|---|---|
| `base_Url_Hub` | `http://localhost:3000` |
| `adminToken` | Deixar vazio |
| `bookId` | Deixar vazio |

Salve o ambiente e selecione-o antes de executar as requisições.

### 4. Executar os testes

Execute as requisições na ordem das pastas:

1. **Login:** valida o acesso de administrador, usuário comum e usuário inexistente.
2. **Adicionar:** testa o cadastro de um livro válido e uma tentativa de cadastro inválido.
3. **Buscar:** testa a listagem, a consulta por ID e a busca de um livro inexistente.
4. **Atualizar:** testa a edição de um livro, verifica os dados atualizados e tenta atualizar um livro inexistente.
5. **Excluir:** testa a exclusão do livro e a tentativa de excluir um livro inexistente.

O login de administrador salva o token utilizado nas operações que exigem autenticação. O cadastro do livro também salva seu ID para uso nas próximas requisições.

Para executar tudo, utilize a opção **Run** da collection no Postman, respeitando a ordem das requisições.

**Importante:** a execução completa altera os dados da API local, criando, atualizando e excluindo um livro.

## Resultado esperado

Cada requisição possui testes automatizados para validar o status HTTP e os dados retornados pela API. No Postman, confira a aba **Test Results** para verificar os testes aprovados e identificar eventuais falhas.
