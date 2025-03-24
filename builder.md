# Builder
## Camadas de Desenvolvimento
* **Tecnologia:** A própria ferramenta do Builder e suas atualizações.
* **Kernel (Saúde):** O domínio padrão a todas soluções.
* **Específico:** Regras de negócio implementadas pela benner à clientes particulares.
* **Cliente:** Regras de negócio implementas pelo próprio cliente *(Builder Cliente)*
## Conceitos Principais
* **Handler:** Chave Primária.
* **Carga:** "Pasta".
* **Tabela:** Com persistência.
* **Tabela Virtual:** Sem persistência *(Uma View)*
* **Meta-tabela:**  Informações do próprio sistema.
* **Entidade Especializada:** Criação das regras de negócio em uma dll C#
  * *Ao habilitar, as macros benner ficam de lado; Porém, as macros benner **do cliente não!***
## Scripts
*Está mais ligado ao Runner, mas há partes importantes de configuração no Builder*
* **Macro de Módulo:** Script VBA executado em botões de um módulo em específico.
* **Macro de Tabela/Carga:** Script VBA executados sobre triggers específicos de alguma tabela.
* **Delphi Especializado:** Scripts visuais em alternativa ao padrão Runner.
* **Procedure Especializado:** Scripts de banco *(eg. SPCOOKER)*
* **C# Especializado:** Scripts C# .NET *(Comum em entidade especializadas)*
