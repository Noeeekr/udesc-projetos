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
  - Para as regras do desenvolvimento [Cheque a Definição de Domínio](./development/domain.md)
  - Para o desenvolvimento de UI [Cheque a Interface Visual](./development/frontend.md)
  - Para o desenvolvimento do sistema interno [Cheque o Sistema Interno](./development/backend.md)
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

## Informações de Execução do Projeto

Informações sobre datas, responsabilidades e outros podem ser encontradas em [Arquivo de Registro](./registry.md).

Informações sobre entrevistas com o cliente, _Feedback_ e notas adicionais podem ser encontradas na [Seção de Entrevistas](./interviews.md).