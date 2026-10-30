# Entrega 6 — Prototipação em papel

**Data:** 10/09/2026 
**Status:** 🟨 em andamento  
**Responsabilidade:** 1 solução integrada por equipe

## Objetivo da atividade

Externalizar rapidamente ideias de interação em baixa fidelidade para explorar alternativas antes de investir em detalhes visuais. O valor da atividade está no **ciclo construir → simular → observar → revisar**, não na beleza do desenho.

## 1. Escopo do protótipo

**Personas:** Camila Rocha (P01 — Analista/Administradora)
**Cenários/tarefas cobertos:** Cenário C01 / Tarefas T01 (HTA) e T03 (CTT) — Triagem de atendimentos, filtragem por nível de risco, navegação mestre-detalhe e auditoria de explicabilidade jurídica (RAG / Art. 147-B). 
**Objetivos principais:** 

- Permitir à analista obter uma visão agregada instantânea do volume de casos e ocorrências de alto risco via cartões KPI.

- Oferecer filtros rápidos por nível de risco (ALTO, MÉDIO, BAIXO) e busca direcionada para triagem eficiente.

- Preservar o sigilo dos dados em ambiente compartilhado através da exibição de IDs mascarados (#C001).

- Garantir acesso em um único clique para o painel de auditoria do RAG.

## 1.1 Possíveis famílias de interface

Escolha apenas o que for coerente com tarefas e cenários. Para TCCs técnicos, o protótipo pode explorar:

- **dashboard** para monitoramento e tomada de decisão;
- **configuração/parametrização** para preparar algoritmo/modelo/processo;
- **entrada/seleção de dados** com validação;
- **acompanhamento de execução** com progresso, fila, cancelamento e recuperação;
- **relatório/resultados** com explicação, gráficos e exportação;
- **histórico** com busca, filtros, ordenação e detalhes;
- **comparação** entre execuções, versões, algoritmos ou períodos;
- **administração** de usuários, papéis, permissões ou entidades do domínio;
- **auditoria/logs** traduzidos para o perfil;
- **alertas/ocorrências** com ação de resposta.

> Não desenhe todas essas telas por obrigação. O objetivo da baixa fidelidade é experimentar a **estrutura da interação** necessária para as tarefas priorizadas.

## 2. Fluxos escolhidos

| Fluxo | Tarefa/objetivo | Por que foi priorizado |
|---|---|---|
| PF01 | Visualizar métricas globais, filtrar atendimentos de Risco Alto e iniciar auditoria do RAG (T01/T03) | É a porta de entrada da analista Camila para gerenciar o volume diário de conversas, identificar emergências e validar as justificativas geradas pela IA. |

## 3. Telas e estados

- Numere as telas/estados (`P01`, `P02`...).
- Indique controles que mudam o estado.
- Mostre pelo menos caminhos principais e estados de erro/retorno relevantes.

- ### Tela P01 — Painel Administrativo / Histórico e Visão Geral
Interface única em folha quadriculada contemplando:
* **Cabeçalho:** Logótipo do sistema, título da tela ("Visão geral"), navegação rápida (Casos, Análises, Relatórios, Config) e perfil.
* **Métricas KPI:** 3 cartões superiores para resumo estatístico rápido do período.
* **Filtros e Busca:** isolamento por risco (ALTO, MÉDIO, BAIXO) e campo de texto `BUSCAR CASOS...`.
* **Tabela Principal:** Listagem com colunas para ID do Caso (#C001 a #C004), Data, Nível de Risco, Categoria Principal, Mensagens Processadas e Botão `AUDITAR`.
* **Rodapé:** Indicador de paginação e total de registros exibidos ("Mostrando 4 de 130 casos").

![Protótipo](../assets/06_prototipos/prototipo_fluxo_01.svg)

## 4. Simulação / walkthrough

Realize uma simulação com uma pessoa que não participou da elaboração dessas telas. Um colega pode ser usado **para essa iteração formativa**, mas isso não substitui os participantes finais da Entrega 14.

| Observação | Tela/ação | Evidência | Consequência para o design |
|---|---|---|---|
| A métrica agregada no topo permitiu identificar o volume crítico antes da leitura da tabela. | Tela P01 / Leitura inicial | Participante: "Consigo ver direto que 28 casos precisam de atenção prioritária sem rolar a página." | Validou a presença dos cards de KPI no topo da página. |
| O filtro de nível de risco foi acionado como primeiro passo interativo. | Tela P01 / Filtragem | O participante clicou diretamente no botão ALTO para isolar os casos graves. | Manter os botões de filtro em posição de destaque logo acima da tabela. |
| A coluna de mensagens processadas (ex: 28/30) ajudou a entender a severidade. | Tela P01 / Leitura da tabela | Participante: "Saber que 28 de 30 mensagens contêm indícios me faz escolher o #C001 primeiro." | Mantida a exibição da proporção de mensagens no nível mestre da tabela. |

## 5. Alterações após a simulação

| Antes | Problema | Depois | Justificativa |
|---|---|---|---|
| Exibição isolada da categoria principal sem contexto de proporção. | {O analista não sabia quantas mensagens daquela conversa continham abusos antes de abrir o detalhe. | Adicionada a coluna MENSAGENS PROCESSADAS (ex: 28/30, 15/18) na Tabela P01. | Oferece um indicador claro da intensidade do comportamento abusivo diretamente na triagem mestre. |
| Nomes ou dados de contato visíveis na tabela. | Risco de exposição indevida de dados sensíveis em telas de escritório. | Adoção estrita de IDs mascarados (#C001, #C002). | Garante a conformidade com diretrizes de privacidade e proteção de dados da vítima. |

## Checklist

- [X] O protótipo cobre tarefas relevantes da Entrega 5.
- [X] Cada tela/estado pode ser justificado por uma tarefa, decisão ou informação necessária.
- [X] O projeto não criou dashboard/CRUD/login apenas para parecer “completo”.
- [ ] Telas/estados estão numerados e navegáveis na documentação.
- [X] Há pelo menos uma simulação/walkthrough documentado.
- [X] Críticas não foram apenas listadas: geraram decisão de revisão.
- [X] O protótipo continua em baixa fidelidade; detalhes visuais não mascaram problemas de fluxo.
