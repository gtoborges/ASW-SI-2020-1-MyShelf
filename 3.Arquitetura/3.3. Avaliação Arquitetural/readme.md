### Documento de Avaliação Arquitetural

Principais atributos de qualidade priorizados para um padrão arquitetural de API REST:

#### Reliability
O sistema deve estar operante e acessível 24/7 (ou o máximo próximo disso)

#### Security
Garantir a integridade dos dados com boas práticas ao guardar informações do usuário
Utilização do conceito de “transaction” para garantir a integridade dos dados durante operações caso haja múltiplas operações no banco de dados e ocorra falhas.

#### Usability
Interface amigável/simples
Confirmação visual das ações do usuário (para que o usuário tenha certeza de que suas operações foram realizadas ou não)

#### Maintainability
Código dentro dos padrões e boas práticas
Divisão dos arquivos seguindo o padrão inicial definido
