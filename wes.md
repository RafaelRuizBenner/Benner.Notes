# WES
## Conceitos Básicos
* **Página:** Corpo do conteúdo.
* **Widget:** Componente.
  * **Visão:** Grid (*"lista"*), forms, etc.
  * **Menu:** Navegação (*"ir até uma certa Página ou Visão"*)
* **Pemissões:**
  * **Papéis:** *Quem?*
  * **Tarefas:** *O que?*
* **Visões de Dados:** Filtro / Composição de dados para alimentar um widget
  * No WES, as visões de dados são feitas pelos Consolidados *(Camada -1; União das camadas de builder, benner, e específico)*
* **Geração:**
  * **Código autogerado:** localizado no folder 'a'
  * **Código especializado:** localizado no folder 'e'
## Práticas
* *Sempre que algo do builder for alterado, 'limpar caches' no WES também*
* *Sempre que criar uma nova página auto-gerada, 'gerar páginas' no WES*
