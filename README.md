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

---

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

- Para começarmos o desenvolvimento do projeto, será necessário unificar as ideias da equipe, elaborar um plano de analise de requisitos e coletar os dados para garantir a precisão do desenvolvimento. 
- Após a analise de requisitos, para o desenvolvimento será necessário dividir em pelo menos 2 frentes. A primeira no desenvolvimento do front-end e a segunda no desenvolvimento do back-end.

#### Método de operação

- Scrum

#### Critéria (problemas, prioridades etc) 

##### Pedidos do cliente

- Definem as condições, formato, tempo e qualidade que o cliente espera receber o produto.

##### Necessidades do cliente

- Definem os pontos críticos que o sistema devem conter, solucionar e/ou facilitar.

##### Comentários do cliente 

##### Limitações do cliente & produção

- Lonely Node: Para simplicidade do projeto e diminuição de custos iniciais, é esperado que o sistema funcione em apenas uma máquina por vez.
  - Wifi Only: Se possível, é esperado que o sistema evolua para funcionar em máquinas na rede local quando ativo.
    - Internet Available: Se possível, é esperado que o sistema funcione 24h com acesso a internet. 

---

### Requisitos

#### Regras de negócio

- Definem regras que o sistema deve seguir.
- Definem regras que os desenvolvedores devem seguir.
- Definem regras que componentes especificos do sistema devem seguir.

> <br/>
> 
> ##### Quantidade 0
>
> Como há a possibilidade alta de entrada e saída de produtos previsiveis, é ideal que possa haver produtos com quantidade 0 para prevenir a reconfiguração de produtos. 
> 
> Para entender o problema, imagine o caso, "criei um produto X, todas as unidades acabaram, o produto foi removido, pedi um novo estoque, tive que criar X de novo e registrar o estoque novo".   
>
> ##### Movimentação em Massa do Estoque
>
> De acordo com a analise do colaborador _Elian_, o sistema deve considerar eventos de movimentação em massa, pois em primeiro caso de uso, grandes volumes de estoque terão de ser registrados. Isso serve para garantir a velocidade de registro em eventuais casos de mudanças de estoque (loja 1 para loja 2) ou remoções em larga escala (vendas em lotes).
>
> Ao considerar esses eventos, o sistema deve permitir, no mínimo, criações e baixas em lotes. Nesse caso, ao criar/remover 10 produtos diferentes uma vez sem ter eventos de interrupção no processo, com possíveis keybinds facilitadoras ou sistema simplificado.
>
> ##### Etiquetas
>
> O sistema deve permitir que um produto tenha etiquetas, que permitem definir a localização do produto no estoque físico. Um produto pode ter mais de uma etiqueta, por exemplo, etiqueta A (prateleira 5) etiqueta B (quinta linha da prateleira) para facilitar a alteração depois.
>
> ##### Localização preemptiva
>
> O sistema deve permitir filtrar produtos por nome e manter correspondencias por nome como prioridade de visualização. Junto a isso, deve ser capaz de filtrar por outros dados, como descrição, etiqueta etc. Nesse caso, o sistema deve mostrar eles ranqueados da seguinte forma: todos com correspondencia de nome (maior correspondencia primeiro), todos com correspondencia de descrição (maior correspondecia primeiro) e depois por etiqueta. 
>
>
> <br/> 


#### Requisitos de UI

<b>
Interface
</b>

> <br/>
>
> <ol id="front-end">
>   <li>Sistema de Autenticação &amp; Autorização</li>
>   <li>Sistema de Visualização de Produtos</li>
>   <li>Sistema de Adição de Produtos</li>
>   <li>Sistema de Remoção de Produtos</li>
>   <li>Sistema de Atualização de Produtos</li>
>   <li>Sistema de Pedidos</li>
>   <li id="sistema-de-carrinho-de-produto">Sistema de Carrinho de Produtos</li>
>   <li>Sistema de Criptografia de Dados</li>
> </ol>
>
> <br/>

<br/>

<ol id="interface-de-login">
  <li>Interface de login
    <ol>
      <li>Campos de inserção para nome de usuário e senha. 
        <ol>
          <li><del>Botão de para acessar e botão para recuperar a senha.</del> (Nota 1) 
            <ol>
              <li><del>Deverá ser enviado um e-mail para o e-mail vinculado a conta que está tentando acessar, solicitando a criação de uma nova senha.</del></li>
            </ol>
          </li>
        </ol>
      </li>
    </ol>
  </li>
  <li id="interface-base">Interface base
    <ol>
      <li>Acesso a <a href="#interface-de-logs">Interface de Logs</a></li>
      <li>Acesso a <a href="#interface-de-produtos">Interface de Produtos</a></li>
      <li>Acesso a <a href="#interface-permissões">Interface de Permissões do Sistema</a></li>
    </ol>
  </li>
  <li id="interface-de-logs">Interface de logs
    <ol>
      <li>Tabela com todas as operações realizadas <code>(Missing Documentation: Lista das operações disponíveis)</code> dentro do sistema (exceto consultas <code>(Missing Documentation: Caracterização da consulta)</code>).</li>
    </ol>
  </li>
  <li id="interface-permissões">Interface permissões
    <ol>
      <li>Tabela com todos os usuários que possuem permissões dentro do sistema.
        <ol>
          <li>Exibir os diferentes [Tipos de Permissões](#permissões-de-usuário) que o usuário contém.</li>
        </ol>
      </li>
    </ol>
  </li>
  <li id="interface-de-produtos">Interface de produtos
    <ol>
      <li>Tabela com os produtos contados no sistema.
        <ol>
          <li>Barra de navegação por nome
            <ol>
              <li>Deve ignorar espaços, hífens e pontos.</li>
              <li>Deve conter tratamento de texto
                <ol>
                  <li>Se digitar 0445110318 ou 0-445-110-318, o sistema deve encontrar a mesma peça.</li>
                  <li>Perdoar erros de digitação comuns (ex: buscar "Bosh" e o sistema entender "Bosch")</li>
                </ol>
              </li>  
            </ol>
          </li>
          <li>Contém um limite de exibição de produtos (50) <code>(Interface Behavior)</code></li>
          <li>Botão para incluir um produto novo
            <ol>
              <li>Abre um <i>Modal</i> na tela para informar os [Dados do Produto](#produto).</li>
              <li>Desabilitado se mais de um item estiver no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>. <code>(Interface Behavior)</code></li>
            </ol>
          </li>
          <li>Linha de Produto (Elemento Gráfico)
            <ol>
              <li>Deve mostrar os [Dados do Produto](#produto) mais importantes. <code>(Missing Documentation: Especificação de Dados)</code></li>
              <li>Clicar em uma linha de produto abrirá um <i>Modal</i> com a maioria dos dados atuais do banco. <code>(Missing Documentation: Especificação de Dados)</code>
                <ol>
                  <li><del>Para evitar casos de múltiplos usuários modificando dados ao mesmo tempo, será necessário impedir que haja várias mutações (delete, update, put) ao mesmo tempo.</del> (Nota 1)</li>
                </ol>
              </li>
              <li><i>CheckBox</i> (Elemento Gráfico) 
                <ol>
                  <li>Ao ser clicado, passa as informações do produto para o <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produtos</a> do sistema.</li>
                  <li>Após informado a quantidade e realizado a validação do semáforo, o sistema solicitará à API a retirada desses produtos do sistema. <code>(Interface Behavior)</code></li>
                </ol>
              </li>
            </ol>
          </li>
        </ol>
      </li>
      <li>Deve conter um botão para atualização da maioria dos [Dados do Produto](#produto) <code>(Interface Behavior)</code> <code>(Missing Documentation: Especificação de Dados)</code>
        <ol>
          <li>Ao clicar no botão, ele abrirá o <i>Modal</i> de atualização. <code>(Interface Behavior)</code></li>
          <li><i>Modal</i> de atualização
            <ol>
              <li>Caixa de entrada para quantidade de produto (a ser abastecida no sistema), que será limitada a quantidade do produto com menor quantidade no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>.</li>
              <li>Caixa de entrada para nome do produto (a ser atualizado), apenas se houver 1 produto no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>.</li>
              <li>Botão de Confirmação. <code>UI Interruptiva</code>
                <ol>
                  <li>Atualiza todos os itens no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>.</li>
                </ol>
              </li>
            </ol>
          </li>
        </ol>
      </li>
      <li>Deve conter um botão para baixa do produto <code>(Interface Behavior)</code>  
        <ol>
          <li>Ao clicar no botão, ele abrirá o <i>Modal</i> de baixa. <code>(Interface Behavior)</code></li>
          <li> <i>Modal</i> de baixa
            <ol>
              <li>Caixa de entrada para quantidade de produto (a ser retirada do sistema), que será limitada a quantidade do produto com menor quantidade no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>.</li>
              <li>Botão de Confirmação. <code>UI Interruptiva</code>
                <ol>
                  <li>Exclui todos os itens no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>.</li>
                </ol>
              </li>
            </ol>
          </li>
        </ol>
      </li>
    </ol>
  </li>
</ol>

**Gerais**

- ```Avisos Não-Interruptivos```: Mensagens (e modais) de sucesso não devem fazer com que o usuário necessite de confirmação para fechar. Elas devem aparecer como pequenos alertas temporários no canto da tela (_toast notifications_) para não quebrar o ritmo de trabalho. 
- ```Avisos Interruptivos```: Mensagens de erro crítico (ex: "Estoque insuficiente para esta Ordem de Serviço") exigem ação e travam a tela.

**Extras** (Prioridade decrescente).

- ```Conjuntos```: O sistema deve permitir o cadastro de um "Produto Composto", nesse caso, um conjunto.
  - Conjuntos podem ser utilizados para dar saída em multiplos produtos ao mesmo tempo, o sistema desconta automaticamente do inventário todos os subcomponentes vinculados a ele.
  - Conjuntos podem ser utilizados para dar entrada em multiplos produtos ao mesmo tempo, o sistema incrementa automaticamente do inventário todos os subcomponentes vinculados a ele.
  - **Justificativa**: Para consertar uma Bomba Injetora VE, o bombista não pede ao almoxarifado 1 mola, 3 anéis e 1 eixo separadamente. Ele pede o "Kit de Reparo da Bomba VE".
  - Conjuntos podem ser utilizados para ver o status de multiplos produtos ao mesmo tempo, o sistema mostra automaticamente o que falta e existe no inventário para todos os subcomponentes vinculados a ele.
  - **Justificativa**: Aumenta a velocidade de visualização e operação geral.
  - **Contras**: Pode acabar sendo inutil a medida que a incidencia da necessidade de produtos em conjuntos não está presente na mecanica. Por exemplo, caso todo pedido necessidade de produtos bastantes diferentes.
    - Entrentanto, pode funcionar para os casos de clientes que vem para refazer o mesmo pedido entre outros. Deve-se analisar o fluxo de caixa real para decidir se isso é necessário.
- ```Rastreabilidade Automática```: Toda ação de criação, mutação ou exclusão precisa registrar o usuário, a data e a hora onde foi feita. 
<del>O sistema não deleta itens do banco de dados, ele apenas os inativa ou oculta, preservando o histórico.</del> (Nota 2)
  - ```Registro Temporário```: O sistema inativa temporáriamente os dados, se eles não forem recuperados pelo usuário em 30 dias, eles serão deletados.
  - ```Ignorar Dados Desativados```: O código interno deve ignorar dados marcados como desativados nas listagens para visualização a não ser que especificado.
- ```Tipografia Ampliada```: Códigos de peças automotivas costumam ser longos e alfanuméricos (ex: 0 445 110 318). Eles precisam ser renderizados em fontes monoespaçadas (onde toda letra tem a mesma largura) para evitar erros de leitura.
- ```Registro de Clientes```: Registrar clientes (nome, telefone etc) para guardar informações de quais peças cada cliente usou através de uma relação entre Produto x Cliente. 
- ```Equivalência de Produtos```: O produto pode conter um campo "Tipo Equivalente". Quando a busca por uma peça alvo falha, o sistema exibe imediatamente uma sugestão alternativa por equivalencia: "Saldo indisponível. Deseja utilizar o item equivalente X, que possui Y unidades em estoque?".
  - **Contras**: Custa **tempo notável** e **aumenta bastante a complexidade** do sistema de produtos, principalmente por conter uma série de relações, condições e possibilidades indiretas a serem elaboradas.
 ##### Permissões de Usuário (Extra)

- ```Permissões```: Usuários podem ter diversas combinações diferentes de permissões.
 - Cadastrar ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
 - Visualizar ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
 - Excluir ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
 - Alterar ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
- ```Cargos```: O sistema deve conter cargos pré-definidos estaticamente. Cargos são conjuntos de permissões que facilitam o ato de adicionar multiplas permissões. 
  - Administrador: Adiciona todas as permissões que existem no sistema.
- ```Autorização de Usuário```
  - Uma sessão de usuário deve durar, no máximo, vinte e quatro horas.

### Back End

  1.  Sistema de Autenticação e Autorização (com Sessões)
      1.  Deve remover a sessão do usuário que fique autorizado por intervalo maior do que o definido em [Duração da Autorização](#autorização-de-usuário)
      2.  Deve armazenar os [Dados de Sessão](#sessão)
      3.  Deve receber os [Dados de Autenticação](#dados-de-login) e criar uma sessão caso reflitam as credenciais de um usuário existente. 
      4.  Deve disponibilizar uma interface funcional para criar sessão, terminar sessão, adicionar permissões ao usuário, criar usuário, deletar usuário e modificar usuário (remover permissões, adicionar permissões, modificar o nome, senha etc). ```(Missing Documentation: Especificação de Funcionalidade)```
  2. Logs
      1.  Deve disponibilizar uma interface funcional para obter os [Logs Coletados pelo Sistema](#dados-de-logs) de acordo com os parâmetros informados. ```(Missing Documentation: Especificação de Parametros)```
  3. Produtos
     1.  Para os produtos, deverá haver um sistema de gerenciamento.
         1. Mecanismo de cadastro de produtos.
            1. Deve ser capaz de receber parametros que identifiquem os produtos alvo.
         2. Mecanismo de exclusão de produtos. 
            1. Deve ser capaz de receber parametros que identifiquem os produtos alvo.
         3. Mecanismo de alteração de produtos.
            1. Deve ser capaz de receber parametros que identifiquem os produtos alvo.
            2. Deve disponibilizar ajuste de quantidade, incremento (abastecimento) de quantidade ou remoção de uma quantidade. 
         4. Mecanismo de consultar de produtos.
            1. Deve ser capaz de receber parametros que identifiquem os produtos alvo.

---
### Histórico de Atualizações com o Cliente

---

**Primeira Visita Técnica**
#### Dúvidas

```Modo Escuro ou Claro por Padrão```


**Justificativa**
Em oficinas, telas muito claras podem cansar a vista e evidenciar marcas de dedos e sujeira no monitor. Para aumentar a velocidade do processo de desenvolvimento, é esperado fazer apenas um dos dois para o produto inicial, por isso, a escolha do estilo de cores é essencial.

- Paletas de cores com fundo escuro e fontes de alto contraste devem melhorar a visibilidade à distância.
- Muito constrante pode acabar sendo prejudicial. 
- Paletas de cores baseadas em preto são mais dificeis de navegar. 

```Especificidade```

**Justificativa**
Existem peças de alto valor agregado (ex: Módulos Eletrônicos ECM) que exigem o registro do Número de Série individual de cada peça que entra e sai. Já outras o controle é apenas por quantidade (ex: temos 5 unidades, não importa o número de série delas).

```Funcionamento dos pedidos e armazenamento```

Deve-se considerar perguntar sobre o fluxo na qual os pedidos acontecem. Dando enfoque a forma em que são recebidos e também como são armazenados: com que dados, se são etiquetados, o que entra e sai mais.

```Pontos mais recorrentes ou necessários```

Deve-se considerar questionar o que mais acontece em relação ao estoque que atrasa os funcionários (tempo de procura, notificar baixa para outros funcionários, ter que checar precificação no site etc).

_Provavelmente registros de eventos, dados de estoque e descrições de eventos_

```Terminais```

Verificar quantos terminais são utilizados no local, isso pode definir a complexidade e disponibilidade do sistema (se pode ser feita para apenas um computador ou deve ser em rede).

****
#### Feedback Recebido

---

### Produção

#### Mapa de Requisitos Técnicos

> <br/>
> 
> ### Back End
>
> - Banco de Dados: Provavelmente Local, em memoria com salvamento em JSON. 
> - Paradigma: Orientado a Objetos.
> - Linguagem: Python.
> - Framework: PyQt.
>
> Comportamento: Active Record / Data Mapper (cada classe tem um semelhante no banco de dados) 
>
> <br/>

<br>

> <br/>
>
> ### Dados Temporários (Sistema)
> 
> ###### Carrinho de Produto
>
> ```(Missing Documentation: Dados)```
> 
> ###### Sessão
>
> ```(Missing Documentation: Dados)```
>
> ###### Etiquetas de Produto (Dados de localização)
>
> Para a criação, deverá conter os seguintes dados:
> - Produto: Referencia (O produto a qual a etiqueta se refere)
> - Nome: String (O nome/apelido da etiqueta)
> - Descrição: String (A descrição de onde o produto está)
>
> ###### Produto
>
> Para a criação, deverá conter os seguintes dados:
> - Quantidade: ```(Missing Documentation: Significado)``` 
> - Descrição: ```(Missing Documentation: Significado)``` 
> - Código: ```(Missing Documentation: Significado)``` 
> - Origem: String (Local onde foi comprado, nome do cliente que devolveu a peça etc)
> - Usado: Booleano (Define se a peça é nova ou reusada)
> - Destino: String (Paradeiro do produto)
>
> ###### Dados de Login
>
> ```(Missing Documentation: Dados)```
>
> ### Dados (Banco de Dados)
>
> Dados frutos das necessidades do cliente, de operação do sistema e de interface gráfica.
>
> ###### Produto (Tabela _estoque_)
> Ao ser inserido no banco de dados, contém os seguintes dados:
> - Ultimo Modificador: ```(Missing Documentation: Significado)```
> - Ultima Modificação: ```(Missing Documentation: Significado)```
> - Data de Criação: ```(Missing Documentation: Significado)```
>
> ###### Permissões (Tabela _permissoes_)
>
> ```(Missing Documentation: Dados)```
> 
> ###### Usuário (Tabela _usuario_)
>
> Dados credenciais:
> - Nome: ```(Missing Documentation: Significado)```
> - Senha: ```(Missing Documentation: Significado)```
> 
> ### Dados de Logs (Banco de Dados)
>
> ###### Logs (Tabela _logs_)
>
>  ```(Missing Documentation: Dados)```
>
> <br/>

#### Responsabilidades

Documentação.
- Lead: André
- Auxiliar & Elaborator: Eduardo
- Auxiliar & Elaborator: Murilo 
- Elaborator: Elian

Visita Técnica & Intermediação (Feedbacks, Propostas etc).
- Lead: Elian
- Participant: André


## Proximas Etapas

1. Visita Técnica
2. Converter as informações da visita para requisitos
3. Definir o visual dos elementos em [Requisitos de Interface Gráfica](#requisitos-de-ui).
4. Definir uma stack de desenvolvimento para _frontend_ e _backend_.

## Notas

Nota 1: 
O meio atual de resolução para este elemento da interface e comportamento não pode ser construído sem ferir as regras os limites do desenvolvimento ou apresentam problemas que não são necessários resolver devido a estrutura atual do sistema. 
<br/>
[De acordo com limitações do projeto](#limitações-do-cliente--produção), é esperado que o sistema funcione sem a necessidade de um servidor conectado a rede external (apenas wifi). 
<br/>
Por causa disso, esse elemento da interface e comportamento serão descartados até a apresentação de uma solução compatível com o sistema.

Nota 2: 
Itens deletados **devem** ser deletados, para não criar um caso de armazenamento de crescimento infinito. Entretanto, registros pequenos das ações podem mantidas indefinidamente. Além disso, há o caso [Quantidade Zero](#quantidade-0)

É importante considerar que esta proposta aumenta o tempo de produção do MVP significativamente.