# Dominio do Sistema

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

> <br/>
>
> ##### Autorização de Usuário
>
> O sistema deve ter no minímo 1 usuário com nome e senha. 
>
> Sempre que houver um tempo de inatividade maior que 1 (uma) hora, o sistema deve voltar para a tela de autorização.
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
> 
> - ```Avisos Não-Interruptivos```: Mensagens (e modais) de sucesso não devem fazer com que o usuário necessite de confirmação para fechar. Elas devem aparecer como pequenos alertas temporários no canto da tela (_toast notifications_) para não quebrar o ritmo de trabalho. 
> - ```Avisos Interruptivos```: Mensagens de erro crítico (ex: "Estoque insuficiente para esta Ordem de Serviço") exigem ação e travam a tela.
> 
> <br/> 


#### Regras de negócio (Extra)

> <br/>
>
>  ##### Estoque 
> 
> - ```Conjuntos```: O sistema deve permitir o cadastro de um "Produto Composto", nesse caso, um conjunto.
>   - Conjuntos podem ser utilizados para dar saída em multiplos produtos ao mesmo tempo, o sistema desconta automaticamente do inventário todos os subcomponentes vinculados a ele.
>   - Conjuntos podem ser utilizados para dar entrada em multiplos produtos ao mesmo tempo, o sistema incrementa automaticamente do inventário todos os subcomponentes vinculados a ele.
>   - **Justificativa**: Para consertar uma Bomba Injetora VE, o bombista não pede ao almoxarifado 1 mola, 3 anéis e 1 eixo separadamente. Ele pede o "Kit de Reparo da Bomba VE".
>   - Conjuntos podem ser utilizados para ver o status de multiplos produtos ao mesmo tempo, o sistema mostra automaticamente o que falta e existe no inventário para todos os subcomponentes vinculados a ele.
>   - **Justificativa**: Aumenta a velocidade de visualização e operação geral.
>   - **Contras**: Pode acabar sendo inutil a medida que a incidencia da necessidade de produtos em conjuntos não está presente na mecanica. Por exemplo, caso todo pedido necessidade de produtos bastantes diferentes.
>     - Entrentanto, pode funcionar para os casos de clientes que vem para refazer o mesmo pedido entre outros. Deve-se analisar o fluxo de caixa real para decidir se isso é necessário.
> - ```Rastreabilidade Automática```: Toda ação de criação, mutação ou exclusão precisa registrar o usuário, a data e a hora onde foi feita. 
> <del>O sistema não deleta itens do banco de dados, ele apenas os inativa ou oculta, preservando o histórico.</del> (Nota 2)
>   - ```Registro Temporário```: O sistema inativa temporáriamente os dados, se eles não forem recuperados pelo usuário em 30 dias, eles serão deletados.
>   - ```Ignorar Dados Desativados```: O código interno deve ignorar dados marcados como desativados nas listagens para visualização a não ser que especificado.
> - ```Tipografia Ampliada```: Códigos de peças automotivas costumam ser longos e alfanuméricos (ex: 0 445 110 318). Eles precisam ser renderizados em fontes monoespaçadas (onde toda letra tem a mesma largura) para evitar erros de leitura.
> - ```Registro de Clientes```: Registrar clientes (nome, telefone etc) para guardar informações de quais peças cada cliente usou através de uma relação entre Produto x Cliente. 
> - ```Equivalência de Produtos```: O produto pode conter um campo "Tipo Equivalente". Quando a busca por uma peça alvo falha, o sistema exibe imediatamente uma sugestão alternativa por equivalencia: "Saldo indisponível. Deseja utilizar o item equivalente X, que possui Y unidades em estoque?".
>   - **Contras**: Custa **tempo notável** e **aumenta bastante a complexidade** do sistema de produtos, principalmente por conter uma série de relações, condições e possibilidades indiretas a serem elaboradas.
> 
>  ##### Permissões de Usuário 
> 
> - ```Permissões```: Usuários podem ter diversas combinações diferentes de permissões.
>  - Cadastrar ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
>  - Visualizar ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
>  - Excluir ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
>  - Alterar ```(Missing Documentation:  Comportamento habilitado)``` ```(Missing Documentation: Recurso Afetado)```
> - ```Cargos```: O sistema deve conter cargos pré-definidos estaticamente. Cargos são conjuntos de permissões que facilitam o ato de adicionar multiplas permissões. 
>   - Administrador: Adiciona todas as permissões que existem no sistema.
> - ```Autorização de Usuário```
>   - Uma sessão de usuário deve durar, no máximo, vinte e quatro horas.
