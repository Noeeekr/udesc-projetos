# Desenvolvimento do Produto

## Introdução

### Mapa de requisitos

<ol>
    <li>
        Sistema de Autenticação e Autorização (com Sessões)
        <ol>
            <li>Deve remover a sessão do usuário que fique autorizado por intervalo maior do que o definido em <a href="./domain.md#autorização-de-usuário">Duração da Autorização</a></li>
            <li>Deve receber os <a href="#usuário-tabela-usuario">Dados Credenciais</a> e avaliar se coincidem com algum usuário existente.</li>
            <li style="text-decoration: line-through;">Deve armazenar os <a href="#sessão">Dados de Sessão</a>.</li>
            <li style="text-decoration: line-through;">Deve disponibilizar uma interface funcional para criar sessão, terminar sessão, adicionar permissões ao usuário, criar usuário, deletar usuário e modificar usuário (remover permissões, adicionar permissões, modificar o nome, senha etc). 
        </ol>
    </li>
    <li>
        Logs
        <ol>
            <li>Deve disponibilizar uma interface funcional para obter os <a href="#dados-de-logs-banco-de-dados">Logs Coletados pelo Sistema</a> de acordo com os parâmetros informados.</li>
        </ol>
    </li>
    <li>
        Produtos
        <ol>
            <li>
                Deverá haver um sistema de gerenciamento de produtos.
                <ol>
                    <li>
                        Mecanismo de cadastro de produtos.
                        <ol>
                            <li>Deve adicionar um registro de alteração no sistema de registros</li>
                            <li>Deve receber os dados de produto definidos em dados de produto</li>
                            <li>Deve criar uma notificação de feedback de execução</li>
                        </ol>
                    </li>
                    <li>
                        Mecanismo de exclusão de produtos.
                        <ol>
                            <li>Deve adicionar um registro de alteração no sistema de registros</li>
                            <li>Deve receber os dados de produto definidos em dados de produto</li>
                            <li>Deve criar uma notificação de feedback de execução</li>
                        </ol>
                    </li>
                    <li>
                        Mecanismo de alteração de produtos.
                        <ol>
                            <li>Deve adicionar um registro de alteração no sistema de registros</li>
                            <li>Deve receber os dados de produto definidos em dados de produto</li>
                            <li>Deve criar uma notificação de feedback de execução</li>
                        </ol>
                    </li>
                    <li>
                        Mecanismo de consultar de produtos.
                        <ol>
                            <li>Deve mostrar os dados de produto definidos em dados de produto</li>
                        </ol>
                    </li>
                </ol>
            </li>
        </ol>
    </li>
</ol>

---

### Produção

#### Plano de desenvolvimento

- Considerando que o ambiente a qual o sistema será utilizado é controlado e o baixo risco de invasão, para diminuir o tempo de desenvolvimento inicial do sistema, o sistema de autenticação e autorização inicialmente deve conter apenas 1 (um) usuário com nome e senha estaticamente definidos no código, para garantir o mínimo de segurança.  

#### Dados e Ferramentas

> <br/>
> 
> ### Back End
>
> - Banco de Dados: Local; em sistema de arquivos padrão; formato JSON. 
> - Paradigma: Orientado a Objetos.
> - Linguagem: Python.
> - Framework: Nenhum.
>
> Comportamento: Active Record / Data Mapper (cada classe tem um semelhante no banco de dados) 
>
> <br/>

<br>

> <br/>
>
> ### Dados Temporários (Memória)
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
> - Quantidade: Inteiro (Quantidade mais recente do produto em estoque)
> - Descrição: String (Descrição leve do produto)
> - Código: String (Código único do produto no estoque) 
> - Origem: String (Local onde foi comprado, nome do cliente que devolveu a peça etc)
> - Usado: Booleano (Define se a peça é nova ou reusada)
> - Destino: String (Paradeiro do produto)
>
> ### Dados Persistentes (Banco de Dados)
>
> Dados frutos das necessidades do cliente, de operação do sistema e de interface gráfica.
>
> ###### Produto (Tabela _estoque_)
> Ao ser inserido no banco de dados, contém os seguintes dados:
> - Ultimo Modificador: Nome (Ultimo usuário a modificar a log)
> - Ultima Modificação: Data (Momento em que a log foi alterada pela ultima vez)
> - Data de Criação: Data (Momento em que a log foi registrada)
>
> ###### Usuário (Tabela _usuario_)
>
> Dados credenciais:
> - Nome: String (Nome do usuário autorizado, para registros de alterações no sistema)
> - Senha: String (Senha para liberação de entrada no sistema)
> 
> ### Dados de Logs (Banco de Dados)
>
> ###### Logs (Tabela _logs_)
>
> Dados de registro:
>  - Mensagem: String (Ação realizada contendo os identificadores dos dados afetados)
>  - Momento: Data (Momento em que a log foi registrada)
>  - Autor: String (Nome do autor da ação)
>
> ###### Carrinho de Produto
>
> ```(Possible Update: Sistema de Carrinho)```
>
> ###### Sessão
>
> ```(Possible Update: Sistema de Autenticação)```
>
> ###### Permissões (Tabela _permissoes_)
>
> ```(Possible Update: Sistema de Autenticação)```
> 
> <br/>

## Notas

Nota 1: 
O meio atual de resolução para este elemento da interface e comportamento não pode ser construído sem ferir as regras os limites do desenvolvimento ou apresentam problemas que não são necessários resolver devido a estrutura atual do sistema. 
<br/>
[De acordo com limitações do projeto](./domain.md#limitações-do-cliente--produção), é esperado que o sistema funcione sem a necessidade de um servidor conectado a rede external (apenas wifi). 
<br/>
Por causa disso, esse elemento da interface e comportamento serão descartados até a apresentação de uma solução compatível com o sistema.

Nota 2: 
Itens deletados **devem** ser deletados, para não criar um caso de armazenamento de crescimento infinito. Entretanto, registros pequenos das ações podem mantidas indefinidamente. Além disso, há o caso [Quantidade Zero](./domain.md#quantidade-0)

É importante considerar que esta proposta aumenta o tempo de produção do MVP significativamente.

## Extras

```(Missing Documentation: [...])```: Falta a documentação para o tópico definido em ```[...]```.
```(Possible Update: [...])```: O tópico definido em ```[...]``` ainda não é previsto como parte do sistema e está sendo documentado de antemão.