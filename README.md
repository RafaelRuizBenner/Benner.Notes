# Benner Saúde
### Stakeholders
Existem quatro classes principais de stakeholders:
* **Operadoras** (proprietárias dos planos. *eg Unimed*)
* **Prestadores** (os hospitais em si. *eg Hospital São Caetano*)
* **Beneficiários** (os usuários do plano)
* **Colaborador Benner**
## A Equipe
* **Desenvolvimento:** Equipe responsável pela criação de features e melhorias nos sistemas existentes.
* **Sustentação:** Equipe responsável pela correção de problemas nos sistemas existentes.
* **Inovação:** Equipe responsável pela criação de novos sistemas.
* **QA (Qualidade):** Equipe responsável por teste e documentação da implementação.
* **Suporte:** Equipe responsável por dar auxílio às *Operadoras*.
* **Central de Atendimento:** Equipe responsável por dar auxílio aos *Prestadores* e *Beneficiários*.
* **\*BTO:** Colaboradores das *Operadoras*. Operam nos processos de pagamento para prestadoras, reembolso, etc.
## Aplicações
* **AG [Auto-Gestão]:** Aplicativo Core; Gestão automatizada de plano e prestação de saúde.
* **Portal / Mobile:** Aplicações para os *Beneficiários* (Web e Mobile, respectivamente). Funções como visualizar consultas marcadas, acompanhar pagamentos, entre outras.
* **Conecta:** Aplicação para os *Prestadores*. Funções como enviar contas, conceder autorizações, entre outras.
* **siscon:** Aplicação para os *Colaboradores Benner*. Funções como lançar horas, pedidos de alteração nos sistemas, entre outras.
* **Lean:** Aplicação para as *Operadoras*. Função de **Regulação** dos procedimentos médicos.
## Termos
### Implementações
Existem três níveis de implementações no sistema AG:
* **kernel** (para todos os clientes [*Operadoras*])
* **k9** (específico a um cliente; feito pela Benner)
* **k** (específico a um cliente; feito pelo Cliente)
### Views
Existem quatro tipos de integração front-back com views:
* **builder (10)** (todas as informações)
* **benner (20)** (informações parciais)
* **k9 (40)** (peculiares do cliente; feito pela Benner)
* **k (50)** (peculiares do cliente; feito pelo Cliente)
## AG [Técnico]
### Bases Desenvolvimento Kernel SQL
* **DES_AG_RELANT [hoje: 3.62.0]:** duas versões atrás.
* **DES_AG_SQL [hoje: 3.63.0]:** uma versão atrás.
* **DESENV_AG_SQL [hoje: 3.64.0]:** versão corrente.
### Ferramentas
* **BServer:** Controlador básico dos dados em sistemas benners; Aberto a multi-banco, como Oracle e SQL.
  * **Server Manager:** Interface visual do BServer.
* **BSVersion:** Versionador com todos artefatos, ddl, tarefas, exe, ...
  * **Bloqueio:** Trava um artefato para alterações.
  * **Checkin:** Desbloqueia um artefato.
  * **Checkout:** Baixa um artefato.
* **BProvider:** Host do backend.
* **SPCOOKER:** Criação de procedure SQL.
* **BUILDER:** Criador da estrutura (tabela e metadados) para Sistemas Benner.
  * **Handler:** Chave primária (todos índices e relações são automatizadas pelo Builder).
* **RUNNER:** Criador de aplicações desktop.
* **WES:** Criador de aplicações web.
  * *Diferente do Runner, o Wes possui BProvider (para formulários e algumas persistências, fica acoplado)*
* **BTL:** Processamento de Messageria em segundo plano.
  * *O WES se utiliza dele para reduzir a carga de requisições, enviando para o BTL rodá-las em segundo plano*
* **AOL \[Usado no Server Manager\]:** Atualização de sistemas benner (para desenvolvimento, mas principalmente produção)
  * *Por meio de ddls, permite atualizações customizadas para cada cliente*
* **Integrator:** Garante a integridade das tabelas, tal qual a permissão de usuários a certas funções administrativas.
  * *Suas mensagens estão ligadas à serviços (Inclusão, Alteração, Exclusão, Validação, ...)*
### Configuração
Primeira vez que instalar uma base, sempre pelo installer do CS \[No Gorilla\]
E só então, o Aplicativo *Selecionador Sistema*
* **Runner:** Só executa o sistema.
* **Installer:** Atualiza e executa.
### Práticas
* **Nas bases de desenvolvimento:** usar com usuário (NOME | SENHA)
* **Nas bases de suporte:** usar a padrão (sysdba | sup01)
