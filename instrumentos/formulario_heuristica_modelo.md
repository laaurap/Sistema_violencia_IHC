# Formulário de avaliação heurística — modelo

**Avaliador:** Laura de Souza Parente (`22.123.033-7`)  
**Versão:** Protótipo navegável de alta fidelidade no Figma — Entrega 11   
**Data:** 15/11/2026  
**Estados especiais examinados:** vazio (`F01E` — busca sem resultados `#C999`) / filtro sem resultado / confirmação (`F04` — banner verde de aprovação e reclassificação) / carregamento e processamento de laudo (`F07` — preview de relatório) / controle de acesso e anonimização (`#ID` sem nome civil)

## Cobertura

| H | Heurística | Fluxos/telas examinados | Violação? | IDs |
|---:|---|---|---|---|
| 1 | Visibilidade do status do sistema | Visão Geral (`F01`), Filtro Alto (`F02A`), Auditoria (`F03`), Confirmação (`F04`), Análises (`F06`) | **sim** | `V01` (`HC02`) |
| 2 | Compatibilidade sistema–mundo real | Auditoria Split-Screen (`F03`), Relatórios (`F07`), Análises (`F06`) | **não** | — |
| 3 | Controle e liberdade do usuário | Estado Vazio (`F01E`), Modal de Reclassificação (`F03R`), Barra Lateral (`F01`–`F08`) | **não** | — |
| 4 | Consistência e padrões | Todas as telas (`F01`–`F08`), botões de ação, badges de risco e exportação (`F07`) | **sim** | `V02` (`HC03`) |
| 5 | Prevenção de erros | Modal de Reclassificação (`F03R` — justificativa obrigatória), Estado Vazio (`F01E`) | **não** | — |
| 6 | Reconhecimento em vez de memorização | Auditoria Split-Screen (`F03`), Listagem de Casos (`F01`), Filtros rápidos | **não** | — |
| 7 | Flexibilidade e eficiência de uso | Visão Geral (`F01` — cards KPI superiores e filtros rápidos), Busca por `#ID` | **sim** | `V03` (`HC04`) |
| 8 | Estética e design minimalista | Visão Geral (`F01`), Auditoria (`F03`), Análises (`F06`), Relatórios (`F07`) | **não** | — |
| 9 | Reconhecer, diagnosticar e recuperar erros | Estado Vazio / Busca sem resultados (`F01E` — código `#C999`) | **não** | — |
| 10 | Ajuda e documentação | Análises Estatísticas (`F06`), Auditoria (`F03` — escore de confiança da IA `94,2%`) | **sim** | `V04` (`HC01`) |

## Problemas

| ID | H | Tela/estado | Ação/condição | Problema | Consequência | Evidência | Severidade 0–4 | Justificativa | Recomendação |
|---|---|---|---|---|---|---|---:|---|---|
| V01 | H1 | Visão Geral (`F01`) e Filtro Alto (`F02A`) | Visualizar indicadores superiores (KPIs) e comparar com o contador de paginação no rodapé da tabela. | Divergência numérica entre os cards KPI do topo (`132` casos totais e `28` alertas de alto risco) e o rodapé da listagem (`Exibindo 1–4 de 130` / `90`). | Pode gerar desconfiança do analista quanto à integridade e atualização em tempo real da fila de triagem. | Cards KPI superiores (`132` / `28`) vs. texto de paginação inferior (`130` / `90`) nas telas `tela_visao_geral.png` e `filtro_alto.png`. | **2** | Problema menor de consistência de dados simulados no protótipo; não bloqueia a execução das tarefas, mas afeta a credibilidade do status. | Sincronizar todos os contadores simulados no Figma para refletirem exatamente `132` casos totais e `28` alertas de alto risco. |
| V02 | H4 | Confirmação (`F04`), Filtro Alto (`F02A`) e Relatórios (`F07`) | Ler rótulos de botões de ação, badges de severidade e botões de exportação de arquivos. | Inconsistências ortográficas e semânticas nos rótulos: `VIZUALIZAR` (em vez de `VER DETALHES`), `Rsico Alto` (erro de digitação) e botão de exportação tabular rotulado como `Download PDF` em vez de CSV. | Quebra o padrão terminológico entre telas e pode induzir o operador a baixar um formato de arquivo diferente do esperado. | Capturas `tela_sucesso.png` (`VIZUALIZAR`), `filtro_alto.png` (`Rsico Alto`) e `tela_relatorios.png` (`Download PDF` no card de planilha). | **2** | Problema menor de consistência textual; o contexto visual permite compreender a ação, mas exige padronização profissional. | Padronizar os rótulos para `VER DETALHES`, `Risco Alto`, `Base Anonimizada` e `Download CSV` na versão `v1.1` do Figma. |
| V03 | H7 | Visão Geral (`F01`) | Clicar diretamente no card KPI vermelho `Alerta de Alto Risco: 28` esperando filtrar a listagem abaixo. | O card KPI superior funciona apenas como indicador estático, exigindo que o usuário desloque o cursor até a barra de filtros da tabela (`ALTO`). | Reduz a agilidade de triagem para operadores experientes que utilizam os cards de resumo como atalho de navegação. | Comportamento interativo do componente KPI superior na tela `tela_visao_geral.png` (ausência de hotspot de filtragem). | **1** | Problema cosmético/oportunidade de eficiência; os botões explícitos de filtro logo abaixo já resolvem a tarefa sem bloqueios. | Vincular hotspot interativo ao card KPI de alto risco para acionar diretamente a visão filtrada (`F02A`). |
| V04 | H10 | Análises Estatísticas (`F06`) e Auditoria (`F03`) | Interpretar a taxa de concordância/precisão da IA (`94,2%`) e o volume agregado de atendimentos (`132 casos`). | Ausência de nota explicativa permanente esclarecendo que o escore da IA representa *indício preliminar de apoio à triagem* e que os números refletem apenas atendimentos submetidos à plataforma (não prevalência populacional). | Risco de viés de automação (operador tratar a sugestão do modelo como decisão definitiva) ou interpretação estatística enviesada em relatórios institucionais. | Telas `tela_analises.png` e `F03` (exibição direta de `94,2%` e `132 casos` sem microcopy explicativo de escopo e limites). | **3** | Problema maior de compreensão e explicabilidade em sistemas de apoio à decisão sensíveis; impacta diretamente a meta `MU02` e `QA03`/`QA05`. | Inserir rodapé/tooltip informativo permanente nas telas `F03` e `F06` declarando o caráter preliminar do parecer automatizado e a unidade de contagem da amostra. |
