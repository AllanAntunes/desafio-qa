# Teste QA

> Por que Qualidade é importante para você?
[Resposta] A Qualidade basicamente define o sucesso do produto oferecido. Ter um software que atenda às necessidades e expectativas dos clientes e, ao mesmo tempo, tenha um bom funcionamento, com o menor número possível de bugs e boa performance, é o melhor dos mundos. Apesar da Qualidade conter aspectos intangíveis, de negócio, os quais dependem do direcionamento tomado pelos donos do produto, ela é diretamente influenciada pela equipe de desenvolvimento e QAs. Portanto, cada detalhe no ciclo de desenvolvimento de software conta para alcançarmos a sonhada "Qualidade" e, por tabela, a satisfação do cliente final.

> Indique qual a alternativa correta em relação à diferença entre o re-testing e regression testing:
[X] O re-testing está executando um teste novamente; o regression testing procura efeitos colaterais inesperados;
[ ] O re-testing procura efeitos colaterais inesperados; o regression testing está repetindo esses testes;
[ ] O re-testing é feito após as falhas serem corrigidas; o regression testing é feito durante o desenvolvimento da aplicação;
[ ] O re-testing usa ambientes diferentes, o regression testing usa o mesmo ambiente;
[ ] O re-testing é feito por desenvolvedores, o regression testing é feito por QA engineer

> Considerando um serviço de gerenciamento de usuários onde podemos, criar, recuperar informações, atualizar parcialmente, atualizar totalmente e deletar um usuário, respectivamente, informe qual alternativa contém os métodos que realizam essas ações:

Metódos: GET, POST, PATCH, DELETE e PUT

a) cria um usuário
[POST] /users
b) recupera os detalhes do usuário identificado com o id fornecido
[GET] /users/:id
c) atualiza parcialmente o conteúdo identificado com o ID fornecido
[PATCH] /users/:id
d) substitui o conteúdo identificado pelo id fornecido
[PUT] /users/:id
e) exclui o conteúdo identificado com o id fornecido
[DELETE] /users/:id

[ ] GET, POST, PATCH, DELETE e PUT
[ ] PUT, PATCH, DELETE, POST e GET
[X] POST, GET, PATCH, PUT e DELETE
[ ] PATCH, DELETE , PUT, GET e POST
[ ] DELETE, PUT, PATCH, POST e GET

> Quais são os testes de caminho feliz e alternativos que devemos nos atentar durante a validação de uma API REST?
[Resposta] A princípio, é necessário ficar de olho nos resultados aguardados no contrato/documentação/Swagger. Isto inclui os status code de sucesso, os de sem resultados encontrados (quando tratar-se de uma busca) e também as exceções programadas. Porém, também é importante ficar ligado nos possíveis retornos fora do esperado, tanto por bug/objeto retornado fora do padrão acordado, quanto por indisponibilidade do endpoint ou rota.

> O que é pirâmide de teste e qual a sua importância?
[Resposta] A pirâmide de testes é uma representação gráfica dos níveis de testes utilizados para a validação de um software.

  ||   Testes de Sistema -> User Interface Tests/E2E
 ||||  Testes de Integração -> Service Tests
|||||| Testes Unitários -> Unit Tests

https://martinfowler.com/articles/practical-test-pyramid.html

> Considerando o fluxo https://imgur.com/a/D0Zaq8w, escreva os cenários necessários para a cobertura total de testes:
[Resposta]
1. Início da conversa
Validar conteúdo da mensagem inicial

2. Pega Estado
[Observação] Estou considerando que há um script analisando se a sigla inputada é realmente de um Estado brasileiro
Verificar se uma sigla de Estado válida é aceita pelo bot
Verificar se uma sigla de Estado inválida causa mensagem de exceção
Validar input inesperado

3. Pega Cidade
Validar input com 3 ou mais letras
Validar input inesperado com 3 ou mais caracteres alfanuméricos
Validar input inesperado com 2 ou menos letras ou caracteres alfanuméricos

4. Pega Rua
Validar input com 3 ou mais letras
Validar input inesperado com 3 ou mais caracteres alfanuméricos
Validar input inesperado com 2 ou menos letras ou caracteres alfanuméricos

5. Consulta API
Validar menu exibido quando o retorno da API contiver dois ou mais CEPs/Endereços
Validar mensagem exibida quando o retorno da API contém apenas um CEP/Endereço
Validar mensagem de exceção quando o retorno da API não contiver algum CEP/Endereço
Validar mensagem de exceção quando o status code da API for diferente de 200 e 404

6. Escolha uma das ruas
Selecionar opções oferecidas no menu de seleção de logradouro
Validar input inesperado no menu de seleção de logradouro

> Considerando o serviço de busca de CEP (https://viacep.com.br):
a) Crie uma collection no postman com as principais apis
[Resposta] Collection disponível no GitHub

b) Escreva os possíveis cenários de testes para a API de busca: viacep.com.br/ws/RS/Porto Alegre/Domingos/json/
[Resposta]
Validar corpo da resposta quando a API retornar um ou mais CEPs válidos
Validar se array está vazio quando a API não encontrar um CEP válido
Validar se status code 400 é retornado quando um ou mais parâmetros estiverem incorretos

c) Automatize ou realize um teste de performance desse serviço
[Resposta] Teste de performance com JMeter disponível no GitHub

* Teste de carga: como a aplicação se comporta mediante a carga habitual esperada;
* Teste de stress: como a aplicação se comporta mediante uma carga muito maior que a habitual, chegando a encontrar o ponto onde o sistema quebra por excesso de requisições simultâneas;
* Teste de pico: como a aplicação se comporta mediante um pico de acesso, seja em um horário do dia, ou então sazonal;
* Teste de estabilidade: como a aplicação se comporta por um período de tempo, com carga normal, sempre observando a latência. Útil para observar a performance do sistema mediante atualizações de software, servidor e também possível crescimento de resultados de queries SQL.