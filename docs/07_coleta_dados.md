# Entrega 7 — Coleta de dados, necessidades e aspectos éticos

**Data:** 28/10/2026
**Status:** 🟩 concluída

## Objetivo da atividade

Planejar dados necessários para compreender usuários e requisitos de IHC, escolher técnicas adequadas e documentar instrumentos de modo que a aplicação possa ser reproduzida por pessoas diferentes.

## Para escopos de IHC derivados de TCC técnico

Quando o usuário e a interface foram propostos pela disciplina, uma prioridade da coleta é investigar se esse **cenário de uso realmente faz sentido**. Não trate o exercício de comercialização da Entrega 1 como validação de mercado.

Perguntas úteis incluem:

- esse perfil realmente realiza a atividade imaginada?
- quais ferramentas usa hoje?
- quais informações consulta?
- quais decisões toma?
- que vocabulário utiliza?
- quais parâmetros compreende e quais deveriam ser abstraídos?
- precisa de dashboard, histórico, filtros, relatórios ou comparação? Por quê?
- quais erros são frequentes e quais são críticos?
- existem papéis/permissões diferentes?
- que resultados do algoritmo/modelo seriam úteis ou difíceis de interpretar?

Quando o acesso ao perfil profissional for difícil, discuta com o docente alternativas metodológicas (especialistas próximos, dados secundários, literatura, participantes proxy) e registre as limitações. **Não esconda a limitação da amostra.**

## Hipóteses e lacunas prioritárias herdadas da Entrega 1

Antes de decidir “que dados coletar”, retome os itens `[H]` e `[?]` da Entrega 1 e o registro de hipóteses em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md). A coleta deve responder perguntas reais do projeto, e não apenas produzir um formulário porque a técnica foi solicitada.

| ID | Hipótese/lacuna | Evidência atual | Decisão que depende da resposta | Prioridade |
|---|---|---|---|---|
| H01 | Analistas de direitos humanos sentem necessidade de explicabilidade jurídica RAG (Art. 147-B) para confiar nas classificações automáticas de risco. | Análise de concorrência e literatura indicam alta taxa de desconfiança em modelos "caixa-preta". | Formato de apresentação da fundamentação legal no painel mestre/detalhe. | alta |
| H01 | O destaque direto de excertos nas mensagens reduz o tempo de auditoria sem comprometer a precisão. | Testes preliminares de visualização no protótipo P01. | Manutenção ou ajuste do realce de frases de abuso (gaslighting, chantagem). | alta |
| H01 | Vítimas de violência psicológica preferem o envio direto de blocos de texto/áudio via WhatsApp a preencher formulários longos. | Entrevistas informais prévias com acolhedores do suporte emergencial. | Arquitetura de interação do chatbot vs. interfaces tradicionais. | média |

## Parte A — necessidades e requisitos de IHC

> **Responsabilidade:** solução individual por integrante.

### A01 — Laura de Souza Parente

**Autor(a):** Laura de Souza Parente — 22.123.033-7

#### Que dados coletar?

| Dado/informação | Hipótese/lacuna relacionada | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Tempo médio de análise e nível de confiança do auditor | H01, H02 | Avaliar se a explicabilidade RAG reduz o esforço cognitivo. | Disposição visual do card do RAG na tela de auditoria (P02). |
| Frequência de reclassificação manual de risco | H01 | Medir a margem de erro percebida pelo humano sobre a IA. | Necessidade de um campo de observações obrigatório ao reclassificar. |
| Clareza na diferenciação entre níveis de risco (Alto, Médio, Baixo) | H02 | Validar se as métricas KPI e os filtros rápidos da P01 satisfazem a triagem diária. | Ajuste de cores, rótulos e disposição dos filtros na listagem mestre. |


#### De quem coletar?

| Perfil/stakeholder | Critério de inclusão | Relação com persona/público |
|---|---|---|
| Analistas / Auditores de Atendimentos | Profissionais ou voluntários que atuam na triagem de casos de apoio a mulheres vítimas de violência. | Corresponde diretamente à Persona Camila Rocha (P01). |
| Especialistas em Direitos Humanos e Apoio Social | Profissionais com experiência no enquadramento de violência psicológica (Art. 147-B). | Stakeholders de validação do enquadramento jurídico RAG. |

#### Aspectos éticos

Analise voluntariedade, consentimento, minimização de dados, privacidade, riscos, gravação, anonimização, armazenamento e descarte. Não responda apenas “sim, por causa da LGPD”: explique **quais dados e riscos existem neste projeto**.

- Voluntariedade e Consentimento: Todos os participantes assinarão um Termo de Consentimento Livre e Esclarecido (TCLE) informando a voluntariedade e a possibilidade de desistência a qualquer momento sem sanções.

- Privacidade e Anonymização: A recolha não solicitará nem armazenará dados pessoais sensíveis das vítimas reais. Todos os históricos de mensagens apresentados nos testes utilizarão cenários fictícios elaborados para fins académicos com identificadores mascarados (#C001).
  
- Minimização de Dados: Serão recolhidos estritamente os dados de usabilidade (tempo de tarefa, cliques, respostas de utilidade) e perfil profissional sintético.
  
- Armazenamento e Descarte: Os dados recolhidos serão mantidos em repositório privado encriptado até à conclusão e defesa do TCC, sendo posteriormente eliminados em definitivo

> Repita A02, A03...

## Parte B — ferramentas de coleta

> Cada integrante deve preparar uma técnica/instrumento completo. As técnicas devem ser diferentes entre si e **questionário deve estar entre as técnicas escolhidas**, conforme o enunciado da disciplina.

### Instrumento I01 — Questionário de Avaliação de Usabilidade e Explicabilidade RAG

**Autor(a):** Laura de Souza Parente — 22.123.033-7
**Técnica:** Questionário (Google Forms / Formulário Estruturado)  
**Objetivo:** Mensurar a perceção dos profissionais de análise quanto à clareza das métricas do painel, eficácia do filtro de risco e utilidade da fundamentação RAG baseada no Art. 147-B.  
**Público:** Profissionais e voluntários da área de acolhimento social e auditoria de dados.

#### Procedimento padronizado de aplicação

1. Preparação:  Disponibilização do link do formulário eletrónico acompanhado dos cenários de teste simulados e do protótipo P01.
2. Apresentação/consentimento: Apresentação do objetivo académico do estudo e recolha do consentimento digital (TCLE) na primeira secção.
3. Aplicação: O participante visualiza as telas de simulação e responde às questões organizadas em Likert de 5 pontos e questões abertas.
4. Encerramento: Agradecimento e recolha de comentários adicionais facultativos.
5. Armazenamento/anonimização: Exportação das respostas para formato CSV sem registo de e-mail ou IP dos respondentes.

#### Instrumento

Cole aqui o questionário/roteiro completo ou forneça link **mais uma cópia textual no repositório**.

```text
Secção 1: Consentimento e Perfil Profissional

1. Você concorda em participar voluntariamente dessa pesquisa academica de IHC?
[ ] Sim, concordo com os termos.
[ ] Não concordo.

2. Qual a sua área de atuação principal?
( ) Direitos Humanos / Assistência Social
( ) Direito / Área Jurídica
( ) Tecnologia / Análise de Dados
( ) Outro: __________

Secção 2: Triagem e Visualização Mestre (Tela P01)

1. Os cartões de indicadores no topo da tela (Total de Casos, Alto Risco, Categoria Frequente) ajudam a priorizar o trabalho diário?
- Escala de 1 (Discordo Totalmente) a 5 (Concordo Totalmente).
  
2. A visualização da proporção de mensagens processadas (ex: 28/30) é suficiente para avaliar a gravidade do caso antes de abri-lo?
- Escala de 1 (Discordo Totalmente) a 5 (Concordo Totalmente).

3. Qual a sua percepção sobre o uso do código anônimo (#C001) em vez do nome da vítima na listagem principal?
  ( ) Essencial para a privacidade.
  ( ) Adequado.
  ( ) Indiferente.
  ( ) Dificulta a identificação.

Secção 3: Explicabilidade Legal (Módulo RAG)

1. A citação direta do Art. 147-B do Código Penal juntamente com a justificativa da IA aumenta sua confiança no veredito?
  - Escala de 1 (Pouquíssima Confiança) a 5 (Muita Confiança).

2. Ao discordar da classificação da IA, o botão "Reclassificar Risco" atende à necessidade de ajuste manual?
  - Escala de 1 (Não atende) a 5 (Atende perfeitamente).

Secção 4: Questões Abertas

1. Que informação adicional gostaria de ver no painel mestre para facilitar a sua decisão?
- Resposta curta de texto.
```

#### Como os dados serão analisados

{{ex.: distribuição de respostas, codificação temática, agrupamento de problemas}}

- Dados Quantitativos: Cálculo de médias, desvio padrão e percentuais das respostas nas escalas Likert para validar se a satisfação com a explicabilidade RAG atinge nota superior a 4,0.   
- Dados Qualitativos: Agrupamento temático das respostas abertas para derivar novos requisitos de interface para as iterações de alta fidelidade.

## Síntese

Explique quais lacunas de conhecimento sobre usuários o conjunto de técnicas pretende reduzir. Indique explicitamente quais hipóteses da Entrega 1 deverão ficar **sustentadas, refutadas ou refinadas** após a análise dos dados. Quando os dados forem coletados/analisados, atualize o histórico em `RASTREABILIDADE.md`.

O conjunto das técnicas de recolha propostas visa resolver as principais lacunas identificadas na Entrega 1, especificamente a validação sobre se a explicabilidade RAG (Art. 147-B) atende à necessidade real dos analistas de auditoria sem gerar sobrecarga cognitiva.

- Sustentar H01: Confirmando que a fundamentação jurídica aumenta a confiança do auditor na IA.

- Refinar H02: Ajustando a forma de exibição dos filtros e a proporção das mensagens com base nos comentários dos profissionais.

- Refinar H03: Confirmando a viabilidade da triagem via identificadores anónimos sem prejuízo à auditoria.

## Checklist

- [X] Hipóteses/lacunas prioritárias da Entrega 1 foram revisitadas.
- [X] Se o escopo de IHC foi derivado de TCC técnico, a coleta investiga a plausibilidade do usuário, tarefa e contexto adotados.
- [X] Perguntas não pressupõem que dashboard, CRUD, filtros ou relatórios sejam necessários; investigam a necessidade.
- [X] Cada dado a coletar responde uma dúvida concreta do projeto ou justifica outra necessidade de informação.
- [X] Parte A identifica dados e perfis de coleta de forma específica.
- [X] Aspectos éticos são contextualizados para o projeto.
- [X] Há uma técnica completa por integrante e técnicas distintas.
- [X] Questionário está incluído entre as técnicas.
- [X] Cada instrumento possui objetivo, público, procedimento e conteúdo integral.
- [x] Perguntas evitam indução e coletam apenas dados necessários.
- [X] Está claro como os dados serão analisados e usados no design.
