# ServeRest - Testes de API com Postman

Automação de testes da API [ServeRest](https://serverest.dev) usando Postman.
O projeto cobre o fluxo completo de um CRUD de produtos, com login automático e testes em cada etapa.

## O que foi automatizado

- **Login automático:** um script (Before request) faz o login sozinho e salva o token em uma variável, sem copiar e colar.
- **Autenticação herdada:** todas as requisições usam Bearer Token `{{token}}` definido na collection.
- **Nome de produto dinâmico:** cada execução gera um nome novo, porque a API não aceita nomes repetidos.
- **Requisições encadeadas:** o ID do produto cadastrado é salvo em `produtoId` e reutilizado nas próximas requisições.
- **Testes automatizados:** validação de status code e do conteúdo da resposta em cada requisição.

## Tecnologias

- Postman
- JavaScript (scripts e testes do Postman)
- API ServeRest

## Como executar

1. Baixe os arquivos deste repositório:
   - `serverest-collection.postman_collection.json`
   - `serverest-environment.json`
2. No Postman, clique em **Import** e selecione os dois arquivos.
3. Selecione o environment **Severest** no canto superior direito.
4. Confira se a variável `baseUrl` está com o valor `https://serverest.dev` (sem barra no final).
5. Clique nos três pontinhos da collection → **Run**.
6. Desmarque a requisição **Login** (o login já roda automaticamente) e clique em **Run**.

Se tudo estiver certo, todos os testes ficam verdes.

## Observações

- O usuário usado no login (`fulano@qa.com`) precisa existir na ServeRest. Se não existir, cadastre-o antes pelo endpoint `/usuarios`.
- A ServeRest é uma API pública de estudos e limpa os dados periodicamente.
- O token não é versionado neste repositório.

## Próximos passos

- Adicionar cenários negativos (requisição sem token, cadastro com nome repetido).
- Executar a collection automaticamente com Newman e GitHub Actions.

## Autora

Nataly Castilione
[GitHub](https://github.com/NatalyCastilione)
