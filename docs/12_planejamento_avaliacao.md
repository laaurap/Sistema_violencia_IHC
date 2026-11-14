# Entrega 12 — Planejamento da avaliação de usabilidade (DECIDE)

**Data:** {{dd/mm/aaaa}}  
**Status:** ⬜ não iniciada  
**Responsabilidade:** 1 solução por equipe

## Objetivo da atividade

Planejar a avaliação antes de executá-la, ligando perguntas de avaliação a métodos, participantes, tarefas, métricas, aspectos práticos, ética e forma de análise.

## O que está sendo avaliado

Em projetos cuja interface foi criada ou ampliada para a disciplina, o plano deve declarar explicitamente que a avaliação investiga **a qualidade da interação/protótipo**, não a validade científica ou o desempenho técnico do algoritmo/modelo do TCC.

Exemplos de perguntas:

- o DBA consegue localizar e comparar duas execuções?
- o analista entende o significado de um indicador?
- o administrador consegue alterar uma permissão sem risco de erro não percebido?
- o usuário compreende que o processamento está em andamento e consegue recuperar-se de uma falha?
- os filtros ajudam a localizar o histórico relevante?
- um relatório permite identificar a informação necessária para a decisão?

Se o protótipo utiliza dados ou resultados simulados, documente isso no plano.

## A. Método DECIDE

| Etapa | Aplicação no projeto |
|---|---|
| **D — Determine the goals** | Quais objetivos da avaliação? Relacione às metas de usabilidade da Entrega 8. |
| **E — Explore the questions** | Quais perguntas específicas a avaliação deve responder? |
| **C — Choose the evaluation paradigm and techniques** | Quais métodos serão usados e por quê? Ex.: inspeção heurística + observação de usuários. |
| **I — Identify the practical issues** | Participantes, recrutamento, ambiente, equipamentos, piloto, cronograma, responsáveis, riscos técnicos. |
| **D — Decide how to deal with ethical issues** | Consentimento, privacidade, gravação, anonimização, interrupção, dados sensíveis. |
| **E — Evaluate, interpret and present the data** | Como dados quantitativos/qualitativos serão consolidados, comparados às metas e apresentados. |

|---|---|
| **D — Determine the goals** | Avaliar se o painel web administrativo permite à **Analista de Triagem e Auditoria**: (1) compreender os indicadores gerais sem confundir volume de análises com prevalência populacional (`H04`); (2) filtrar casos por nível de risco e localizar códigos anônimos com rapidez, recuperando-se de buscas vazias (`H01` / `MU01`); (3) confrontar transcrições sinalizadas com a fundamentação legal RAG (Art. 147-B) e aprovar ou reclassificar o parecer da IA de forma segura (`H03` / `MU02`, `MU03`); e (4) navegar pelas visões de histórico, métricas do modelo e exportação de relatórios sem sobrecarga cognitiva (`MU04`). |
| **E — Explore the questions** | Desdobradas em `QA01` a `QA06` na Seção B, cobrindo eficiência de filtragem/busca, recuperação de erro em busca sem resultados, compreensão da explicabilidade RAG (*split-screen*), segurança no fluxo de reclassificação humana (*human-in-the-loop*), interpretação não enviesada dos indicadores e conformidade heurística/acessibilidade visual. |
| **C — Choose the evaluation paradigm and techniques** | Combinação de **dois métodos complementares** para garantir rigor analítico mesmo em equipe individual: (1) **Inspeção Heurística** conduzida pela autora (aplicando as 10 Heurísticas de Nielsen + critérios de explicabilidade de IA e contraste visual) para identificar problemas estruturais de feedback, consistência e prevenção de erros; e (2) **Teste de Usabilidade Moderado com Observação e Protocolo Pensar em Voz Alta (*Think-Aloud*)** com participante externo (`P01`), seguido de questionário pós-tarefa (SEQ) e entrevista breve, para observar dificuldades reais de navegação e compreensão dos pareceres. |
| **I — Identify the practical issues** | **Participantes:** Recrutamento por conveniência de **1 participante externo ao desenvolvimento do protótipo** (`P01`, estudante/profissional familiarizado com sistemas web e painéis digitais, atuando no papel simulado de *Analista de Triagem e Auditoria*), complementado pela inspeção heurística da autora. **Ambiente e Equipamento:** Sessão individual presencial ou remota (via Google Meet com compartilhamento de tela) em computador/notebook com resolução desktop (`1440 × 1024 px`), utilizando o link público do protótipo no Figma (`Fit width and height`). **Verificação Prévia e Cronograma:** Verificação técnica prévia do link e hotspots do Figma pela autora em 13/11/2026 antes da sessão oficial; execução do teste com `P01` entre 14/11/2026 e 15/11/2026; duração estimada de 25 a 30 minutos, conduzida e registrada por Laura de Souza Parente. **Riscos técnicos:** Instabilidade de conexão ou ajuste de escala do Figma mitigados com pré-teste do link em janela anônima e configuração `Fit width and height`. |
| **D — Decide how to deal with ethical issues** | **Consentimento e Voluntariedade:** Apresentação e assinatura do Termo de Consentimento Livre e Esclarecido (TCLE) antes do início, explicando que o objeto avaliado é a interface (nunca o participante) e garantindo o direito de pausa ou desistência a qualquer momento sem ônus. **Privacidade e Sensibilidade do Tema:** Como o protótipo simula mensagens de violência psicológica (humilhação/manipulação), o participante é previamente informado sobre a natureza temática fictícia do conteúdo; a identidade civil do participante é mantida sob sigilo nos relatórios (identificado apenas como `P01`), e eventuais registros de tela/áudio são usados estritamente para transcrição de falas e descartados após a Entrega 14. |
| **E — Evaluate, interpret and present the data** | **Consolidação:** Tabulação quantitativa das 5 tarefas (`UT01`–`UT05`) realizadas por `P01` contendo resultado (sucesso total, parcial ou falha), tempo de execução em segundos, contagem de erros/hesitações, pedidos de ajuda e nota de facilidade pós-tarefa (SEQ 1–7). **Análise Qualitativa:** Codificação das falas do *Think-Aloud* de `P01` e das violações levantadas na inspeção heurística por severidade (0 a 4 de Nielsen) e categoria de impacto (compreensão RAG, filtragem, feedback, LGPD). **Apresentação:** Comparação direta dos resultados obtidos com os critérios esperados e metas de usabilidade na Entrega 14, gerando lista priorizada de melhorias para o protótipo. |

## B. Perguntas de avaliação

| ID | Pergunta | Método | Métrica/evidência | Critério esperado |
|---|---|---|---|---|
| QA01 | {{usuários completam T01 sem ajuda?}} | observação | sucesso, ajuda, erro | {{MU01}} |
| QA02 | {{há problemas de feedback?}} | heurística | violações H1 | {{...}} |

| QA01 | O participante consegue filtrar atendimentos por nível de risco (`ALTO`, `MÉDIO`, `BAIXO`) e localizar um caso específico (`#C001`) sem auxílio? | Observação de teste (`P01`) + Think-Aloud | Resultado da tarefa, tempo de execução, cliques fora do alvo e pedidos de ajuda | Concluir a filtragem e busca em até 45 segundos, sem ajuda do moderador (`MU01` / `H01`) |
| QA02 | Ao pesquisar um código inexistente (`#C999`) e obter estado vazio, o participante compreende o ocorrido e consegue restaurar a listagem padrão? | Observação de teste (`P01`) + Inspeção heurística | Recuperação autônoma, tempo de reação e violações de H9 (recuperação de erros) | Reconhecer a ausência do registro e acionar a recuperação (`Limpar Filtros`) de forma autônoma em até 20 segundos (`MU01`) |
| QA03 | Na tela de auditoria (*split-screen*), o participante compreende por que a IA classificou o caso como alto risco (mensagens sinalizadas + Art. 147-B) e distingue *indício preliminar* de *sentença definitiva*? | Observação (`P01`) + Entrevista pós-tarefa | Explicação verbal coerente sobre os trechos sinalizados, base legal e grau de confiança (`94%`) | Articular corretamente os critérios legais do RAG e os limites da classificação preliminar da IA (`MU02` / `H03`) |
| QA04 | O participante consegue aprovar um parecer ou reclassificar o nível de risco registrando justificativa obrigatória, percebendo claramente a confirmação do sistema? | Observação de teste (`P01`) + Inspeção heurística | Conclusão do fluxo (`F03 → F03R → F04`), percepção do banner de sucesso e atualização do status | Concluir o fluxo sem erros de navegação e reconhecer explicitamente o feedback de gravação (`MU03`) |
| QA05 | Ao consultar a Visão Geral, Análises Estatísticas e Relatórios, o participante interpreta corretamente os indicadores agregados sem confundir volume de atendimentos com prevalência populacional? | Observação (`P01`) + Pergunta de interpretação | Resposta qualitativa sobre o significado dos KPIs (`132 casos`, `28 alertas`) e localização de exportação | Interpretar adequadamente os KPIs sem viés populacional e localizar o preview/download de laudo (`MU04` / `H04`) |
| QA06 | O protótipo apresenta violações graves de consistência visual, visibilidade do status do sistema, prevenção de erros ou contraste/legibilidade? | Inspeção heurística | Lista de problemas classificados pela escala de severidade de Nielsen (0–4) | Zero violações de severidade 4 (catastróficas) e planos de correção documentados para severidades 2–3 |

## C. Escopo e participantes

| Item | Planejamento |
|---|---|
| Perfis | Usuário externo ao desenvolvimento (`P01`), com familiaridade cotidiana com computadores, navegadores web e sistemas/painéis digitais, atuando no papel simulado de **Analista de Triagem e Auditoria**. |
| Critérios de inclusão/exclusão | **Inclusão:** idade ≥ 18 anos; experiência habitual com navegação web em desktop; concordância com o TCLE; não ter participado da criação das telas do Figma. **Exclusão:** integrantes da equipe do projeto (a autora realiza apenas a inspeção heurística em separado) ou pessoas que declarem desconforto emocional prévio com textos simulados sobre conflitos interpessoais. |
| Nº de participantes | **1 participante externo (`P01`)** recrutado por conveniência para o teste de usabilidade moderado com observação (*Think-Aloud*) + **1 avaliadora** na inspeção heurística (totalizando duas fontes complementares de evidência). |
| Ambiente | Sessão individual em ambiente silencioso (presencial ou remota via Google Meet com compartilhamento de tela e áudio). |
| Dispositivo | Computador desktop ou notebook com mouse/trackpad, navegador Google Chrome/Edge atualizado e tela configurada em modo widescreen (`1440 × 1024 px` / `Fit width and height`). |
| Protótipo/versão= | Protótipo navegável de alta fidelidade no Figma — Entrega 11 (`v1.0`, fluxos `M01` a `M04`, telas `F01` a `F08`), operando com dados fictícios anonimizados. |
| Teste piloto | **Quem:** Verificação prévia estruturada pela própria autora (`P00`). **Quando:** 13/11/2026 (antes da sessão oficial com `P01`). **O que validar:** funcionamento de todos os hotspots clicáveis no Figma em aba anônima, modo `Fit width and height`, tempo total estimado e clareza/neutralidade dos enunciados das tarefas (`UT01`–`UT05`). |


## D. Lista de tarefas de avaliação

| ID | Cenário neutro entregue ao usuário | Objetivo oculto da avaliação | Critério de sucesso | Tempo-limite (se houver) |
|---|---|---|---|---|
| UT01 | *"Você acabou de iniciar seu turno de revisão e precisa verificar quantos atendimentos estão classificados como urgentes hoje e isolar apenas esses registros na listagem principal."* | Avaliar compreensão dos cards KPI (`F01`) e acionamento do filtro de risco `ALTO` (`F02A`) (`T01` / `M01`). | Participante identifica o contador de alertas (`28`) e ativa o filtro de alto risco visualizando apenas os casos filtrados. | 45 segundos |
| UT02 | *"Uma coordenação pediu para verificar se existe algum registro sob o código `#C999`. Pesquise esse atendimento e, caso não o encontre, retorne a visualização completa de todos os casos."* | Testar busca sem resultados (`F01E`), compreensão da mensagem de estado vazio e uso do botão de recuperação (`Limpar Filtros`) (`M01`). | Participante realiza a busca, reconhece a ausência do registro e restaura a listagem completa sem auxílio. | 45 segundos |
| UT03 | *"Abra o atendimento `#C001` para revisar a conversa registrada, verifique os trechos que motivaram o alerta do sistema e a base legal utilizada, e conclua a validação concordando com a classificação sugerida."* | Avaliar leitura da interface *split-screen* (`F03`), compreensão da explicabilidade RAG (Art. 147-B) e fluxo de aprovação (`F04`) (`T02` / `M02`). | Participante abre o caso `#C001`, aponta as mensagens sinalizadas/fundamentação legal, aprova o parecer e percebe o feedback de sucesso. | 90 segundos |
| UT04 | *"Suponha que, ao revisar um atendimento, você discorde da gravidade estimada pelo sistema e considere necessário alterar o nível de risco para Médio, deixando registrado o motivo técnico dessa mudança."* | Avaliar descoberta e uso do fluxo *Human-in-the-Loop* (`F03 → F03R → F04`), preenchimento de justificativa e confirmação (`T03` / `M03`). | Participante abre o modal de reclassificação, seleciona o novo nível, preenche justificativa, confirma e verifica o status atualizado. | 90 segundos |
| UT05 | *"Antes de encerrar o turno, verifique qual tem sido a taxa geral de concordância entre as revisões humanas e o sistema, e localize onde gerar ou pré-visualizar um relatório consolidado para envio institucional."* | Avaliar navegação entre abas secundárias (`F06 Análises` e `F07 Relatórios`) e compreensão das métricas agregadas (`T04` / `M04`). | Participante acessa as abas de Análises e Relatórios, identifica a precisão/concordância (`94.2%`) e localiza a pré-visualização/exportação do laudo. | 90 segundos |

> Uma boa instrução descreve o objetivo do participante sem dizer **onde clicar** ou usar o rótulo exato do controle que está sendo testado.

## E. Instrumentos

- [Modelo de termo de consentimento](../instrumentos/termo_consentimento_modelo.md)
- [Roteiro de teste](../instrumentos/roteiro_teste_usabilidade.md)
- [Planilha de observação](../instrumentos/planilha_observacao_modelo.md)
- [Formulário de avaliação heurística](../instrumentos/formulario_heuristica_modelo.md)
- {{questionário pré/pós-teste}}

- [Modelo de termo de consentimento](../instrumentos/termo_consentimento_modelo.md)
- [Roteiro de teste](../instrumentos/roteiro_teste_usabilidade.md)
- [Planilha de observação](../instrumentos/planilha_observacao_modelo.md)
- [Formulário de avaliação heurística](../instrumentos/formulario_heuristica_modelo.md)
- Questionário breve pré-teste (perfil e familiaridade com painéis/triagem) e pós-tarefa SEQ (*Single Ease Question*, escala de 1 a 7) + entrevista semiestruturada de fechamento (compreensão da explicabilidade RAG e interpretação dos KPIs).

## F. Plano de análise

## F. Plano de análise

Defina antes dos testes:

- sucesso total / parcial / falha;
- o que conta como erro, dúvida, ajuda e abandono;
- como tempo será medido;
- escala de satisfação pós-tarefa;
- como observações/falas serão codificadas;
- como problemas serão priorizados;
- como comparar resultados às metas de usabilidade.

- **Classificação de desempenho por tarefa (sucesso total / parcial / falha):**
  - **Sucesso total:** participante (`P01`) conclui o objetivo da tarefa dentro do tempo esperado, pelo caminho previsto ou equivalente válido, sem ajuda do moderador.
  - **Sucesso parcial:** participante conclui o objetivo, mas com hesitação prolongada, caminho ineficiente (3 ou mais desvios/cliques errados), ultrapassando o tempo-limite ou necessitando de 1 dica neutra do moderador.
  - **Falha:** participante desiste da tarefa, não atinge o objetivo final, interpreta erroneamente o resultado crítico ou necessita de intervenção direta para avançar.
- **Definição de erro, dúvida, ajuda e abandono:**
  - **Erro de interação:** clicar em elemento não interativo ou rota incorreta acreditando que executará a ação desejada (ex.: clicar no card de KPI achando que ele filtra a tabela quando apenas o botão de filtro o faz).
  - **Dúvida / hesitação:** pausa superior a 8 segundos acompanhada de verbalização de incerteza sobre o significado de um termo, ícone ou estado.
  - **Pedido de ajuda:** solicitação explícita ao moderador sobre como prosseguir (o moderador responde inicialmente com perguntas neutras como *"O que você esperaria encontrar aqui?"* antes de fornecer qualquer dica mínima).
  - **Abandono:** declaração do participante de que não consegue concluir a tarefa.
- **Medição de tempo:** cronometrado em segundos a partir do término da leitura do enunciado neutro da tarefa (`UT01`–`UT05`) até a conclusão da ação final esperada na interface.
- **Escala de satisfação pós-tarefa:** aplicação imediata após cada tarefa da escala **SEQ (*Single Ease Question*)** de 1 (*Muito difícil*) a 7 (*Muito fácil*), complementada ao final da sessão por 3 perguntas abertas sobre clareza da explicabilidade RAG, confiança na reclassificação e interpretação dos números gerais.
- **Codificação de observações e falas:** as anotações da planilha de observação de `P01`, suas verbalizações no *Think-Aloud* e os achados da inspeção heurística serão agrupados por afinidade em categorias temáticas: (1) *Navegação e Filtragem*; (2) *Compreensão da Explicabilidade RAG e Risco*; (3) *Fluxo Human-in-the-Loop e Feedback*; (4) *Interpretação de Indicadores e Privacidade*.
- **Priorização de problemas:** tanto os achados do teste com `P01` quanto as violações da inspeção heurística serão classificados pela **Escala de Severidade de Nielsen (0 a 4)**: `0` (não é problema), `1` (cosmético), `2` (menor — baixa prioridade), `3` (maior — alta prioridade de correção) e `4` (catastrófico — correção obrigatória imediata).
- **Comparação com metas de usabilidade:** os indicadores obtidos na sessão com `P01` (conclusão das 5 tarefas dentro do limite estipulado, nota SEQ ≥ 5,5/7 e interpretação correta dos pareceres/KPIs) e na inspeção heurística (zero violações de severidade 4) serão confrontados diretamente com as metas definidas na Entrega 8 e documentados na Entrega 14.

## Checklist

- [X] As seis etapas DECIDE foram contextualizadas, não apenas expandidas por sigla.
- [X] Perguntas de avaliação têm método e evidência correspondentes.
- [X] O plano distingue avaliação de IHC de avaliação técnica/científica do TCC.
- [X] Dados ou processamentos simulados no protótipo estão declarados.
- [X] Tarefas vêm de objetivos/cenários relevantes.
- [X] Critérios de sucesso foram definidos antes da coleta.
- [X] Questões práticas e éticas estão resolvidas.
- [X] Instrumentos estão prontos antes da Entrega 13/14.
- [X] Plano diz como dados serão analisados e apresentados.
