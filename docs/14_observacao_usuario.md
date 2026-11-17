# Entrega 14 — Avaliação de usabilidade por observação de usuários

**Data:** 16/11/2026  
**Status:** ⬜ não iniciada  
**Responsabilidade:** solução consolidada por equipe. O número de participantes finais observados deve ser igual ao número de integrantes, conforme o modelo da disciplina; recomenda-se que cada integrante seja responsável por conduzir/analisar ao menos um participante.

## Objetivo da atividade

Observar usuários representativos realizando tarefas reais ou realisticamente simuladas para identificar problemas de eficácia, eficiência, compreensão e satisfação que não podem ser inferidos apenas por inspeção.

> **Participantes finais não devem ser membros da equipe.** Um integrante pode participar do teste piloto apenas para validar roteiro/equipamentos, sem contar na amostra final.

### Quando o usuário é um perfil profissional especializado

Em TCCs técnicos, o público pode ser DBA, analista, pesquisador, administrador, técnico ou outro especialista. Priorize participantes que possuam relação real com as tarefas. Se não for possível recrutar o perfil ideal, qualquer participante aproximado/proxy deve ser **justificado previamente e tratado como limitação**; não apresente o resultado como equivalente ao de especialistas reais.

O teste avalia a **interação com o protótipo**. Não é necessário que o participante valide o desempenho científico do algoritmo. Resultados simulados podem ser usados quando declarados e coerentes com a tarefa.

Tarefas podem envolver, por exemplo, interpretar um dashboard, configurar uma análise, encontrar uma execução no histórico usando filtros, comparar resultados, gerar relatório, revisar alerta ou administrar permissões.

## A. Fluxograma do processo — equipe

![Fluxograma](../assets/14_testes/fluxograma_avaliacao.svg)

O fluxograma deve representar, no mínimo: planejamento → recrutamento → consentimento → preparação → execução das tarefas/observação → pós-teste → consolidação/análise → recomendações.

## B. Procedimento de preparação e execução — equipe

### Passo 1 — Objetivos e versão avaliada

**Versão/commit/Figma:** Protótipo no Figma — Entrega 11 — [Link do Protótipo no Figma](https://www.figma.com/design/YVklhni7iJ08TDOFGShxkq/TCC?node-id=0-1&t=2fcaddAI2MqV1c7P-1)   
**Metas de usabilidade relacionadas:** 
- **`MU01` (Eficácia e recuperação de erros):** Filtrar atendimentos por nível de risco (`ALTO`, `MÉDIO`, `BAIXO`), localizar códigos anônimos e recuperar-se autonomamente de buscas sem resultados (`QA01`, `QA02`).
- **`MU02` (Compreensão da explicabilidade RAG):** Confrontar transcrições sinalizadas com a fundamentação legal (Art. 147-B) na visão *split-screen* (`F03`), distinguindo *indício preliminar de triagem* de *sentença definitiva* (`QA03`).
- **`MU03` (Segurança e controle *Human-in-the-Loop*):** Aprovar pareceres ou reclassificar o nível de risco registrando justificativa obrigatória (`F03 → F03R → F04`), percebendo claramente a confirmação do sistema (`QA04`).
- **`MU04` (Eficiência, interpretação gerencial e satisfação):** Navegar entre histórico, métricas agregadas (`F06`) e relatórios (`F07`) sem sobrecarga cognitiva e atingir nota média **SEQ ≥ 5,5/7,0** (`QA05`).


### Passo 2 — Participantes

| ID | Perfil | Critérios que justificam participação | Integrante responsável |
|---|---|---|---|
| **U01** | Estudante concludente (último semestre) de Ciência da Computação, familiarizado com sistemas web e dashboards analíticos, externo à equipe de desenvolvimento e sem contato prévio com o protótipo. | **Justificativa de participante *proxy*:** O público-alvo final do painel são analistas de triagem e supervisores técnicos de redes de atendimento (especialistas de difícil acesso no cronograma da disciplina). Conforme planejado na Entrega 12, recrutou-se 1 participante externo à equipe (`U01`) atuando no papel simulado de *Analista de Triagem e Auditoria* para avaliar a clareza da interação, filtros, auditoria *split-screen* e reclassificação humana. A ausência de formação jurídica/psicossocial especializada é declarada formalmente como limitação metodológica na Seção G. | Laura de Souza Parente (`22.123.033-7`) |


### Passo 3 — Consentimento e privacidade

- Termo/registro de consentimento: {{link}}
- Gravação de tela/áudio/vídeo: Sim — gravação da sessão remota (compartilhamento de tela no protótipo do Figma + áudio *Think-Aloud*), hospedada em modo **Não listado** no YouTube com finalidade estritamente acadêmica.
- Forma de anonimização: Identidade civil omitida nos documentos e relatórios da disciplina (referenciado exclusivamente como **`U01`** / `P01` na Entrega 12), utilizando apenas dados fictícios anonimizados (`#C001`–`#C999`) no protótipo.
- Local e período de armazenamento: Vídeo não listado de acesso restrito via link direto exclusivamente durante o semestre letivo de 2026.2 para avaliação docente, sendo removido após o encerramento da disciplina.

### Passo 4 — Teste piloto

**Data:** 13/11/2026  
**O que foi validado:** Funcionamento de todos os hotspots clicáveis do protótipo no Figma em janela anônima (`Fit width and height`), tempo estimado da sessão (~13 minutos), qualidade da gravação de tela/áudio e clareza/neutralidade da missão exploratória apresentada ao participante.  
**Mudanças após piloto:** Adoção de missão exploratória contínua no papel de *Analista de Triagem*, permitindo ao participante navegar livremente pelo painel, testar todos os estados (incluindo estado vazio/erro) e executar o fluxo completo de auditoria e reclassificação sem indução de cliques pelo moderador.

### Passo 5 — Tarefas

| ID | Cenário/instrução apresentada | Critério de sucesso | Métricas | Ligação com modelo |
|---|---|---|---|---|
| UT01 | Identificar os indicadores gerais do turno e compreender/filtrar atendimentos por nível de risco (`ALTO`, `MÉDIO`, `BAIXO`) e status na listagem principal. | Identificar os indicadores superiores (`132` casos / alertas) e explorar a filtragem por nível de risco e status na listagem. | Sucesso (total/parcial/falha), tempo (`mm:ss`), erros, ajudas, satisfação SEQ (1–7) | `T01` / `M01` / `F01 → F02A` (`QA01`, `MU01`) |
| UT02 | Testar uma busca sem correspondência (`tela de erro`) e retornar à visualização completa de todos os casos. | Realizar a busca sem resultados, reconhecer a mensagem de estado vazio e acionar `LIMPAR FILTROS / RESTAURAR BUSCA` sem auxílio. | Sucesso (total/parcial/falha), tempo (`mm:ss`), erros, ajudas, satisfação SEQ (1–7) | `M01` / `F01E → F01` (`QA02`, `MU01`) |
| UT03 | Abrir um atendimento sinalizado para revisar a conversa registrada, verificar a fundamentação legal (`Art. 147-B`) e validar o parecer. | Abrir a auditoria individual, inspecionar a tela *split-screen* (conversa × Art. 147-B) e acionar o fluxo de aprovação com percepção do feedback. | Sucesso (total/parcial/falha), tempo (`mm:ss`), erros, ajudas, satisfação SEQ (1–7) | `T02` / `M02` / `F03 → F04` (`QA03`, `MU02`) |
| UT04 | Revisar um caso de alto risco e alterar manualmente o nível de risco para `MÉDIO`, registrando a justificativa técnica do analista. | Abrir a reclassificação humana a partir da auditoria, selecionar o novo nível de risco (`MÉDIO`), preencher a justificativa técnica, confirmar e verificar a atualização. | Sucesso (total/parcial/falha), tempo (`mm:ss`), erros, ajudas, satisfação SEQ (1–7) | `T03` / `M03` / `F03 → F03R → F04` (`QA04`, `MU03`) |
| UT05 | Explorar as visões gerenciais de análises estatísticas e relatórios consolidados do sistema. | Acessar as abas de `Análises` (`F06`) e `Relatórios` (`F07`), identificar os indicadores agregados e localizar a pré-visualização/exportação do laudo. | Sucesso (total/parcial/falha), tempo (`mm:ss`), erros, ajudas, satisfação SEQ (1–7) | `T04` / `M04` / `F06` & `F07` (`QA05`, `MU04`) |


### Passo 6 — Protocolo do moderador

1. Receber participante e explicar que **o produto está sendo avaliado, não a pessoa**.
2. Obter consentimento.
3. Aplicar perfil pré-teste mínimo necessário.
4. Ler instruções padronizadas.
5. Observar sem ensinar o caminho; registrar pedidos de ajuda separadamente.
6. Se usar *think aloud*, explicar e aplicar de forma consistente.
7. Após cada tarefa, registrar satisfação/SEQ ou escala definida.
8. Fazer pós-teste/entrevista breve.
9. Encerrar e explicar uso dos dados.

## C. Resultados — por participante

### U01 — Usuário aproximado (*proxy*), estudante concludente de Ciência da Computação

| Tarefa | Grau de sucesso | Erros | Tipos de erro/dificuldade | Ajudas | Tempo | Satisfação | Evidência/observação |
|---|---|---:|---|---:|---|---|---|
| **UT01** *(Visão Geral & Filtros de Risco)* | **Total** | 0 | Nenhuma dificuldade; identificou rapidamente os KPIs, filtros de risco e status na listagem. | 0 | `01:02` *(exploratório)* | **7 / 7** | `[00:58]`–`[02:25]`: *"Já gostei muito da classificatória do nível de risco... dá para ver que tem alguns pendentes, outros aprovados, outros com reclassificação."* |
| **UT02** *(Busca sem Resultados & Restauração)* | **Total** | 0 | Nenhuma dificuldade; compreendeu imediatamente a mensagem de estado vazio e o botão de restauração. | 0 | `00:22` | **7 / 7** | `[09:20]`–`[09:42]`: *"Aqui ele vai dar que nenhum foi encontrado porque eu pesquisei alguma coisa que não tinha... mas aí dá para limpar, restaurar busca também, de boa."* |
| **UT03** *(Auditoria Split-Screen & Aprovação)* | **Total** | 0 | Nenhuma dificuldade; leitura rápida dos balões de conversa e da base legal Art. 147-B. | 0 | `01:22` *(com leitura)* | **7 / 7** | `[02:29]`–`[03:51]`: *"Aparece aqui explicadinho bonitinho, parecer preliminar daí crime de violência psicológica, o artigo... você colocar o número do artigo é muito bom, que a pessoa consegue se justificar se ela precisar."* |
| **UT04** *(Reclassificação Humana)* | **Total** | 0 | Nenhuma dificuldade; fluxo de alteração para nível `MÉDIO` e registro de justificativa concluído sem travamentos. | 0 | `00:39` | **7 / 7** | `[03:54]`–`[04:33]`: *"Novo nível, média amarela que ele estava no alto. E consegue também ter a justificativa do analista... se a pessoa não gosta da justificativa da IA, pelo menos uma pessoa humana escrevendo às vezes se sente mais confortável."* |
| **UT05** *(Análises & Relatórios)* | **Total** | 0 | Nenhuma dificuldade; navegação natural pelas abas `Análises` (`94%`) e `Relatórios` (`Sumário Executivo` / `PDF`). | 0 | `03:00` *(exploratório)* | **7 / 7** | `[04:48]`–`[07:48]`: *"Sumário executivo, o que aconteceu, a porcentagem de cada caso de abuso, fundamentação jurídica, que eu acho que é muito bom ter... essa parte dos relatórios é muito bom pra nunca perder nenhum relatório."* |

*\*Nota sobre SEQ (1–7): Nota máxima `7/7` consolidada no pós-teste, respaldada na gravação pelas declarações espontâneas de `U01` de que não encontrou nenhuma dificuldade, compreendeu todo o fluxo em poucos minutos e adotaria o painel em ambiente profissional.*

**Link da gravação (se autorizado):** [Gravação de Teste da Interface — YouTube (Não Listado)](https://youtu.be/sgTh_ITuW0I) 
**Resposta pós-teste:** Na entrevista de encerramento (`[07:48]`–`[12:55]`), o participante (`U01`) afirmou que **não travou em nenhuma parte**, destacou que a interface *"é bem autoexplicativa, bem limpa, bem clean"* e que *"em 5 minutos eu tô entendendo bem como ela funciona"*, elogiou a codificação semântica de cores (vermelho = alto risco/atenção imediata; amarelo = médio; verde = baixo) e declarou: ***"Com certeza usaria dentro de um ambiente de trabalho... eu acho que ela é muito boa para uma empresa e para as pessoas do dia a dia"***. Como sugestão espontânea (`[12:36]`), propôs expandir a base de casos simulados e incluir um canal de feedback dos operadores dentro da plataforma. Atribuiu nota máxima (**7/7**) de facilidade.

> Repita para U02, U03...

## D. Consolidação por tarefa

| Tarefa | Taxa de sucesso | Tempo típico | Erros recorrentes | Satisfação | Meta atendida? | Problemas prioritários |
|---|---:|---|---|---|---|---|
| **UT01** *(Filtragem e Classificação de Risco)* | **100%** (1/1 total) | `01:02` *(com exploração verbal)* | Nenhum (0 erros) | **7,0 / 7,0** | **Sim** (`MU01`) | Nenhum bloqueio no teste; manter melhoria oportunista `HC04` (atalho clicável no card KPI). |
| **UT02** *(Busca Vazia e Restauração)* | **100%** (1/1 total) | `00:22` *(meta ≤ 45s)* | Nenhum (0 erros) | **7,0 / 7,0** | **Sim** (`MU01`) | Nenhum; estado vazio e botão de restauração altamente eficazes. |
| **UT03** *(Auditoria Split-Screen e Aprovação)* | **100%** (1/1 total) | `01:22` *(meta ≤ 90s)* | Nenhum (0 erros) | **7,0 / 7,0** | **Sim** (`MU02`) | Nenhum bloqueio; `U01` percebeu espontaneamente o termo *"parecer preliminar"* (`[03:00]`), mas manter nota fixa `HC01`. |
| **UT04** *(Reclassificação Humana)* | **100%** (1/1 total) | `00:39` *(meta ≤ 90s)* | Nenhum (0 erros) | **7,0 / 7,0** | **Sim** (`MU03`) | Nenhum bloqueio; fluxo *Human-in-the-Loop* considerado um dos pontos mais fortes do sistema. |
| **UT05** *(Análises e Relatórios)* | **100%** (1/1 total) | `03:00` *(leitura detalhada)* | Nenhum (0 erros) | **7,0 / 7,0** | **Sim** (`MU04`) | Nenhum bloqueio; corrigir rótulos textuais `HC03` (`Rsico Alto` / `Download CSV`). |

## E. Achados e recomendações

| ID | Achado | Evidência (quant. + qual.) | Impacto | Recomendação | Artefatos a revisar |
|---|---|---|---|---|---|
| **AU01** | **Validação empírica da fluidez navegacional, explicabilidade RAG e fluxo *Human-in-the-Loop*:** A divisão *split-screen* (conversa × Art. 147-B), a codificação por cores semânticas e a reclassificação com justificativa humana foram compreendidas sem fricção. | **Quantitativo:** 100% de sucesso total (5/5 tarefas, 0 erros, 0 ajudas, SEQ **7,0/7,0**). **Qualitativo:** Falas de `U01` em `[03:00]` (*"parecer preliminar... você colocar o número do artigo é muito bom"*), `[04:10]` (*"justificativa do analista... uma pessoa humana escrevendo"*) e `[12:09]` (*"usaria com certeza"*). | **Positivo (Alta eficácia e satisfação):** Confirma que a arquitetura de informação e os mecanismos de explicabilidade atendem à proposta do projeto. | Preservar integralmente a estrutura visual, a barra lateral, os badges semânticos e a disposição *split-screen* na evolução do sistema. | Nenhum ajuste estrutural necessário (manter base do Figma `v1.0`). |
| **AU02** | **Refinamento de microcopy, notas contextuais preventivas e canal de feedback operacional:** Além das correções textuais herdadas da inspeção heurística (`HC01`–`HC03`), `U01` sugeriu ampliar a massa de casos de teste e adicionar feedback contínuo dos operadores. | **Evidência cruzada (E13 + E14):** Erros sutis de rótulo (`VIZUALIZAR`, `Rsico Alto`, `Download PDF` para CSV) e divergência de contadores (`132`/`130` e `28`/`90`) passaram despercebidos na navegação rápida de `U01`; em `[12:36]`, `U01` sugeriu *"colocar mais casos, ter uma parte de feedback das pessoas que estão utilizando"*. | **Moderado (Prevenção semântica e acabamento institucional):** Evita ruídos interpretativos em uso contínuo e fortalece a melhoria contínua. | Aplicar pacote de refinamento no Figma (`v1.1`): corrigir rótulos (`VER DETALHES`, `Risco Alto`, `Download CSV`), sincronizar contadores (`132` e `28`), fixar rodapé explicativo sobre limites da IA (`HC01`) e incluir opção de feedback do analista nas configurações. | Protótipo Figma (`tela_sucesso`, `tela_relatorios`, `filtro_alto`, `tela_analises`) e Matriz de Rastreabilidade. |


## F. Comparação com a avaliação heurística

| Problema | Detectado na heurística? | Detectado por usuários? | O que aprendemos |
|---|---|---|---|
| **Ausência de nota contextual sobre limite preliminar da IA e unidade de contagem (`HC01` / `V04`)** | **Sim** (Severidade 3 — Maior) | **Parcialmente** (`U01` leu *"parecer preliminar"* na auditoria `[03:00]`, mas não questionou o escopo estatístico de `94%` em `Análises`) | Embora o rótulo de parecer preliminar ajude na auditoria individual, na tela de `Análises` (`94%` de precisão) o usuário tende a aceitar a métrica sem questionar a base amostral; portanto, a nota explicativa permanente continua essencial. |
| **Divergência numérica entre KPIs e rodapé da tabela (`HC02` / `V01`)** | **Sim** (Severidade 2 — Menor) | **Não** (`U01` focou nos cards superiores `132 casos` `[04:35]` e nos badges da tabela) | Em triagem rápida, o operador confia nos cards KPI superiores e ignora o rodapé da paginação, mas sincronizar `132` e `28` mantém a consistência dos dados. |
| **Inconsistências ortográficas e de rótulo de botão (`HC03` / `V02`)** | **Sim** (Severidade 2 — Menor) | **Não** (`U01` navegou pelos botões e PDFs sem hesitação `[08:58]`) | O contexto visual compensou os erros de digitação (`VIZUALIZAR`, `Rsico Alto`, `Download PDF`), mas a revisão textual eleva a credibilidade institucional. |
| **Card KPI estático sem atalho de clique (`HC04` / `V03`)** | **Sim** (Severidade 1 — Cosmético) | **Não** (`U01` usou diretamente os filtros de risco e abas laterais sem hesitar) | Os controles explícitos de filtro já são suficientemente claros e eficientes, tornando o clique no card KPI apenas um atalho complementar opcional. |
| **Clareza da navegação *split-screen*, estado vazio e reclassificação humana** | **Sim** (Boas práticas `H2`, `H3`, `H6`, `H8`, `H9`) | **Sim** (Confirmado empiricamente: 100% de sucesso, 0 erros, SEQ `7/7`) | Convergência total entre inspeção heurística e teste empírico: as decisões de design para explicabilidade RAG, recuperação de erro e *Human-in-the-Loop* funcionam na prática. |


## G. Conclusão

A conclusão deve responder:

1. Quais metas de usabilidade foram atingidas?
   - Todas as quatro metas definidas para a avaliação (`MU01`, `MU02`, `MU03` e `MU04`) foram **plenamente atingidas**: o participante `U01` obteve **100% de sucesso total** nas cinco tarefas (`UT01`–`UT05`), concluiu as ações específicas dentro dos limites estipulados (incluindo `22s` na recuperação de busca vazia e `39s` na reclassificação humana), registrou **zero erros e zero pedidos de ajuda**, e avaliou a facilidade geral com nota **7,0 / 7,0** na escala SEQ (superando a meta de `≥ 5,5/7,0`).

2. Quais problemas foram recorrentes e com quais perfis/tarefas?
   - Não houve problemas recorrentes de navegação, erros de clique ou travamentos em nenhuma das tarefas executadas por `U01`. Os únicos pontos de melhoria identificados concentram-se nos achados documentais e de microcopy da inspeção heurística (`HC01`–`HC04`) e na sugestão complementar de expandir os casos simulados e incluir feedback operacional (`AU02`).

3. O que surpreendeu a equipe?
   - Surpreendeu positivamente a rapidez com que um participante sem formação jurídica identificou espontaneamente o caráter preliminar do parecer e o valor probatório do artigo legal (`Art. 147-B` em `[03:00]`), bem como a valorização imediata da justificativa humana na reclassificação (`[04:10]`) e a declaração de que adotaria a interface em ambiente empresarial (`[12:16]`). Também ficou evidente na comparação com a Entrega 13 que problemas sutis de texto e de escopo estatístico (`HC01`–`HC03`) não bloqueiam a fluidez, exigindo inspeção heurística complementar para serem detectados.

4. Quais mudanças são prioritárias?
   - Para a próxima iteração do protótipo (`v1.1`), priorizam-se: (1) inserir a nota informativa permanente esclarecendo o caráter preliminar da IA e a unidade de contagem estatística (`HC01`); (2) corrigir os rótulos textuais (`VER DETALHES`, `Risco Alto`, `Base Anonimizada` e `Download CSV`) (`HC03`); (3) sincronizar os contadores simulados do rodapé da tabela (`132` e `28`) (`HC02`); e (4) adicionar o atalho clicável no card KPI de alto risco (`HC04`) e espaço para feedback do operador (`AU02`).
  
5. Que limitações do teste impedem generalizações amplas?
   - Duas limitações metodológicas principais impedem a generalização estatística ampla dos resultados: (1) **tamanho da amostra ($n = 1$ participante)**, adequado ao escopo individual da disciplina, mas insuficiente para capturar variabilidade comportamental de equipes maiores; e (2) **uso de participante aproximado (*proxy*)**, que embora possua sólida base técnica em Computação e familiaridade com painéis corporativos, não atua diariamente como analista jurídico ou psicossocial de redes de acolhimento (especialistas que poderiam demandar nuances adicionais em casos limítrofes).

## Checklist

- [X] Número de participantes finais atende ao enunciado.
- [X] Participantes são representativos do público e não são membros da equipe.
- [X] Se foram usados participantes proxy, a justificativa e a limitação estão explícitas.
- [X] O teste avalia a interação; não confunde usabilidade do protótipo com desempenho técnico do TCC.
- [X] Tarefas administrativas/analíticas usadas no teste são rastreáveis a objetivos e cenários.
- [X] Há consentimento e anonimização.
- [X] Foi realizado teste piloto.
- [X] Tarefas têm critérios de sucesso definidos antes do teste.
- [X] Moderadores não ensinaram o caminho durante a tarefa.
- [X] Resultados estão separados por usuário e por tarefa.
- [X] Foram registrados sucesso, erros, ajudas, tempo e satisfação quando aplicáveis.
- [X] Conclusão combina evidência quantitativa e qualitativa.
- [X] Achados geram recomendações e atualização da rastreabilidade.
