# Engenharia de Software - Modro - Projeto de Extensão

## Introdução:

A mecânica Fagundes bombas quer fazer investimentos no almoxarifado corporativo, esperando melhorias para diminuir o tempo de descoberta e aumentar a transparência e disponibilidade de informação.

Pontos chaves: Facilidade, transparência e disponibilidade.

Requisitos superficiais:
- O dominio em que o sistema existe necessita de resposta imediatas. O sistema deve ser fácil de acessar. Possivelmente por aplicativos de interface gráfica, no melhor caso, em dispositivos móveis interconectados.
- O dominio em que o sistema existe é afetado por _downtime_, sistema não deve ficar totalmente irreponsível quando houverem falhas e, se falhar, o modulo/sistema que falhar deve ser capaz de ser reiniciado com facilidade.
- O dominio em que o sistema existe é sensível a percas de dados e omição de informação. Todas as ações devem ser transparêntes em relação ao que fazem.

## Duração

Tempo de produção (otimista): 21 Set. - 21 Nov. 2 meses, ou 8 semanas.

Notas importantes:
- As semanas consistem de **6 dias (seg-sábado)**.
- Um período de **duas semanas** (semanas flex) é flexibilizável para _reviews_, _feedbacks_ e remodelagens durante o projeto.

### Fases de Desenvolvimento Cascata:

- Analise de requisitos (1 semana).
  - Formulação dos requisitos, perguntas e observações (4-5 dias, segunda-feira a quinta-feira, ou sexta-feira).
    - Momento para **desenvolver um esboço do que o sistema poderia conter**, levar essas ideias para o cliente e então ver o que ele prefere antes de criar um protótipo visual.
  - Visita técnica & entrevista com o cliente (1 dia, preferir sexta-feira envés de sábado). 
    - Momento para apresentações, **trocas de ideias, analise do fluxo local**, equipamento disponível para implantação do sistema, **avaliar o nível de capacidade dos funcionários e suas opiniões** etc.
- Criação de um protótipo de MVP para aprovação do _Product Owner (PO)_ (1 semana).
  - Escolha das ferramentas (<=2 dias).
  - Criação de um protótipo como imagens, slides, vídeos etc. (tempo restante, até o final da semana)
- Inicio do Desenvolvimento Técnico (1 semana).
  - Formulação dos requisitos técnicos, elaboração técnica do _Minimum Viable Product_. (6 dias, no máximo)
    - Formulação (4 dias, segunda-feira a quinta-feira).
    - Review (1 dia, na sexta-feira).
    - Alterações (1 dia, no sábado).
- Desenvolvimento (2 semanas).
  - Para as etápas do desenvolvimento [clique aqui](#desenvolvimento)
- Apresentação do projeto (1 semana).
  - Desenvolvimento do roteiro de apresentação (2 dias).
  - Desenvolvimento da apresentação como slides, vídeo etc (2 dias).
  - Tempo para a equipe se inteirar dos detalhes da apresentação (3 dias).
  - Apresentação (1 dia, a ser marcado).

#### Tempo total: 6 semanas.

### Fases de Desenvolvimento Flexível:
- Primeiro Periodo de Feedback (3 dias).
    - Recepção do _Feedback_ do protótipo, alterações no protótipo e nova review (periodo flex, a partir da amostrsgem ao cliente, de até no maximo 3 dias).
- Segunda Periodo de Feedback (3 dias).
    - Recepção do _Feedback_ do produto, alterações nas regras de desenvolvimento (periodo flex, a partir da amostragem ao cliente, de até no maximo 3 dias).
- Terceiro Periodo de Feedback (3 dias).
    - Recepção do _Feedback_ de entrega, analise do pontos fracos e fortes para melhorias futuras (periodo flex, a partir da entrega ao cliente, de até no maximo 3 dias).

#### Tempo total de desenvolvimento: 3 dias.

## Sobre as responsabilidades

É esperado que, durante o projeto, todo dia haja ao menos 1 (uma) pessoa investindo no projeto. Para que não fique maçante, a divisão de tarefas deve dispersar as atividades entre os colaboradores com vista na separação entre o tempo de execução. Cada dia uma pessoa diferente assume o procedimento de uma fase, garantindo 1 atividade a cada 5~ dias para cada.

## Desenvolvimento do Produto

### Analise do dominio

- Para começarmos o desenvolvimento do projeto, será necessário dividir em pelo menos 2 frentes. A primeira no desenvolvimento do front-end e a segunda no desenvolvimento do back-end.

* Front-End *
  1 - Tela de login, com input de usuário e senha. Botão de para acessar e botão para recuperar a senha.
    1.1 - Na opção de recuperar a senha, deverá ser enviado um e-mail para o e-mail vinculado a conta que está tentando acessar, solicitando a criação de uma nova senha.
  2 - Página inicial, contendo opções de acesso à página de produtos, página de permissões do sistema e a página de logs.
  3 - Para a página de logs, conterá uma tabela com todas as operações realizadas dentro do sistema (exceto consultas).
  4 - Para a página de permissões, existirá uma tabela com todos os usuários que possuem permissões dentro do sistema, exibindo diferentes tipos de permissões, entre elas: Visualizar, Cadastrar, Alterar, Excluir e Administrador. Onde cada usuário poderá ter diversas combinações diferentes de permissões.
  5 - Para a página de produtos, existirá uma tabela de todos os produtos contados no sistema, que só será exibida após a definição de pelo menos um parâmetro, para que não sobrecarregue a consulta no servidor. Existirá um botão para incluir um produto novo, que abrirá um modal na tela para informar os códigos, descrições e quantidades de acordo com a regra de negócio do cliente. Para editar um produto, será possível clicar em cima de um produto na lista e abrirá o mesmo modal com as informações atuais do banco. (Será necessário impedir que haja alguma movimentação em qualquer outro sistema aberto que possa modificar os dados do produto que se está fazendo a manutenção. Esse impedimento será realizado através de um sistema de semáforo). Também no modal de edição, existirá um botão para exclusão do produto, que só poderá ocorrer caso nenhuma requisição esteja em andamento.
  6 - Existirá um 'checkbox' na linha de cada produto da tabela que ao ser selecionado, jogará as informações do produto dentro de um carrinho no sistema. Após o usuário selecionar todos os produtos que serão retirados do estoque. Ao clicar no botão 'Retirar' que estará junto dos produtos que serão retirados do estoque, ele abrirá mais um modal que você poderá colocar a quantidade a ser retirada do sistema (Desde que o produto não esteja sendo alterado em outro sistema e que haja quantidade suficiente). Após informado a quantidade e realizado a validação do semáforo, o sistema solicitará à API a retirada desses produtos do sistema.
  7 - Existirá um botão para abastecer no canto superior esquerdo, onde você incluirá novas quantidades que serão somadas ao que já existe. Onde você clicará no botão para abastecer, ele aparecerá um modal para você pesquisar o produto que deseja abastecer, e mencionará a quantidade que será abastecida.

* Back-End *
  1 - O back-end seguirá o padrão de orientação a objetos, onde cada classe terá um correspondente ao banco de dados (Por exemplo: Produto, Permissão e Log)
  2 - Permissão
    2.1 - Haverá um endpoint que fará a validação do usuário e senha e retornará um token que poderá ser usado por até 24 horas dentro do sistema se caso a validação for sucesso. Esse token permanecerá armazenado na tabela de permissões no banco de dados.
    2.1 - Haverá quatro endpoints para o sistema de usuários. Três endpoints com o método POST para cadastrar, alterar e excluir permissões e um endpoint com o método GET para consultar um ou mais permissões.
  3 - Logs
    3.1 - Haverá apenas um endpoint com o método GET para obter os logs de acordo com os parâmetros informados.
  4 - Produtos
    4.1 Para os produtos, haverão quatro endpoints possíveis. Três endpoints com o método POST para cadastrar, alterar e excluir produtos e um endpoint com o método GET para consultar um ou mais produtos.
      4.1.1 O método alterar será utilizado tanto para ajustar uma quantidade, abastecer uma quantidade ou requisitar uma quantidade. O cadastro apenas para novos produtos e a exclusão para a exclusão de um produto.
    4.2 Também existirá um endpoint com o método POST que funcionará como um semáforo e bloqueará a utilização do produto, alterando um parâmetro no cadastro do produto.

  5 - No banco de dados, existirão um data base (db_estoque), e três tabelas (tb_permissao, tb_produto, tb_log), onde cada um deles possuirá uma chave primária para a manipulação de seus dados e tb_log possuirá a chave estrangeira de tb_produto. O restante das informações dependerá da regra de negócio do sistema definido pelo cliente.

#### Método de operação

- Define a forma em que a operação de desenvolvimento vai ser gerênciada.

##### Problemas & Prioridades Encontrados 

- Definem os pontos críticos que o sistema devem conter, solucionar e/ou facilitar.

#### Pedidos, Necessidades & Comentários do cliente (Critéria)

- Definem as condições, formato, tempo e qualidade que o cliente espera receber o produto.

#### Regras de negócio

- Definem regras que o sistema deve seguir.
- Definem regras que os desenvolvedores devem seguir.
- Definem regras que componentes especificos do sistema devem seguir.

#### Limitações do cliente

### Produção

A ser feito.

#### Mapa de Requisitos Técnico

A ser feito.

#### Responsabilidades

A ser feito.
