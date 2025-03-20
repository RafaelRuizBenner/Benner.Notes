# Benner Saúde
### Stakeholders
Existem quatro classes principais de stakeholders:
* **Operadoras** (proprietárias dos planos. *eg Unimed*)
* **Prestadores** (os hospitais em si. *eg Hospital São Caetano*)
* **Beneficiários** (os usuários do plano)
* **Colaborador Benner** (trabalhadores da Benner)
## A Equipe
* **Inovação:** Equipe responsável pela criação de features e melhorias nos sistemas.
* **Sustentação:** Equipe responsável pela correção de problemas nos sistemas.
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
Existem dois tipos de integração front-back com views:
* **builder (10)** (todas as informações)
* **benner (20)** (informações parciais)
* **k9 (40)** (peculiares do cliente; feito pela Benner)
* **k (50)**(peculiares do cliente; feito pelo Cliente)
## AG [Técnico]
### Bases Desenvolvimento Kernel SQL
* **DES_AG_RELANT [hoje: 3.62.0]:** duas versões atrás.
* **DES_AG_SQL [hoje: 3.63.0]:** uma versão atrás.
* **DESENV_AG_SQL [hoje: 3.64.0]:** versão corrente.
### Ferramentas
* **BSVersion:** Versionador com todos artefatos, ddl, tarefas, exe, ...
  * **Bloqueio:** Trava um artefato para alterações.
  * **Checkin:** Desbloqueia um artefato.
  * **Checkout:** Baixa um artefato.
* **SPCOOKER:** Criação de procedure SQL.
* **BUILDER:** Criador de sistemas da Benner.
  * **Handler:** Chave primária.
### Configuração
Primeira vez que instalar uma base, sempre pelo installer do CS \[No Gorilla\]
E só então, Aplicativo *Selecionador Sistema*
* **Runner:** Só abre.
* **Installer:** Atualiza.
### Práticas
* **Nas bases de desenvolvimento:** usar com usuário (NOME | SENHA)
* **Nas bases de suporte:** usar a padrão (sysdba | sup01)
