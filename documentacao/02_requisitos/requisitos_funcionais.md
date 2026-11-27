# Requisitos Funcionais — ThreeCode Agenda

## Módulo 01 — Usuários e Acessos

### RF001 — Realizar login

**Descrição:** O sistema deverá permitir que usuários cadastrados acessem a plataforma por meio de e-mail e senha individuais.

**Comportamento esperado:**
- Apresentar uma tela de autenticação.
- Solicitar e-mail e senha.
- Validar as credenciais informadas.
- Permitir o acesso quando as credenciais forem válidas.
- Recusar o acesso quando as credenciais forem inválidas.

**Critérios de aceitação:**
- Usuários cadastrados com credenciais válidas conseguem acessar o sistema.
- Credenciais incorretas não permitem o acesso.
- Senhas não devem ser armazenadas em texto puro.
- Cada usuário deve possuir credenciais individuais.
- Profissionais cadastrados para atendimento não possuem acesso por login.

### RF002 — Encerrar sessão

**Descrição:** O sistema deverá permitir que o usuário encerre sua sessão de acesso de maneira segura.

**Comportamento esperado:**
- Disponibilizar uma opção para encerrar a sessão.
- Invalidar a sessão autenticada do usuário.
- Redirecionar o usuário para a tela de login.
- Exigir uma nova autenticação para acessar novamente.

**Critérios de aceitação:**
- O usuário consegue encerrar sua sessão.
- Após o encerramento, páginas protegidas não podem ser acessadas utilizando a sessão anterior.
- O sistema solicita novas credenciais para permitir outro acesso.

### RF003 — Cadastrar usuários

**Descrição:** O sistema deverá permitir exclusivamente aos administradores o cadastro de novas contas de acesso.

**Comportamento esperado:**
- Disponibilizar uma funcionalidade para cadastrar usuários.
- Solicitar os dados necessários para a criação da conta.
- Permitir a definição de um perfil de acesso.
- Permitir que o administrador defina a senha inicial do usuário.
- Vincular o usuário à empresa e às unidades correspondentes.
- Verificar se o e-mail informado já está cadastrado.
- Impedir que usuários sem perfil de administrador realizem novos cadastros.

**Critérios de aceitação:**
- Somente administradores podem cadastrar novos usuários.
- O administrador consegue definir a senha inicial.
- O sistema não permite e-mails duplicados dentro da mesma empresa.
- Cada usuário possui vínculo com a empresa correspondente.
- Usuários sem autorização não conseguem realizar cadastros.
- As senhas devem ser armazenadas de forma segura, nunca em texto puro.

### RF004 — Alterar a própria senha

**Descrição:** O sistema deverá permitir que cada usuário autenticado altere sua própria senha de acesso.

**Comportamento esperado:**
- Disponibilizar uma funcionalidade para alteração de senha.
- Solicitar a senha atual do usuário.
- Solicitar a nova senha.
- Solicitar a confirmação da nova senha.
- Validar as informações antes de concluir a alteração.

**Critérios de aceitação:**
- Cada usuário consegue alterar sua própria senha.
- A alteração somente é realizada após a validação da senha atual.
- A nova senha e sua confirmação devem ser iguais.
- A nova senha deve ser armazenada de forma segura.
- A senha anterior deixa de ser válida após a alteração.

### RF005 — Gerenciar permissões de usuários

**Descrição:** O sistema deverá permitir que administradores definam e gerenciem as permissões de acesso dos usuários.

**Comportamento esperado:**
- Permitir conceder permissões individuais aos usuários.
- Permitir retirar permissões anteriormente concedidas.
- Permitir criar perfis de permissões reutilizáveis.
- Permitir atribuir perfis aos usuários.
- Permitir personalizar permissões individuais sem alterar o perfil dos demais usuários.
- Controlar o acesso aos módulos do sistema.
- Controlar as ações que cada usuário poderá executar.
- Aplicar as permissões tanto na interface quanto nas operações do backend.

**Critérios de aceitação:**
- Somente administradores podem gerenciar permissões.
- Cada usuário possui permissões correspondentes às suas autorizações.
- Um perfil pode ser atribuído a vários usuários.
- Alterações nas permissões individuais de um funcionário não modificam as permissões dos demais.
- Usuários não conseguem executar ações para as quais não possuem permissão.
- As permissões são respeitadas em todas as operações do sistema.

### RF006 — Consultar usuários cadastrados

**Descrição:** O sistema deverá permitir que usuários autorizados consultem as contas de acesso cadastradas em sua empresa.

**Comportamento esperado:**
- Exibir uma lista de usuários cadastrados.
- Apresentar nome, e-mail, perfil de permissões, unidade vinculada e situação da conta.
- Permitir pesquisar usuários pelo nome ou e-mail.
- Permitir filtrar usuários por perfil de permissões.
- Permitir filtrar usuários por unidade.
- Restringir a consulta aos usuários pertencentes à empresa do usuário autenticado.

**Critérios de aceitação:**
- Administradores conseguem consultar os usuários de sua empresa.
- Usuários sem permissão não conseguem acessar a funcionalidade.
- A pesquisa retorna os usuários correspondentes aos termos informados.
- Os filtros apresentam resultados de acordo com os critérios selecionados.
- Nenhum usuário consegue consultar contas pertencentes a outra empresa.

### RF007 — Editar usuários cadastrados

**Descrição:** O sistema deverá permitir que administradores autorizados editem as informações e configurações das contas de usuários cadastrados.

**Comportamento esperado:**
- Permitir selecionar um usuário na lista de usuários cadastrados.
- Permitir editar os dados cadastrais do usuário.
- Permitir alterar o e-mail de acesso.
- Permitir alterar o perfil de permissões.
- Permitir modificar as permissões individuais.
- Permitir alterar as unidades vinculadas ao usuário.
- Registrar as alterações realizadas e identificar o administrador responsável.

**Critérios de aceitação:**
- Somente administradores autorizados podem editar usuários.
- O sistema valida os dados antes de salvar as alterações.
- O sistema não permite e-mails duplicados dentro da mesma empresa.
- As alterações de permissões são aplicadas corretamente.
- Um administrador não consegue editar usuários pertencentes a outra empresa.
- As alterações ficam registradas para fins de auditoria.

### RF008 — Ativar e desativar usuários

**Descrição:** O sistema deverá permitir que administradores ativem ou desativem contas de usuários sem excluir seus registros do banco de dados.

**Comportamento esperado:**
- Disponibilizar uma opção para desativar usuários.
- Impedir o acesso de usuários com contas inativas.
- Preservar os dados cadastrais e históricos do usuário.
- Permitir a reativação de contas anteriormente desativadas.
- Registrar quem realizou a ativação ou desativação.

**Critérios de aceitação:**
- Somente administradores autorizados podem ativar ou desativar contas.
- Usuários inativos não conseguem realizar login.
- Os registros históricos permanecem disponíveis.
- Contas inativas podem ser reativadas por administradores.
- As alterações de situação ficam registradas para auditoria.

### RF009 — Recuperar senha de acesso

**Descrição:** O sistema deverá permitir que usuários recuperem o acesso à conta por meio de um procedimento seguro de redefinição de senha.

**Comportamento esperado:**
- Disponibilizar a opção "Esqueci minha senha" na tela de login.
- Solicitar o e-mail cadastrado pelo usuário.
- Enviar um link seguro de redefinição de senha quando aplicável.
- Permitir cadastrar uma nova senha por meio do link recebido.
- Utilizar um token único e temporário para validar a solicitação.
- Invalidar o token após sua utilização ou expiração.
- Informar ao usuário que a solicitação foi recebida, sem revelar se o e-mail está cadastrado.

**Critérios de aceitação:**
- O usuário consegue solicitar a recuperação da senha.
- O link de redefinição possui validade limitada, inicialmente definida em 30 minutos.
- O token não pode ser reutilizado.
- Tokens expirados não permitem redefinir a senha.
- A nova senha é armazenada de forma segura.
- O sistema não revela a existência ou inexistência de uma conta por meio das respostas da recuperação.

### RF010 — Consultar dados da própria conta

**Descrição:** O sistema deverá permitir que cada usuário autenticado consulte suas próprias informações cadastrais e configurações de acesso.

**Comportamento esperado:**
- Disponibilizar uma área de perfil pessoal.
- Exibir o nome do usuário.
- Exibir o e-mail cadastrado.
- Exibir o perfil de permissões atribuído.
- Exibir a empresa e as unidades às quais está vinculado.
- Exibir a situação da conta.

**Critérios de aceitação:**
- Cada usuário consegue consultar seus próprios dados.
- O usuário não consegue acessar os dados pessoais de outros funcionários por meio dessa funcionalidade.
- As informações exibidas correspondem à conta autenticada.
- A consulta respeita os limites de acesso da empresa e das unidades.

### RF011 — Editar dados da própria conta

**Descrição:** O sistema deverá permitir que cada usuário autenticado edite determinadas informações pessoais de sua própria conta.

**Comportamento esperado:**
- Permitir alterar o próprio nome.
- Permitir alterar o próprio telefone.
- Validar os dados informados antes de salvar.
- Salvar as alterações no cadastro do usuário.
- Impedir a alteração direta do e-mail de acesso, empresa, unidades e permissões pelo próprio usuário.

**Critérios de aceitação:**
- O usuário consegue editar seu próprio nome e telefone.
- As alterações são salvas corretamente.
- O sistema valida os dados antes de atualizar o cadastro.
- O usuário não consegue alterar informações administrativas ou permissões por essa funcionalidade.
- Um usuário não consegue modificar os dados de outro usuário.

### RF012 — Consultar histórico de atividades

**Descrição:** O sistema deverá registrar as principais atividades realizadas pelos usuários e permitir que administradores e funcionários autorizados consultem esses registros.

**Comportamento esperado:**
- Registrar ações importantes realizadas pelos usuários.
- Identificar o usuário responsável por cada ação.
- Registrar a data e o horário da atividade.
- Identificar o tipo de operação realizada.
- Identificar o registro afetado pela operação.
- Disponibilizar filtros para facilitar a consulta.
- Permitir que administradores e funcionários com permissão específica consultem o histórico.
- Restringir os registros consultados à empresa correspondente.
- Impedir alterações ou exclusões indevidas dos registros de auditoria.

**Critérios de aceitação:**
- As atividades definidas para auditoria são registradas corretamente.
- Cada registro identifica o usuário responsável pela ação.
- Os registros apresentam data e horário.
- Somente usuários autorizados conseguem consultar o histórico.
- Nenhum usuário consegue consultar registros pertencentes a outra empresa.
- Os registros de auditoria não podem ser modificados ou excluídos por usuários comuns.

### RF013 — Visualizar usuários por empresa e unidade

**Descrição:** O sistema deverá permitir que administradores consultem os usuários de acesso vinculados às diferentes unidades de sua empresa, respeitando as permissões.

**Comportamento esperado:**
- Permitir que administradores visualizem os usuários de todas as unidades da própria empresa.
- Disponibilizar filtros para localizar usuários por unidade.
- Permitir consultar os funcionários vinculados a uma unidade específica.
- Restringir a visualização de informações conforme as permissões de cada usuário.
- Impedir a consulta de usuários pertencentes a outras empresas.

**Critérios de aceitação:**
- Administradores conseguem visualizar os usuários de todas as unidades da própria empresa.
- Os filtros por unidade retornam os usuários correspondentes.
- Funcionários comuns visualizam somente as informações autorizadas.
- Nenhum usuário consegue consultar dados de outras empresas sem autorização.

### RF014 — Gerenciar unidades

**Descrição:** O sistema deverá permitir que administradores gerenciem as unidades pertencentes à sua empresa.

**Comportamento esperado:**
- Permitir cadastrar novas unidades.
- Permitir consultar as unidades cadastradas.
- Permitir editar os dados das unidades.
- Permitir ativar e desativar unidades.
- Permitir vincular usuários às unidades correspondentes.
- Manter cada unidade vinculada à empresa responsável.

**Critérios de aceitação:**
- Somente administradores autorizados podem gerenciar unidades.
- Uma empresa pode possuir várias unidades.
- Cada unidade deve estar vinculada a uma única empresa.
- O sistema não permite que uma empresa gerencie unidades pertencentes a outra.
- Unidades desativadas não devem permitir novas operações que dependam de seu funcionamento.
- Os registros históricos das unidades desativadas devem ser preservados.

## Módulo 02 — Cadastro de Profissionais

### RF015 — Cadastrar profissionais

**Descrição:** O sistema deverá permitir que administradores cadastrem profissionais responsáveis pela realização dos atendimentos na clínica, sem necessidade de criar contas de acesso ao sistema.

**Comportamento esperado:**
- Permitir cadastrar profissionais.
- Solicitar os dados necessários para identificação do profissional.
- Permitir informar nome, telefone e especialidade.
- Permitir vincular o profissional a uma ou mais unidades da mesma empresa.
- Permitir configurar uma agenda própria para cada vínculo entre profissional e unidade.
- Permitir associar procedimentos cadastrados à agenda do profissional em cada unidade.
- Permitir que um profissional realize diferentes procedimentos.
- Permitir que os procedimentos disponíveis variem entre as unidades.
- Manter o cadastro do profissional independente das contas de usuários do sistema.

**Critérios de aceitação:**
- Somente administradores autorizados podem cadastrar profissionais.
- Profissionais cadastrados não recebem automaticamente login ou senha.
- Cada profissional possui um cadastro próprio dentro da empresa.
- Um profissional pode estar vinculado a várias unidades da mesma empresa.
- Cada vínculo com uma unidade permite organizar uma agenda independente.
- Cada agenda pode possuir diferentes procedimentos associados.
- O sistema não permite vincular um profissional a unidades pertencentes a outra empresa.

### RF016 — Cadastrar serviços

**Descrição:**

O sistema deverá permitir que o administrador cadastre os serviços oferecidos pela empresa em um catálogo único, que poderá ser utilizado pelas diferentes unidades da clínica.

Cada serviço deverá possuir informações como:

- Nome do serviço;
- Descrição;
- Duração estimada;
- Valor cobrado;
- Status (ativo ou inativo).

**Regras de negócio:**

- Somente administradores poderão cadastrar novos serviços.
- Cada serviço deverá pertencer a uma empresa.
- O mesmo serviço poderá ser disponibilizado em diferentes unidades.
- Um serviço poderá ser associado a diferentes profissionais.
- Serviços inativos não poderão ser utilizados em novos agendamentos.
- A desativação de um serviço não deverá apagar seu histórico de utilização.

### RF017 — Associar serviços aos profissionais por unidade

**Descrição:**

O sistema deverá permitir que o administrador associe os serviços cadastrados no catálogo da empresa aos profissionais habilitados para realizá-los em cada unidade.

Durante essa associação, o administrador poderá definir valores e durações específicos para cada combinação de serviço, profissional e unidade.

**Regras de negócio:**

- Somente administradores poderão realizar essas associações.
- Um profissional poderá estar associado a vários serviços em uma mesma unidade.
- Um serviço poderá estar associado a vários profissionais.
- O mesmo profissional poderá possuir associações diferentes em cada unidade.
- O administrador poderá definir um valor específico para cada associação.
- O administrador poderá definir uma duração específica para cada associação.
- Somente serviços e profissionais pertencentes à mesma empresa poderão ser associados.
- Associações inativas não poderão ser utilizadas em novos agendamentos.
- A desativação de uma associação deverá preservar o histórico de agendamentos anteriores.

### RF018 — Configurar horários de atendimento dos profissionais

**Descrição:**

O sistema deverá permitir que o administrador configure os horários de atendimento de cada profissional, individualmente por unidade.

**Regras de negócio:**

- Somente administradores poderão configurar os horários.
- Cada profissional poderá possuir horários diferentes em cada unidade.
- O administrador poderá definir os dias da semana em que o profissional atende.
- O administrador poderá definir o horário de início e término do expediente em cada dia.
- O sistema deverá permitir intervalos durante o expediente, como horário de almoço.
- O sistema deverá considerar os horários configurados ao verificar a disponibilidade para agendamentos.
- Alterações nos horários não deverão modificar agendamentos já registrados.

### RF019 — Gerenciar bloqueios e exceções de agenda

**Descrição:**

O sistema deverá permitir que o administrador registre períodos em que um profissional não estará disponível para atendimento em determinada unidade.

**Regras de negócio:**

- O administrador poderá cadastrar férias, folgas, feriados, ausências e outros bloqueios.
- Cada bloqueio deverá estar vinculado a um profissional e a uma unidade.
- O administrador poderá definir a data e o horário de início e término do bloqueio.
- O sistema deverá impedir novos agendamentos durante os períodos bloqueados.
- O administrador poderá editar ou cancelar bloqueios cadastrados.
- Bloqueios não deverão apagar ou modificar automaticamente agendamentos existentes.
- O sistema deverá preservar o histórico dos bloqueios registrados.

### RF020 — Consultar horários disponíveis para agendamento

**Descrição:**

O sistema deverá apresentar automaticamente os horários disponíveis de um profissional, considerando a unidade, o serviço e a data selecionados pelo funcionário responsável pelo agendamento.

**Regras de negócio:**

- O funcionário deverá selecionar a unidade, o profissional, o serviço e a data desejada.
- O sistema deverá consultar os horários de atendimento configurados para o profissional naquela unidade.
- O sistema deverá considerar a duração específica do serviço para aquele profissional e unidade.
- O sistema deverá desconsiderar intervalos, bloqueios, ausências e períodos já ocupados por outros agendamentos.
- O sistema deverá apresentar somente horários nos quais o atendimento possa ser realizado integralmente.
- Caso não existam horários disponíveis, o sistema deverá informar ao funcionário.
- A disponibilidade deverá ser atualizada sempre que uma nova consulta for realizada.

### RF021 — Cadastrar agendamentos

**Descrição:**

O sistema deverá permitir que funcionários autorizados realizem agendamentos, vinculando um cliente, um serviço, um profissional, uma unidade e um horário disponível.

**Informações do agendamento:**

- Nome do cliente;
- Telefone do cliente;
- Serviço selecionado;
- Profissional responsável;
- Unidade onde será realizado o atendimento;
- Data do atendimento;
- Horário de início e término;
- Valor do serviço;
- Observações adicionais.

**Regras de negócio:**

- Somente funcionários com permissão poderão cadastrar agendamentos.
- O sistema deverá permitir selecionar apenas profissionais e serviços disponíveis para a unidade escolhida.
- O horário deverá estar disponível no momento da confirmação.
- O sistema deverá impedir agendamentos simultâneos para o mesmo profissional e unidade, quando houver conflito de horário.
- O valor e a duração utilizados deverão ser registrados no agendamento, preservando as informações mesmo que sejam alteradas posteriormente no cadastro do serviço.
- O sistema deverá registrar qual funcionário realizou o agendamento.

### RF022 — Consultar agendamentos

**Descrição:**

O sistema deverá permitir que funcionários autorizados consultem os agendamentos registrados, visualizando os compromissos de cada unidade e profissional.

**Regras de negócio:**

- O sistema deverá oferecer visualização dos agendamentos em formato de calendário.
- Deverá permitir visualizar os compromissos por dia, semana e mês.
- Deverá permitir filtrar agendamentos por unidade, profissional, cliente e data.
- Cada agendamento deverá apresentar nome do cliente, serviço, profissional, horário e status.
- Os funcionários somente poderão consultar informações conforme suas permissões e vínculos com a empresa.
- O sistema deverá permitir identificar horários ocupados e horários disponíveis na agenda.

### RF023 — Gerenciar status dos agendamentos

**Descrição:**

O sistema deverá permitir que funcionários autorizados atualizem o status dos agendamentos, acompanhando o andamento dos atendimentos.

**Status disponíveis:**

- Agendado;
- Confirmado;
- Em atendimento;
- Concluído;
- Cancelado;
- Não compareceu.

**Regras de negócio:**

- Todo novo agendamento deverá iniciar com o status "Agendado".
- Funcionários autorizados poderão atualizar o status conforme suas permissões.
- O sistema deverá registrar quem realizou cada alteração de status e quando ela ocorreu.
- Agendamentos concluídos não poderão voltar automaticamente para etapas anteriores.
- Agendamentos cancelados deverão permanecer registrados no histórico.
- Agendamentos com status "Não compareceu" deverão permanecer disponíveis para consultas e relatórios.
- O sistema deverá permitir filtrar agendamentos por status.

### RF024 — Editar agendamentos

**Descrição:**

O sistema deverá permitir que funcionários autorizados editem informações de agendamentos já registrados.

**Informações que poderão ser alteradas:**

- Nome e telefone do cliente;
- Serviço selecionado;
- Profissional responsável;
- Unidade de atendimento;
- Data e horário;
- Observações.

**Regras de negócio:**

- Somente funcionários com permissão poderão editar agendamentos.
- O sistema deverá verificar a disponibilidade antes de confirmar alterações de data, horário, profissional, serviço ou unidade.
- O sistema deverá impedir conflitos com outros agendamentos.
- O valor e a duração deverão ser atualizados conforme as condições do novo serviço, profissional e unidade, quando houver alteração dessas informações.
- O sistema deverá preservar o histórico das alterações.
- O sistema deverá registrar quem realizou a edição e quando ela ocorreu.
- Agendamentos concluídos ou cancelados não poderão ser editados como agendamentos ativos.

### RF025 — Cancelar agendamentos

**Descrição:**

O sistema deverá permitir que funcionários autorizados cancelem agendamentos, registrando o motivo do cancelamento e preservando o histórico da operação.

**Regras de negócio:**

- Somente funcionários com permissão poderão cancelar agendamentos.
- O sistema deverá permitir informar o motivo do cancelamento.
- O status do agendamento deverá ser alterado para "Cancelado".
- O horário cancelado deverá voltar a ficar disponível para novos agendamentos, desde que não exista outro bloqueio.
- O sistema deverá registrar quem realizou o cancelamento e a data e horário da operação.
- O cancelamento não deverá excluir o agendamento do banco de dados.
- O histórico do agendamento deverá permanecer disponível para consulta.
- Agendamentos concluídos não poderão ser cancelados.

### RF026 — Cadastrar clientes

**Descrição:**

O sistema deverá permitir que funcionários autorizados cadastrem clientes em uma base única da empresa, compartilhada entre todas as suas unidades.

**Informações do cliente:**

- Nome completo;
- Telefone;
- E-mail (opcional);
- CPF (opcional);
- Data de nascimento (opcional);
- Observações.

**Regras de negócio:**

- Somente funcionários com permissão poderão cadastrar clientes.
- Cada cliente deverá estar vinculado a uma empresa.
- Os clientes poderão ser atendidos em diferentes unidades da mesma empresa.
- O sistema deverá permitir pesquisar clientes por nome, telefone ou CPF.
- O sistema deverá verificar possíveis cadastros duplicados.
- O cadastro deverá permitir edição das informações por funcionários autorizados.
- A exclusão do cadastro não deverá apagar automaticamente o histórico de agendamentos.
- Os dados dos clientes deverão ser protegidos conforme as regras de privacidade e proteção de dados aplicáveis.

### RF027 — Consultar clientes e histórico de atendimentos

**Descrição:**

O sistema deverá permitir que funcionários autorizados consultem os clientes cadastrados e visualizem o histórico de seus atendimentos em todas as unidades da empresa.

**Regras de negócio:**

- O sistema deverá apresentar uma lista de clientes cadastrados.
- Deverá permitir pesquisar clientes por nome, telefone ou CPF.
- Deverá permitir consultar os dados cadastrais de cada cliente.
- Deverá apresentar o histórico de agendamentos do cliente.
- O histórico deverá apresentar data, horário, serviço, profissional, unidade, valor e status do atendimento.
- Deverá permitir filtrar o histórico por período, unidade e status.
- Funcionários somente poderão acessar informações conforme suas permissões.
- Os dados deverão permanecer vinculados à empresa correspondente, sem permitir acesso por outras empresas.

### RF028 — Editar cadastro de clientes

**Descrição:**

O sistema deverá permitir que funcionários autorizados editem as informações cadastrais dos clientes registrados na empresa.

**Informações que poderão ser alteradas:**

- Nome completo;
- Telefone;
- E-mail;
- CPF;
- Data de nascimento;
- Observações cadastrais.

**Regras de negócio:**

- Somente funcionários com permissão poderão editar os dados.
- O sistema deverá validar as informações antes de salvar as alterações.
- O sistema deverá verificar possíveis duplicidades de CPF e outros dados identificadores.
- As alterações deverão ser registradas no histórico de atividades.
- O sistema deverá identificar quem realizou a alteração e quando ela ocorreu.
- A edição cadastral não deverá modificar os dados históricos dos agendamentos anteriores.
- Os dados deverão permanecer vinculados à empresa correspondente.

### RF029 — Consultar disponibilidade geral da unidade

**Descrição:**

O sistema deverá permitir que funcionários autorizados visualizem a disponibilidade geral dos profissionais de uma unidade, apresentando os horários ocupados e livres em uma única tela.

**Regras de negócio:**

- O sistema deverá apresentar os profissionais vinculados à unidade selecionada.
- Deverá permitir visualizar a agenda por dia.
- Deverá apresentar os horários ocupados e disponíveis de cada profissional.
- Deverá identificar os serviços associados aos agendamentos existentes.
- Deverá considerar os horários de atendimento, intervalos, bloqueios e agendamentos registrados.
- Deverá permitir filtrar a visualização por profissional.
- O acesso deverá respeitar as permissões do funcionário.
- A visualização deverá considerar exclusivamente os dados da empresa e unidade selecionadas.

### RF030 — Registrar chegada do cliente

**Descrição:**

O sistema deverá permitir que funcionários autorizados registrem a chegada do cliente à unidade, indicando que ele está aguardando atendimento.

**Regras de negócio:**

- Somente funcionários com permissão poderão registrar a chegada.
- O registro deverá estar vinculado a um agendamento existente.
- O sistema deverá registrar a data e o horário da chegada.
- O agendamento deverá receber o status "Aguardando atendimento".
- O sistema deverá identificar o funcionário responsável pelo registro.
- A chegada deverá ser registrada na unidade correspondente ao agendamento.
- O registro deverá permanecer disponível no histórico de atividades.

### RF031 — Integrar ferramenta de Business Intelligence

**Descrição:**

O sistema deverá permitir a integração com o Microsoft Power BI para disponibilizar dashboards e relatórios gerenciais, utilizando os dados operacionais do ThreeCode Agenda.

**Regras de negócio:**

- O Power BI será responsável pela apresentação dos dashboards e análises gerenciais.
- O ThreeCode Agenda continuará responsável pelo cadastro, processamento e armazenamento dos dados.
- Os relatórios deverão respeitar o isolamento de dados entre empresas e unidades.
- O acesso aos indicadores deverá respeitar as permissões dos usuários.
- A integração deverá proteger os dados pessoais e empresariais.
- O sistema deverá permitir a atualização dos dados utilizados nos relatórios.
- A arquitetura deverá considerar a instalação do sistema em servidores próprios dos clientes.
- A modalidade de integração, atualização e disponibilização dos dashboards será definida na etapa de arquitetura técnica, considerando custos, licenciamento e segurança.

### RF032 — Gerenciar configurações da empresa

**Descrição:**

O sistema deverá permitir que administradores gerenciem as informações cadastrais e visuais da empresa, possibilitando a personalização de sua identificação dentro do ThreeCode Agenda.

**Informações da empresa:**

- Nome da empresa;
- Logotipo;
- Telefone de contato;
- E-mail de contato;
- Endereço;
- Informações complementares.

**Regras de negócio:**

- Somente administradores poderão alterar as configurações da empresa.
- Cada empresa deverá possuir suas próprias configurações.
- O sistema deverá permitir cadastrar e atualizar o logotipo.
- As informações deverão ser exibidas na identificação da empresa dentro do sistema.
- As alterações deverão ser registradas no histórico de atividades.
- Uma empresa não poderá visualizar ou modificar as configurações de outra empresa.
- As alterações não deverão modificar registros históricos de agendamentos.

### RF033 — Configurar dados das unidades

**Descrição:**

O sistema deverá permitir que administradores configurem e atualizem as informações específicas de cada unidade vinculada à empresa.

**Informações da unidade:**

- Nome da unidade;
- Telefone de contato;
- E-mail de contato;
- Endereço completo;
- Horários gerais de funcionamento;
- Informações complementares.

**Regras de negócio:**

- Somente administradores poderão gerenciar essas informações.
- Cada unidade deverá estar vinculada a uma empresa.
- Cada unidade deverá possuir suas próprias informações cadastrais.
- O sistema deverá permitir atualizar os dados da unidade.
- Os horários gerais de funcionamento deverão servir como referência para a operação da unidade.
- As alterações deverão ser registradas no histórico de atividades.
- A edição das informações não deverá modificar registros históricos de agendamentos.

### RF034 — Exportar dados e relatórios

**Descrição:**

O sistema deverá permitir que funcionários autorizados exportem informações e relatórios em formatos Excel (.xlsx) e PDF (.pdf), facilitando o armazenamento, compartilhamento e análise dos dados da empresa.

**Informações disponíveis para exportação:**

- Agendamentos;
- Cadastro de clientes;
- Relação de profissionais;
- Cadastro de serviços;
- Histórico de atendimentos;
- Relatórios por unidade;
- Relatórios por período;
- Histórico de cancelamentos e não comparecimentos.

**Regras de negócio:**

- A exportação deverá respeitar as permissões do usuário.
- O sistema deverá permitir selecionar os dados que serão exportados.
- Deverá permitir aplicar filtros por período, unidade, profissional e status, conforme o tipo de relatório.
- Os arquivos deverão ser disponibilizados nos formatos Excel e PDF.
- Os dados exportados deverão respeitar o isolamento entre empresas.
- O sistema deverá evitar a exposição de informações pessoais desnecessárias.
- As exportações deverão ser registradas no histórico de atividades.

### RF035 — Gerenciar backups e restauração de dados

**Descrição:**

O sistema deverá oferecer mecanismos de proteção dos dados por meio de backups automáticos e recursos de restauração, permitindo recuperar informações em situações de falhas, perdas ou problemas técnicos.

**Regras de negócio:**

- O sistema deverá permitir configurar backups automáticos.
- O administrador deverá poder consultar a data e o horário dos últimos backups realizados.
- Os backups deverão contemplar os dados necessários para a recuperação do sistema.
- As cópias de segurança deverão ser armazenadas de forma protegida e, sempre que possível, em local separado do servidor principal.
- Os arquivos de backup deverão possuir mecanismos de proteção contra acesso não autorizado.
- O sistema deverá permitir a restauração dos dados a partir de um backup válido, mediante procedimento autorizado.
- A restauração deverá preservar a integridade e a consistência dos dados.
- O sistema deverá registrar as operações de backup e restauração.
- Deverão existir procedimentos para verificar periodicamente se os backups podem ser restaurados corretamente.
- A política de retenção e a frequência dos backups serão definidas na etapa de arquitetura técnica.

### RF036 — Garantir isolamento e proteção dos dados entre empresas

**Descrição:**

O sistema deverá garantir que cada empresa tenha acesso exclusivamente aos seus próprios dados, impedindo consultas, alterações, exclusões ou operações não autorizadas sobre informações pertencentes a outras empresas.

**Regras de negócio:**

- Cada registro deverá possuir vínculo com a empresa correspondente, conforme sua natureza.
- O backend deverá validar a empresa à qual o usuário autenticado está vinculado.
- Todas as operações de consulta, cadastro, edição e exclusão deverão respeitar o isolamento entre empresas.
- O sistema não deverá confiar exclusivamente nos identificadores enviados pelo frontend.
- O acesso a registros de outras empresas deverá ser bloqueado, mesmo quando o usuário tentar manipular URLs, parâmetros ou requisições.
- O isolamento deverá ser aplicado também às unidades, profissionais, serviços, clientes, agendamentos e demais informações.
- As consultas ao banco de dados deverão respeitar o contexto da empresa autenticada.
- Os relatórios e arquivos exportados deverão respeitar o isolamento entre empresas.
- O sistema deverá registrar tentativas relevantes de acesso não autorizado.
- Deverão ser realizados testes de segurança para verificar o isolamento entre empresas.

### RF037 — Consultar estado de funcionamento do sistema

**Descrição:**

O sistema deverá disponibilizar informações sobre seu estado de funcionamento, permitindo que administradores autorizados consultem a disponibilidade dos principais serviços da aplicação.

**Informações apresentadas:**

- Estado de funcionamento da aplicação;
- Estado da conexão com o banco de dados;
- Data e horário da última verificação;
- Indicação de manutenção programada ou em andamento, quando aplicável.

**Regras de negócio:**

- Administradores autorizados poderão consultar o estado de funcionamento do sistema.
- As verificações deverão identificar falhas de comunicação com os principais componentes da aplicação.
- O sistema deverá apresentar informações de maneira clara, sem expor detalhes técnicos sensíveis.
- Credenciais, informações internas do servidor e dados de outras empresas não poderão ser exibidos.
- O acesso a informações técnicas detalhadas deverá ser restrito à equipe responsável pela manutenção.
- O sistema deverá permitir identificar períodos de manutenção programada.

### RF038 — Registrar e consultar erros técnicos

**Descrição:**

O sistema deverá possuir um mecanismo de registro de erros e ocorrências técnicas, permitindo que a equipe responsável pela manutenção identifique, consulte e investigue falhas durante a execução da aplicação.

**Informações registradas:**

- Identificação do erro;
- Data e horário da ocorrência;
- Tipo ou categoria do erro;
- Componente da aplicação envolvido;
- Descrição técnica da ocorrência;
- Identificação do usuário relacionado, quando aplicável;
- Empresa relacionada à ocorrência, quando aplicável.

**Regras de negócio:**

- O sistema deverá registrar automaticamente erros e falhas relevantes.
- Os registros deverão permitir identificar a origem e o momento da ocorrência.
- O acesso aos registros técnicos deverá ser restrito à equipe autorizada para manutenção.
- Os registros não deverão expor senhas, tokens, credenciais ou informações pessoais desnecessárias.
- Os registros deverão possuir mecanismos de proteção contra alterações e exclusões não autorizadas.
- O sistema deverá permitir pesquisar e filtrar ocorrências por período, categoria e componente.
- Os registros deverão auxiliar na investigação e correção de problemas técnicos.
- As falhas técnicas não deverão expor informações internas da aplicação aos usuários comuns.

### RF039 — Controlar versões e atualizações do sistema

**Descrição:**

O sistema deverá disponibilizar informações sobre sua versão instalada e permitir o gerenciamento controlado de atualizações, garantindo que as instalações dos clientes possam receber correções, melhorias e novas funcionalidades.

**Informações apresentadas:**

- Número da versão instalada;
- Data da instalação ou última atualização;
- Histórico de versões;
- Descrição das alterações realizadas em cada versão;
- Indicação de atualizações disponíveis, quando aplicável.

**Regras de negócio:**

- O sistema deverá identificar sua versão atual.
- As atualizações deverão possuir identificação própria de versão.
- A equipe responsável pela manutenção deverá controlar a disponibilização de novas versões.
- O sistema deverá permitir consultar o histórico de atualizações realizadas.
- As atualizações deverão preservar os dados existentes.
- Deverão existir procedimentos de backup antes de atualizações que possam afetar os dados.
- O processo de atualização deverá considerar a compatibilidade entre a aplicação e a estrutura do banco de dados.
- A instalação de atualizações deverá ser realizada por procedimento autorizado.
- O sistema deverá registrar informações sobre atualizações realizadas e possíveis falhas durante o processo.

### RF040 — Gerenciar solicitações de suporte técnico

**Descrição:**

O sistema deverá disponibilizar um módulo para que as empresas clientes registrem solicitações de suporte técnico direcionadas à equipe da ThreeCode, permitindo acompanhar o andamento e a resolução dos chamados.

**Informações da solicitação:**

- Título da solicitação;
- Descrição do problema ou dúvida;
- Categoria da solicitação;
- Data e horário de abertura;
- Usuário responsável pela abertura;
- Status da solicitação;
- Resposta ou orientação da equipe de suporte.

**Regras de negócio:**

- Usuários autorizados poderão abrir solicitações de suporte.
- Cada solicitação deverá estar vinculada à empresa que a registrou.
- O sistema deverá permitir consultar as solicitações abertas pela própria empresa.
- A equipe responsável pela ThreeCode deverá possuir acesso administrativo aos chamados.
- O sistema deverá permitir atualizar o status das solicitações.
- Os chamados poderão possuir os status: Aberto, Em atendimento, Aguardando resposta do cliente e Resolvido.
- O sistema deverá preservar o histórico de interações e alterações de cada solicitação.
- Usuários de uma empresa não poderão visualizar solicitações de outras empresas.
- O acesso administrativo da ThreeCode deverá ser separado das contas comuns das empresas clientes.

### RF041 — Gerenciar painel administrativo da ThreeCode

**Descrição:**

O sistema deverá possuir um ambiente administrativo separado da aplicação utilizada pelas empresas clientes, destinado exclusivamente à equipe autorizada da ThreeCode para gerenciamento e manutenção do produto.

**Funcionalidades:**

- Consultar empresas clientes cadastradas;
- Consultar informações das instalações e versões utilizadas;
- Gerenciar solicitações de suporte técnico;
- Consultar registros de erros técnicos;
- Gerenciar atualizações do sistema;
- Consultar informações operacionais necessárias à manutenção do produto.

**Regras de negócio:**

- O painel deverá possuir autenticação própria.
- Somente integrantes autorizados da equipe ThreeCode poderão acessar o ambiente.
- As permissões deverão ser específicas para as atividades administrativas.
- O acesso deverá possuir mecanismos de auditoria.
- O painel deverá respeitar o isolamento dos dados das empresas clientes.
- O acesso administrativo não deverá conceder automaticamente acesso irrestrito aos dados pessoais dos clientes.
- As operações administrativas deverão ser registradas.
- O ambiente administrativo deverá possuir controles de segurança independentes dos usuários das clínicas.

### RF042 — Gerenciar usuários internos da ThreeCode

**Descrição:**

O painel administrativo deverá permitir o cadastro e gerenciamento dos integrantes da equipe ThreeCode, possibilitando controlar o acesso às funcionalidades administrativas do produto.

**Informações do usuário:**

- Nome completo;
- E-mail de acesso;
- Senha inicial;
- Perfil administrativo;
- Status da conta (ativo ou inativo).

**Regras de negócio:**

- Somente usuários internos com permissão administrativa poderão cadastrar novos integrantes.
- Cada integrante deverá possuir uma conta individual.
- O sistema deverá permitir criar perfis administrativos com diferentes conjuntos de permissões.
- As permissões poderão determinar acesso ao suporte, gerenciamento de empresas, atualizações, manutenção e registros técnicos.
- O sistema deverá permitir ativar e desativar contas.
- Usuários inativos não poderão acessar o painel administrativo.
- Cada usuário poderá alterar sua própria senha.
- O sistema deverá registrar atividades administrativas importantes.
- As contas internas da ThreeCode deverão ser independentes das contas utilizadas pelas empresas clientes.
- O acesso deverá respeitar o princípio do menor privilégio, concedendo somente as permissões necessárias para cada função.

### RF043 — Gerenciar histórico de manutenção por empresa

**Descrição:**  
O sistema deverá permitir que a equipe autorizada da ThreeCode registre e consulte o histórico de manutenções e intervenções técnicas realizadas em cada empresa cliente.

**Funcionalidades:**
- Registrar manutenções realizadas em cada empresa.
- Identificar a empresa e a instalação relacionada à intervenção.
- Registrar o tipo de intervenção, como atualização, correção, manutenção preventiva ou solução de problemas.
- Registrar a descrição do serviço realizado.
- Registrar o responsável pela intervenção.
- Registrar data e horário de início e conclusão, quando aplicável.
- Consultar o histórico de intervenções por empresa.
- Permitir filtros por período, tipo de manutenção e responsável.
- Manter o histórico disponível mesmo após atualizações ou mudanças na instalação.
- Restringir o acesso aos integrantes da ThreeCode que possuam autorização.
- Registrar as operações de criação e alteração dos registros para fins de auditoria.

**Regras de negócio:**
- Cada intervenção deverá estar vinculada à empresa correspondente.
- Somente integrantes autorizados da ThreeCode poderão registrar ou consultar manutenções.
- Os registros deverão preservar informações suficientes para rastrear o que foi realizado e por quem.
- O histórico não deverá ser excluído por usuários comuns.
- O acesso a esse histórico deverá respeitar as permissões do painel administrativo da ThreeCode.

### RF044 — Gerenciar configurações de segurança da instalação

**Descrição:**  
O sistema deverá permitir que integrantes autorizados da ThreeCode gerenciem as configurações de segurança de cada instalação do ThreeCode Agenda.

**Funcionalidades:**
- Configurar o tempo máximo de inatividade antes do encerramento automático de uma sessão.
- Definir critérios mínimos para criação de senhas, como tamanho mínimo e requisitos de complexidade.
- Configurar limites de tentativas consecutivas de login.
- Definir o período de bloqueio temporário após tentativas excessivas de autenticação.
- Consultar as configurações de segurança atualmente aplicadas à instalação.
- Registrar alterações realizadas nas configurações, identificando o responsável, a data e o horário.

**Regras de negócio:**
- Somente integrantes da ThreeCode com permissão específica poderão alterar essas configurações.
- As configurações deverão respeitar os padrões mínimos de segurança definidos pela ThreeCode.
- O sistema não deverá permitir configurações que comprometam os mecanismos essenciais de proteção.
- Alterações deverão ser registradas para auditoria.
- As configurações deverão ser aplicadas no backend, não dependendo exclusivamente do frontend.
- Os parâmetros de segurança deverão ser considerados em todas as contas de usuários da instalação.
- As configurações de uma empresa não poderão interferir nas instalações de outras empresas.

