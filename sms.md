# Fluxo SMS
1. Cliente relata problema em uma SMS no Benner siscon.
2. A Equipe do suporte avalia o protocolo como uma **Correção**, **Nova Implementação**, ou **Problema de Parametrização**
  1. Correções são enviadas à Equipe de Sustentação.
  2. Nova Implementação são enviadas à Análise da Equipe de Desenvolvimento.
  3. Problemas de Parametrização são resolvidos diretamente.
## Correção
1. A SMS é posta pela equipe no Planner *AG - Sustentação*
2. Um desenvolvedor assume a SMS.
   * No siscon, registra-se Recurso como seu Usuário, e Situação como *Programando*
3. Após terminar de desenvolver, as alterações são enviadas para revisão de código
   * Abrindo um pull request na branch criada
4. Em aprovação da revisão, segue-se para a **re-integração**, **testes**, **documentação**, e **homologação**.
5. Caso algum problema de desenvolvimento seja indentificado nas etapas seguintes, retorna para uma eventual correção.
