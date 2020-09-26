# SYSPREPI
[![MIT license](http://img.shields.io/badge/license-MIT-brightgreen.svg)](https://github.com/MikaelSantilio/aprepi/blob/master/LICENSE)

Sistema administrativo da Associação dos Pacientes Renais Crônicos do Estado do Piauí (APREPI)


## Descrição
A proposta inicial é entregar um sistema totalmente funcional, e intuitivo, que possibilite aos usuários realizar, de modo rápido e prático, a gestão de pessoas: sócios, benfeitores e voluntários da APREPI. Também permitir gerenciar eventos, cestas básicas(recebidas e doadas), e ainda, organizar consultas de diversas especialidades oferecidas pela instituição. Além de automatizar essas tarefas, o sistema proposto também seria uma maneira de chegar até novos benfeitores, tendo um plataforma que tornaria mais fácil a divulgação do trabalho realizado no local, bem como fornecendo maior praticidade para realizar doações, tanto para o colaborador quanto para quem recebe.


## Público alvo
- Sócios; 
- Benfeitores;
- Voluntários da APREPI.


## Problema a ser solucionado
A inexistência de um sistema computacional para ajudar a gerenciar as atividades da APREPI, vem causando atrasos nas atividades dela, além de exigir um esforço demasiado de voluntários para manter os dados - referentes aos sócios, as consultas e doações - atualizados.


## Funcionalidades
- **Cadastrar sócios**
    - Sócios são pessoas que se associam para fazer tratamento.

- **Cadastro de Benfeitores**
    - Benfeitores são pessoas que realizam as doações, que podem ser sócios também.

- **Gerar recibo automático**
    - Uma ferramenta que gerasse um recibo a partir de informações inseridas.

- **Organizar consultas**
    - Uma ferramenta que permitisse organizar as consultas, que são realizadas com psicólogo, nutricionista e assistente social.

- **Gerenciar Cestas Básicas**
    - Uma ferramenta que gerencia as cesta básicas que são doadas para a instituição, onde a instituição repassa as mesmas para seus sócios.
- **Gerenciamento de eventos**
    - Uma ferramenta que gerencie os eventos organizados pela instituição, todo evento possui custos e arrecadações.

- **Gerenciamento de Voluntário**
    - Uma ferramenta que permite gerenciar as pessoas que são voluntárias.


## Diagrama de Caso de Uso Preliminar

<img src="https://github.com/MikaelSantilio/aprepi/blob/master/diagrama-caso-uso-v2.jpeg?raw=true" >

## Especificação dos Casos de Uso

| UC-01 | Solicitar consulta |
| - | - |
| Ator principal | Sócio |
| Descrição | O Sócio solicita o agendamento de uma consulta |
| Propósito | Solicitar o agendamento de uma consulta |
| Pré-condição | O usuário estar autenticado no sistema com o perfil de Sócio |
| Pós-condição | Que a solicitação de agendamento de consulta tenha sido realizada |
| Fluxo principal | O Sócio seleciona o botão de solicitação de agendamento de consulta<br/>O sistema exibe um formulário para cadastramento da solicitação<br/>O Sócio informa a especialidade da consulta e uma breve descrição do motivo da solicitação no formulário<br/>O Sócio registra a solicitação<br/>O sistema envia a solicitação para a lista de solicitações do sistema<br/>O sistema informa ao Sócio que assim que a consulta for agendada receberá uma notificação com o dia, hora e o local da consulta<br/>O sistema redireciona o Sócio para a tela principal |
| Fluxo alternativo | - |

| UC-02 | Marcar consulta |
| - | - |
| Ator principal | Funcionário |
| Descrição | Este caso de uso tem a função de detalhar o processo de marcar consulta para um sócio |
| Propósito | Marcar consulta para um sócio com umas das especialidades ofertadas pela instituição |
| Pré-condição | Ter efetuado login como funcionário da instituição |
| Pós-condição | Consulta marcada com sucesso |
| Fluxo principal | 1. O ator acessa a opção **Marcar consulta**<br/>2. O ator verifica a disponibilidade de atendimento da especialidade solicitada pelo sócio<br/>3. O ator preenche os campos com os dados requisitados do sócio<br/>O ator confirma a consulta |
| Fluxo alternativo | - |
| Fluxo exceção | FE01 - Agenda médica lotada<br/>3.1. O ator verificou que não há mais espaço na agenda de nenhum médico da especialidade solicitada<br/>4.1. O ator não marca a consulta<br/>5.1. O sistema notifica o sócio que não foi possível marcar a consulta<br/><br/>FE02 - Falta de médicos da especialidade requisitada<br/>3.1. O ator verificou que não há, no momento, médicos voluntários para a especialidade solicitada.<br/>4.1. O ator não marca a consulta<br/>5.1. O sistema notifica o sócio que não foi possível marcar a consulta |

| UC-03 | Notificar consulta |
| - | - |
| Ator principal | Funcionário |
| Descrição | Este caso de uso tem a função de detalhar o processo de notificar uma consulta marcada ao sócio |
| Propósito | Lembrar o sócio de sua consulta perto da sua data de realização |
| Pré-condição | Ter efetuado login como funcionário da instituição |
| Pós-condição | O sócio é notificado com sucesso da sua consulta |
| Fluxo principal | 1. O sistema notifica o sócio que a data de sua consulta está próxima |
| Fluxo alternativo | Não há |
| Fluxo exceção | FE01 - Erro na notificação<br/>1.1. O sistema não notifica o sócio |

| UC-04 | Fazer doação única |
| - | - |
| Ator principal | Usuário externo |
| Descrição | O Usuário externo realiza uma doação através de boleto bancário ou cartão de crédito. |
| Propósito | Realizar uma doação única |
| Pré-condição | - |
| Pós-condição | Que a doação tenha sido realizada e o benfeitor cadastrado. |
| Fluxo principal | 1. O usuário clica no botão de doação.<br/>2. O sistema leva o usuário para a tela de categorias de doação.<br/>3. Seleciona a opção de doação.<br/>4. O sistema leva o usuário para a tela do formulário de doação.<br/>5. O usuário informa seus dados pessoais para cadastro no sistema.<br/>6. O usuário seleciona a forma de pagamento boleto bancário.<br/>7. O usuário informa o valor da doação.<br/>8. O usuário finaliza a doação.<br/>9. O sistema gera o boleto bancário<br/>10. O sistema leva o usuário para a página de agradecimento com a opção de download do boleto.<br/>11. O sistema envia o boleto e confirmação de cadastro para o email do usuário. |
| Fluxo alternativo | 6. O usuário seleciona a forma de pagamento cartão de crédito.<br/>7. O usuário informa o valor da doação.<br/>8. O usuário finaliza a doação.<br/>9. O sistema faz a cobrança no cartão<br/>10. O sistema leva o usuário para a página de agradecimento.<br/>11. O sistema envia a confirmação de pagamento e cadastro para o email do usuário. |
| Fluxo exceção | - |

| UC-05 | Fazer doação recorrente |
| - | - |
| Ator principal | Usuário externo |
| Descrição | O Usuário externo realiza uma doação recorrente através de cartão de crédito. |
| Propósito | Realizar uma doação recorrente |
| Pré-condição | - |
| Pós-condição | Que o cadastro do benfeitor tenha sido realizado e a doação recorrente registrada. |
| Fluxo principal | 1. O usuário clica no botão de doação.<br/>2. O sistema leva o usuário para a tela de categorias de doação.<br/>3. Seleciona a opção de doação mensal.<br/>4. O sistema leva o usuário para a tela do formulário de doação.<br/>5. O usuário informa seus dados pessoais para cadastro no sistema.<br/>6. O usuário seleciona a forma de pagamento cartão de crédito<br/>7. O usuário informa o valor da doação.<br/>8. O usuário finaliza a doação.<br/>9. O sistema faz o registro do cartão.<br/>10. O sistema leva o usuário para a página de agradecimento.<br/>11.O sistema envia a confirmação de cadastro para o email do usuário. |
| Fluxo alternativo | 3. Seleciona a opção de doação anual. |
| Fluxo exceção | - |

| UC-06 | Fazer doação anônima |
| - | - |
| Ator principal | Usuário externo |
| Descrição | O Usuário externo realiza uma doação anônima através de boleto bancário. |
| Propósito | Realizar uma doação única de forma anônima. |
| Pré-condição | - |
| Pós-condição | Que a doação tenha sido realizada. |
| Fluxo principal | 1. O usuário clica no botão de doação anônima.<br/>2. O sistema leva o usuário para a tela do formulário de doação anônima.<br/>3. O usuário informa seu email para envio de informações sobre a doação e o nome e cpf para gerar o boleto bancário.<br/>4. O usuário informa o valor da doação.<br/>5. O usuário finaliza a doação.<br/> 6. O sistema gera o boleto bancário<br/>7. O sistema leva o usuário para a página de agradecimento com a opção de download do boleto.<br/>8. O sistema envia o boleto para o email do usuário. |
| Fluxo alternativo | - |
| Fluxo exceção | - |

| UC-07 | Receber Cestas Básicas |
| - | - |
| Ator principal | Funcionário |
| Descrição | O funcionário registra uma doação de cesta básica no sistema. |
| Propósito | Registrar as entradas de cestas básicas. |
| Pré-condição | Estar logado no sistema |
| Pós-condição | Estoque de cestas básicas aumenta de acordo com quantidade informada. |
| Fluxo principal | 1. Funcionário faz a autenticação<br/>2. Funcionário registra o que está entrando no estoque<br/>3. Funcionário confirma entrada<br/>4. Recibo é gerado automaticamente<br/>5. Doação é registrada. |
| Fluxo alternativo | 1. Funcionário faz a autenticação<br/>2. Funcionário cadastra o código do material que não tem no sistema. |
| Fluxo exceção | - |

| UC-08 | Distribuir Cesta Básica |
| - | - |
| Ator principal | Funcionário |
| Descrição | O funcionário registra uma distribuição de cesta básica no sistema. |
| Propósito | Registrar as saídas de cestas básicas e informar quem está recebendo. |
| Pré-condição | Estar logado no sistema e ter estoque e cestas. |
| Pós-condição | Estoque de cestas básicas diminui de acordo com quantidade informada. |
| Fluxo principal | 1. Funcionário faz a autenticação<br/>2. Funcionário registra o que está saindo do estoque<br/>3. Funcionário confirma saída<br/>4. Recibo é gerado automaticamente<br/>5.Distribuição é registrada. |
| Fluxo alternativo | 1. Funcionário faz a autenticação<br/>2. Funcionário informa que item está saindo, mesmo que não tenha no estoque, ou ajuste para zero no estoque item que não possui fisicamente, mas no sistema sim. |
| Fluxo exceção | - |


| UC-09 | Criar Evento |
| - | - |
| Ator principal | Funcionário |
| Descrição | O funcionário registra um evento no sistema. |
| Propósito | Criar evento associando participantes e gerenciando gastos e custo |
| Pré-condição | Estar logado no sistema |
| Pós-condição | Ser possível visualizar evento criado pelo o ator |
| Fluxo principal | 1. O ator faz a autenticação no sistema<br/>2. O ator acessa a opção de Criar Evento<br/>3. O ator informa os dados de entrada<br/>4. O ator clica na opção “Associar participante”<br/>5. O ator associa os participantes do evento<br/>6. O ator clica na opção **Gerenciar Gastos**<br/>7. O ator informa os dados necessários e salva<br/>8. O ator clica na opção **Gerenciar Arrecadações**<br/>9. O ator gerencia as arrecadações para o evento<br/>10. O ator clica em **Criar Evento**<br/>11. O sistema redireciona para a tela onde mostra em detalhes o evento criado<br/>12. Fim do caso de uso |
| Fluxo alternativo | - |

| UC-10 | Candidatar-se a voluntário |
| - | - | 
| Ator principal | Usuário externo |
| Descrição | O usuário externo candidata-se à vaga de voluntário no sistema |
| Propósito | Avaliar possíveis voluntários |
| Pré-condição | - |
| Pós-condição | O funcionário irá verificar os dados do voluntário para o cadastrar|
| Fluxo principal | O usuário externo deve clicar no botão **Quero ser voluntário** na página inicial e preencher os dados requisitados<br/>O funcionário verifica os dados fornecidos pelo candidato<br/>O funcionário aprova ou não o candidato a voluntário |
| Fluxo alternativo | O usuário externo deve clicar no botão **Quero ser voluntário** na página inicial e preencher os dados requisitados<br/>O candidato não se enquadra nos pré-requistos para ser voluntário |

| UC-11 | Cadastrar voluntário |
| - | - |
| Ator principal | Funcionário |
| Descrição | O funcionário cadastra um voluntário no sistema |
| Propósito | Cadastrar os voluntários no sistema |
| Pré-condição | O candidato deve atender aos pré-requisitos para à vaga |
| Pós-condição | O funcionário irá cadastrar o voluntário, caso o mesmo atenda aos pré-requisitos |
| Fluxo principal | O funcionário avalia os dados do candidato<br/>O funcionário o cadastra no sistema |
| Fluxo alternativo | O funcionário avalia os dados do candidato<br/>O funcionário não o cadastra por o mesmo não atender os pré-requisitos |  

## Autores

|[<img src="https://avatars0.githubusercontent.com/u/45037602?s=110&v=4" width=110 ><br><small>@rabeloAndre</small>](https://github.com/rabeloAndre)|[<img src="https://avatars1.githubusercontent.com/u/40041499?s=110&v=4" width=110 ><br><small>@MikaelSantilio</small>](https://github.com/MikaelSantilio)|[<img src="https://avatars0.githubusercontent.com/u/58240722?s=110&v=4" width=110 ><br><small>@jefferson-teixeira</small>](https://github.com/jefferson-teixeira)| [<img src="https://avatars3.githubusercontent.com/u/40411200?s=110&v=4" width=110 ><br><small>@RafaelGates</small>](https://github.com/RafaelGates) | [<img src="https://avatars0.githubusercontent.com/u/49573650?s=110&v=4" width=110 ><br><small>@renanaquinno</small>](https://github.com/renanaquinno) |
| :--------------: | :--------------: | :--------------: | :--------------: | :--------------: |
