# Desenvolvimento da Interface do Sistema

## Introdução

A interface de usuário do sistema é uma parte bastante ambiciosa do sistema, pois define um dos principais críterios de aceitação do mesmo: a simplicidade e facilidade. 

A interface do sistema contém 3 principais pontos: Estoque, registro e pedidos. Ambos servindo a um propósito observado no fluxo de tarefas do cliente final. 

### Estoque
O sistema de estoque é o ponto chave, ele contém os dados principais do sistema: os produtos disponíveis, o foco dessa parte da interface é a clareza e visibilidade dos dados, navegação rápida e inserção/atualização fácil. 

### Pedidos
Além disso, o sistema contém uma seção de pedidos, esta seção lida com os produtos que ainda não estão disponíveis no estoque, como pedidos feitos que ainda não chegaram, remoções programadas e pedidos "pre-demanda", aonde o estoque já deixa um pedido pronto a ser feito para quando ele for, de fato, necessário. 

### Registro
Por fim, o sistema também contém uma seção de registros, que oferece noções essenciais sobre quais operações foram feitas no estoque, dando _Insight_ sobre quem fez o quê e quando cada coisa foi feita.

#### Ferramentas Necessárias

> <br/>
> 
> ### Front End
>
> - Fonte de dados: Subsistema local, coadjuvante e offline. 
> - Paradigma: Orientado a Objetos.
> - Linguagem: Python.
> - Framework: PyQt6.
>
> <br/>

---
#### Estilo Visual

Para mais informações sobre os modelos visuais, acesse [Modelos da Interface Gráfica](../assets/README.md)

---
#### Requisitos da UI

> <br/>
> <b>Interface</b>
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