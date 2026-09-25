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
> ##### Permissões de Usuário
>
> Usuários podem ter diversas combinações diferentes de permissões.
> As permissões disponíveis são:
> - Cadastrar ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
> - Visualizar ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
> - Excluir ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
> - Alterar ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
> 
> ###### Cargos
> O sistema deve conter cargos pré-definidos estaticamente. Cargos são conjuntos de permissões que facilitam o ato de adicionar multiplas permissões. 
> Usuários podem ter diversos cargos como: 
> - Administrador: Adiciona todas as permissões que existem no sistema.
> >
>
> ##### Autorização de Usuário
>
> Uma sessão de usuário deve durar, no máximo, vinte e quatro horas.
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
          <li>Contém um limite de exibição de produtos (50) <code>(Interface Behavior)</code></li>
          <li>Botão para incluir um produto novo
            <ol>
              <li>Abre um _Modal_ na tela para informar os [Dados do Produto](#produto).</li>
              <li>Desabilitado se mais de um item estiver no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>. <code>(Interface Behavior)</code></li>
            </ol>
          </li>
          <li>Linha de Produto (Elemento Gráfico)
            <ol>
              <li>Deve mostrar os [Dados do Produto](#produto) mais importantes. <code>(Missing Documentation: Especificação de Dados)</code></li>
              <li>Clicar em uma linha de produto abrirá um _Modal_ com a maioria dos dados atuais do banco. <code>(Missing Documentation: Especificação de Dados)</code>
                <ol>
                  <li><del>Para evitar casos de múltiplos usuários modificando dados ao mesmo tempo, será necessário impedir que haja várias mutações (delete, update, put) ao mesmo tempo.</del> (Nota 1)</li>
                </ol>
              </li>
              <li>_Checkbox_ (Elemento Gráfico) 
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
          <li>Ao clicar no botão, ele abrirá o _Modal_ de atualização. <code>(Interface Behavior)</code></li>
          <li>_Modal_ de atualização
            <ol>
              <li>Caixa de entrada para quantidade de produto (a ser abastecida no sistema), que será limitada a quantidade do produto com menor quantidade no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>.</li>
              <li>Caixa de entrada para nome do produto (a ser atualizado), apenas se houver 1 produto no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>.</li>
              <li>Botão de Confirmação.
                <ol>
                  <li>Atualiza todos os itens no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>.</li>
                </ol>
              </li>
            </ol>
          </li>
        </ol>
      </li>
      <li>Deve conter um botão para exclusão do produto <code>(Interface Behavior)</code>  
        <ol>
          <li>Ao clicar no botão, ele abrirá o _Modal_ de exclusão. <code>(Interface Behavior)</code></li>
          <li>_Modal_ de exclusão
            <ol>
              <li>Caixa de entrada para quantidade de produto (a ser retirada do sistema), que será limitada a quantidade do produto com menor quantidade no <a href="#sistema-de-carrinho-de-produto">Sistema de Carrinho de Produto</a>.</li>
              <li>Botão de Confirmação.
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

### Produção

#### Mapa de Requisitos Técnicos

> <br/>
> 
> ### Back End
>
> - Banco de Dados: 
> - Paradigma: Orientado a Objectos
> - Linguagem:
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
> ###### Produto
>
> Para a criação, deverá conter os seguintes dados:
> - Quantidade: ```(Missing Documentation: Significado)``` 
> - Descrição: ```(Missing Documentation: Significado)``` 
> - Código: ```(Missing Documentation: Significado)``` 
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