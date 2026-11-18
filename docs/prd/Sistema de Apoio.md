# PRD 0001: Sistema de Apoio a Alunos com Deficiência

- **Status:** Aceito
- **Data:** 2026-11-18
- **Especificações:**

## Objetivo

Sistema de Apoio a Alunos com Deficiência é uma plataforma educacional e de suporte desenvolvida para oferecer um ambiente virtual seguro, gratuito e adaptado, auxiliando no processo de aprendizagem de crianças com TDAH (Transtorno do Déficit de Atenção com Hiperatividade) e Discalculia.

## Perfis de uso

| Perfil                  | Quem é                                       | O que precisa fazer                                                                                              |
| ----------------------- | -------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- |
| Criança                 | Aluno usuário da plataforma educacional      | Acessar materiais didáticos e se comunicar com a equipe multidisciplinar                                         |
| Pais                    | Responsável do aluno                         | Monitorar e alterar dados e informações do perfil Criança                                                        |
| Equipe Multidisciplinar | Psicólogos, pediatras e outros especialistas | Monitorar e alterar dados e informações do perfil Criança, podendo também adicionar e excluir materias didáticos |

## Requisitos funcionais

- **RF-001:** Requisito responsável pelo cadastramento de alunos, incluindo a validação obrigatória de documentos.

**Cadastro de Aluno (Perfil Criança):**

Nome: String;

Data de Nascimento: Date, (xx/xx/XXXX);

Ano Escolar: Integer¹;

E-mail do Responsável: String;

Histórico Escolar: String; (Link/Caminho do arquivo)²

Laudo Psicológico: String; (Link/Caminho do arquivo)²

Relatório Psicológico de Orientação: String; (Link/Caminho do arquivo)²

Status: Integer;³

**Regra e observações do preenchimento dos campos:**

¹ O campo Ano Escolar deve aceitar obrigatoriamente apenas valores entre 5 e 9 (referentes ao 5º ao 9º ano do Ensino Fundamental II).

² Todo registo do perfil Criança deve estar obrigatoriamente associado ao ID de um perfil Pais responsável.

³ O Status indicará a situação do cadastro (1 - Pendente de Aprovação, 2 - Ativo, 3 - Suspenso, 4 - Cancelado).

**Alteração:**
Será realizada somente por utilizadores autorizados (ex: Pais ou Equipe Multidisciplinar). Vale salientar que em todos os casos deve ser mantido o histórico dos registos, contendo quem realizou a operação juntamente com o que foi realizado, com data e hora.

**Exclusão:**
Não será realizada a exclusão física dos dados; o sistema utilizará o campo Status para inativação (desativado, suspenso, cancelado, ativo), mantendo o histórico de registos.

**Pesquisa:**
Será permitido buscar utilizadores por Nome, CPF, Registro Profissional, Perfil de Acesso, Ano Escolar e Status de Cadastro.

- **RF-002:** Requisito responsável pelo cadastramento de pais, incluindo a validação obrigatória de documentos.

**Cadastro de Responsável (Perfil Pais):**

CPF: String; (xxx.xxx.xxx-xx)¹

Nome Completo: String;

E-mail: String;

Contato: String; (xx)xxxxx-xxxx

Endereço (CEP, Logradouro, Número, Bairro, Município, UF): String;²

**Regra e observações do preenchimento dos campos:**

¹ O CPF do responsável deve possuir algoritmo de validação de dígitos verificadores.

² O CEP deve preencher os dados de endereço automaticamente via consulta a webservice externo.

**Alteração:**
Será realizada somente por utilizadores autorizados . Vale salientar que em todos os casos deve ser mantido o histórico dos registos, contendo quem realizou a operação juntamente com o que foi realizado, com data e hora.

**Exclusão:**
Não será realizada a exclusão física dos dados; o sistema utilizará o campo Status para inativação (desativado, suspenso, cancelado, ativo), mantendo o histórico de registos.

**Pesquisa:**
Será permitido buscar utilizadores por Nome, CPF, Registro Profissional, Perfil de Acesso, Ano Escolar e Status de Cadastro.

- **RF-003:** Requisito responsável pelo cadastramento de equipe multidisciplinar, incluindo a validação obrigatória de documentos.

**Cadastro de Profissional (Perfil Equipe Multidisciplinar):**

Nome Completo: String;

CPF: String; (xxx.xxx.xxx-xx)¹

E-mail Profissional: String;

Registro Profissional / Conselho: String; (Ex: CRP, CRM)²

Especialidade / Função: Integer; (1 - Psicólogo, 2 - Pediatra, 3 - Outros Especialistas)³

Contato: String; (xx)xxxxx-xxxx

Status: Integer;⁴

**Regra e observações do preenchimento dos campos:**

¹ O CPF do profissional deve possuir algoritmo de validação de dígitos verificadores.

² O campo Registro Profissional (CRP, CRM, etc.) é de preenchimento obrigatório para a Equipe Multidisciplinar, garantindo a validação da atuação institucional do especialista.

³ A Especialidade / Função define o direcionamento automático das chamadas e solicitações de atendimento no módulo de suporte.

⁴ O Status indicará a situação do cadastro (1 - Pendente de Aprovação, 2 - Ativo, 3 - Suspenso, 4 - Cancelado).

**Alteração:**
Será realizada somente por utilizadores autorizados. Vale salientar que em todos os casos deve ser mantido o histórico dos registos, contendo quem realizou a operação juntamente com o que foi realizado, com data e hora.

**Exclusão:**
Não será realizada a exclusão física dos dados; o sistema utilizará o campo Status para inativação (desativado, suspenso, cancelado, ativo), mantendo o histórico de registos.

**Pesquisa:**
Será permitido buscar utilizadores por Nome, CPF, Registro Profissional, Perfil de Acesso, Ano Escolar e Status de Cadastro.

- **RF-004:** Requisito responsável pela submissão e análise probatória de documentos para liberação de acesso.

**Dados do Anexo de Documentos:**

ID do Aluno: Integer;

Histórico Escolar: String; (Link/Caminho do arquivo PDF)¹

Laudo Psicológico: String; (Link/Caminho do arquivo PDF)¹

Relatório Psicológico de Orientação: String; (Link/Caminho do arquivo PDF)¹

Data de Submissão: Date;

Parecer da Validação: String;²

**Regras e observações de preenchimento:**

¹ A submissão dos três ficheiros (Histórico Escolar, Laudo e Relatório) é obrigatória para que o cadastro do aluno mude do status Pendente para Em Análise.

² A Equipe Multidisciplinar analisará os documentos e emitirá o parecer de aprovação ou rejeição fundamentada.

**Alteração/Exclusão:**
Não é permitida a alteração/exclusão de documentos após aprovação, salvo mediante solicitação de reavaliação.

**Pesquisa:**
A Equipe Multidisciplinar pode filtrar cadastros pendentes de validação documental.

- **RF-005:** Requisito responsável pela disponibilização e consumo de conteúdos didáticos adaptados.

**Dados do Conteúdo Adaptado:**

Título do Material: String;

Tipo de Mídia: Integer; (1 - Vídeo, 2 - Documento PDF, 3 - Jogo Educativo)

Foco do Conteúdo: Integer; (1 - TDAH, 2 - Discalculia, 3 - Geral)

Ficheiro/URL de Reprodução: String;

Componente de Tecnologia Assistiva Vinculado: String;

**Regras e observações de preenchimento:**

¹ Os conteúdos devem ser exibidos de forma integrada (embedded) na plataforma, evitando redirecionamentos externos.

² O sistema não registrará notas, pontuações de jogos ou relatórios de desempenho associados ao consumo do material por parte do aluno.

**Alteração:**
Será realizada apenas por utilizadores com perfil da Equipa Multidisciplinar ou Administradores autorizados. Permite atualizar o título, ficheiro/URL, foco do conteúdo e componentes assistivos vinculados. Em todos os casos, deve ser mantido o histórico de edições, contendo o autor da modificação, data e hora.

**Exclusão:**
Não será realizada a exclusão física do material do banco de dados. A inativação do conteúdo no catálogo visível para os alunos ocorrerá por meio da alteração do campo Status (de Ativo para Inativo), preservando a integridade dos registos.

**Pesquisa:**
Será permitido buscar conteúdos didáticos por Título, Tipo de Mídia, Foco do Conteúdo (TDAH, Discalculia ou Geral) e Status do Material.

- **RF-006:** Requisito responsável pela disponibilização e personalização de Tecnologias Assistivas.

**Painel de Recursos Assistivos:**

ID do Aluno: Integer;

Modo de Alto Contraste: Boolean;

Ajuste de Fonte e Espaçamento: Integer;

Leitor de Texto por Voz (Text-to-Speech): Boolean;¹

Ferramenta de Suporte Visual/Calculadora para Discalculia: Boolean;¹

**Regras e observações de preenchimento:**

¹ O sistema disponibilizará estritamente os recursos assistivos focados no apoio ao TDAH e à Discalculia.

² As definições personalizadas do utilizador serão guardadas e carregadas automaticamente ao iniciar sessão.

Alteração/Exclusão: As preferências podem ser modificadas a qualquer momento pelo perfil Pais ou Criança.

Pesquisa: Não se aplica.

- **RF-007:** Requisito responsável pelo canal de suporte e comunicação com a Equipa Multidisciplinar.

**Dados do Pedido de Suporte:**

ID do Chamado: Integer;

ID do Remetente (Pais/Aluno): Integer;

Especialidade Alvo: Integer; (1 - Psicologia, 2 - Pediatria, 3 - Outros Especialistas)¹

Assunto: String;

Mensagem/Histórico de Comunicação: String²;

Ficheiro Anexo: String; (Link/Caminho do arquivo)

Status do chamado: Integer; (1 - Aberto, 2 - Em Atendimento, 3 - Concluído)³

**Regras e observações de preenchimento:**

¹ A Especialidade Alvo selecionada define o direcionamento automático da mensagem para a fila de atendimento dos profissionais correspondentes (psicólogos, pediatras, etc.).

² O conteúdo gravado no campo Mensagem / Histórico de Comunicação é de acesso restrito, sendo mantido sob confidencialidade estrita apenas entre o remetente (pais/aluno) e o profissional designado da equipe multidisciplinar.

³ O Status do Chamado controla o fluxo de atendimento, podendo ser alterado exclusivamente pelo profissional encarregado.

**Alteração:**
Permitida apenas para a alteração de status ou inclusão de réplicas/respostas pelos profissionais da equipe multidisciplinar. Todas as interações devem registrar histórico contendo o autor da ação, data e hora.

**Exclusão:**
Não é permitida a exclusão física de mensagens ou chamados finalizados, visando a preservação do histórico de suporte e integridade das orientações prestadas.

**Pesquisa:**
Permitida a busca e filtragem de chamados por Status, Especialidade Alvo, Período (Data) e Aluno vinculado.

- **RF-008:** Requisito responsável pelo agendamento de sessões virtuais de orientação entre os Pais/Alunos e a Equipe Multidisciplinar.

**Dados do Agendamento:**

ID do Agendamento: Integer;

ID do Solicitante (Pais/Alunos): Integer;

ID do Profissional (Equipe Multidisciplinar): Integer¹;

Data e hora da Sessão: DateTime;

Link da Sala Virtual: String;

Status do Agendamento: Integer²; (1 – Solicitado, 2 – Confirmado, 3 – Realizado, 4 – Cancelado)

**Regras e observações de preenchimento:**

¹ O agendamento é direcionado aos profissionais ativos no perfil da equipe multidisciplinar conforme a disponibilidade informada na plataforma.
² As sessões tem caráter estritamente orientativo e de acolhimento. Ao término da reunião, o sistema não emitirá qualquer tipo de relatório de avaliação individual.

**Alteração:**
Permitida a remarcação de data e hora ou alteração de status pelos pais ou pelo profissional responsável até 24 horas antes do horário agendado, registrando histórico com autor, data e hora.

**Exclusão:**
Não haverá exclusão física dos registos de agendamento; o cancelamento será efetuado mediante alteração do campo Status do Agendamento para Cancelado.

**Pesquisa:**
Permitida a filtragem de sessões por Aluno, Profissional, Intervalo de Datas e Status do Agendamento.

- **RF-009:** Requisito responsável pela emissão de notificações e alertas adaptados aos utilizadores.

**Dados da Notificação:**

ID da Notificação: Integer;

ID do Destinatário: Integer;

Categoria do Alerta: Integer; (1 - Novo Conteúdo Adaptado, 2 - Resposta de Suporte, 3 - Lembrete de Agendamento)

Título da Notificação: String;¹

Mensagem Curta: String;¹

Status de Leitura: Boolean; (0 - Não Lida, 1 - Lida)

Data e Hora de Envio: DateTime;

**Regras e observações de preenchimento:**

¹ As notificações enviadas ao perfil Criança devem apresentar interface visual simplificada, ícones claros e texto objetivo, evitando poluição visual e excesso de estímulos para não dispersar alunos com TDAH.

**Alteração:**
Permitida unicamente a alteração do estado do campo Status de Leitura quando o utilizador visualiza a notificação.

**Exclusão:**
Permitida a limpeza/ocultação de notificações antigas do painel do utilizador.

**Pesquisa:**
O utilizador pode filtrar notificações por Categoria e Status de Leitura.

- **RF-010:** Requisito responsável pela disponibilização da Central de Guias e Orientações para Pais.

**Dados do Guia Orientativo:**

ID do Guia: Integer;

Título do Artigo/Guia: String;

Categoria do Tema: Integer; (1 - Estratégias para TDAH na Rotina, 2 - Suporte à Discalculia no Lar, 3 - Direitos e Acessibilidade)

Conteúdo Textual / Ficheiro Anexo: String; (Link/Caminho do PDF ou artigo)

ID do Autor (Profissional): Integer;

Status de Publicação: Integer; (1 - Rascunho, 2 - Publicado, 3 - Arquivado)

**Regras e observações do preenchimento dos campos:**

¹ Módulo de consulta exclusiva para os perfis Pais e Equipe Multidisciplinar, reunindo boas práticas e orientações de apoio pedagógico sem expor dados individuais de alunos.

**Alteração:**
Permitida aos profissionais da equipe multidisciplinar para atualização dos textos ou anexos dos guias.

**Exclusão:**
Não haverá exclusão física; o artigo poderá ser alterado para o status Arquivado.

**Pesquisa:**
Permitida a busca de guias por Título, Categoria do Tema e Autor.

## Requisitos não funcionais

## Fora do escopo desta versão

## Critérios de conclusão
