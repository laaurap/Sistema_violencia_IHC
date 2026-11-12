# Entrega 1 — Conhecendo o projeto, o usuário e o problema

**Data:** 13/08/2026 (Revisado em 12/11/2026)
**Status:** 🟩 concluída  
**Responsabilidade:** 1 solução consolidada por equipe

## Objetivo da atividade

Reinterpretar o tema do TCC sob a perspectiva de Interação Humano-Computador e construir um **entendimento comum entre os integrantes da equipe**.

A disciplina utiliza preferencialmente o tema do TCC para os exercícios de IHC. Isso vale tanto para TCCs que já preveem uma interface quanto para trabalhos cujo resultado principal é algoritmo, modelo, API, biblioteca, análise de dados, infraestrutura, estudo experimental ou outro artefato técnico.

> **Importante:** a interface projetada na disciplina é um artefato de aprendizagem de IHC. Ela **não se torna automaticamente uma obrigação do TCC**. Sua incorporação ao trabalho de conclusão depende de decisão da equipe e do orientador.

Antes de preencher, leia [`../GUIA_ESCOPO_IHC.md`](../GUIA_ESCOPO_IHC.md).

Nesta primeira semana a equipe **não deve começar desenhando telas**. Primeiro deverá compreender:

- o que o TCC realmente produz;
- quem poderia obter valor dessa contribuição;
- quais pessoas interagem, administram, configuram, interpretam ou são afetadas;
- o que essas pessoas precisam alcançar;
- como atividades relacionadas acontecem hoje;
- problemas, limitações e contexto;
- alternativas existentes;
- qual recorte de interação fará sentido para a disciplina.

Ao final desta entrega, a equipe deve diferenciar:

- **tema do TCC** × **escopo formal do TCC** × **escopo de IHC da disciplina**;
- **objetivo do projeto** × **objetivo do usuário**;
- **problema do usuário** × **solução tecnológica**;
- **fato conhecido** × **hipótese** × **lacuna de conhecimento**;
- **capacidade técnica** × **forma de uso dessa capacidade**;
- **funcionalidade** × **atividade/resultado que o usuário precisa alcançar**;
- **usuário direto** × **stakeholders**.

---

## Como classificar as respostas

Sempre que a resposta fizer uma afirmação sobre usuários, problemas, atividades, necessidades, contexto ou mercado, use:

- **[F] Fato conhecido** — existe evidência/fonte.
- **[H] Hipótese** — afirmação plausível que ainda precisa ser investigada.
- **[?] Não sabemos ainda** — lacuna relevante.

Quando usar `[F]`, informe a origem. Hipóteses prioritárias devem receber IDs (`H01`, `H02`...) e também ser registradas em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

> **Exemplo:** `[H] H01 — DBAs considerariam útil comparar automaticamente o plano atual de execução com uma recomendação produzida pelo algoritmo.`

Uma hipótese explicitada é melhor do que uma suposição escondida.

---

# 0. Identificação do TCC e da equipe

## 0.1 Membros

| Nome completo | Matrícula | GitHub |
|---|---:|---|
| Laura de Souza Parente | 22.123.033-7 | laaurap |

## 0.2 Título atual do TCC

Sistema de Detecção de Violência Psicológica em Conversas

## 0.3 Orientador(a)

Prof. Dr. Victor Perrone de Lima Varela

## 0.4 Qual é o resultado principal atualmente previsto no TCC?

Marque e descreva:

- [X] sistema/aplicação interativa;
- [ ] algoritmo;
- [X] modelo de IA/ML/LLM;
- [X] biblioteca/API/framework;
- [ ] análise de dataset;
- [ ] estudo/benchmark/avaliação experimental;
- [ ] infraestrutura/backend;
- [ ] componente embarcado/IoT;
- [ ] outro: {{...}}.

**Descrição:** `[F — Escopo formal do TCC]` O TCC produz um pipeline de processamento de linguagem natural que identifica indícios de violência psicológica em texto (digitado ou transcrito de áudio). A vítima encaminha ao chatbot, via WhatsApp, uma mensagem ou trecho de conversa recebido do possível agressor; o sistema processa o conteúdo, classifica os indícios encontrados, fundamenta o resultado com referências legais/acadêmicas (como o Art. 147-B do Código Penal) e devolve uma orientação preliminar individual à vítima.
Tecnicamente, o pipeline combina transcrição com Faster Whisper, pré-processamento com spaCy, classificação com modelo BERT multilíngue, RAG para recuperação de referências, API HTTP em FastAPI e integração por Twilio/n8n para o WhatsApp. Para a disciplina de IHC, foi concebida uma camada complementar de interface web administrativa (não prevista para implementação no TCC) destinada à auditoria e acompanhamento agregado das análises.

## 0.5 O TCC já previa desenvolvimento de interface com usuário?

- [ ] Sim, a interface já faz parte do TCC.
- [X] Parcialmente; existe alguma interação, mas ainda não está bem definida.
- [ ] Não. O TCC é predominantemente técnico e não previa interface.

**Explique o que está formalmente previsto no TCC:** `[F — Escopo formal do TCC]` No escopo formal do TCC, existe apenas a interação conversacional via WhatsApp (Twilio), na qual a vítima encaminha uma mensagem ou conversa suspeita recebida do possível agressor e recebe a análise preliminar individual do conteúdo. **O painel administrativo web não será implementado no TCC** — ele foi definido como extensão conceitual e prototipado exclusivamente para a disciplina de IHC, por concentrar maior variedade de tarefas de triagem, visualização de métricas, busca, filtragem, explicabilidade de IA (*human-in-the-loop*) e interpretação de dados sensíveis. O fluxo da vítima pelo WhatsApp continua fazendo parte do ecossistema do projeto apenas como contexto e origem externa dos dados exibidos no painel.

> Esta resposta serve para separar o compromisso do TCC do projeto da disciplina. Mesmo quando a opção for **não**, a equipe irá definir uma interface para exercitar IHC.

---

# 1. Entendendo a contribuição do projeto

## 1.1 Explique o TCC em uma frase, sem citar linguagem de programação, framework ou banco de dados.

O TCC analisa mensagens e conversas para identificar possíveis indícios de violência psicológica, devolve uma orientação preliminar fundamentada à vítima e organiza os resultados anonimizados em uma interface administrativa conceitual (explorada em IHC) para auditoria humana e análise de padrões.

## 1.2 Qual situação, atividade ou problema do mundo real motivou o TCC?

`[H]` Pessoas que vivenciam violência psicológica podem ter dificuldade de reconhecer que determinados comportamentos configuram abuso e, consequentemente, de decidir quando buscar ajuda ou se afastar da situação. Simultaneamente, em cenários de uso institucional ou supervisão de ferramentas de triagem automatizada, analistas responsáveis pelo acompanhamento enfrentam dificuldade para auditar a confiabilidade das classificações da IA e extrair visão consolidada a partir de registros isolados.

## 1.3 Qual é a **capacidade/contribuição central** produzida pelo TCC?

Complete, se ajudar:

> “Nosso TCC produz, melhora, analisa ou permite **classificar automaticamente indícios e categorias de violência psicológica em um texto de conversa, e fundamentar essa classificação preliminar com referências legais/acadêmicas recuperadas por similaridade semântica**.”

Exemplos: otimizar consultas; classificar imagens; detectar anomalias; comparar modelos; identificar padrões; prever demanda; analisar desempenho; gerar resumos; recomendar configurações.

Classificar automaticamente indícios e categorias de violência psicológica em uma conversa e apresentar uma justificativa preliminar fundamentada em referências legais e acadêmicas recuperadas pelo sistema.

## 1.4 O que se espera que esteja diferente **para pessoas, organizações ou processos** se essa contribuição for bem-sucedida?

`[F — Definição de escopo da disciplina]` Para a disciplina de IHC, projeta-se uma camada web administrativa que separa o atendimento imediato (WhatsApp, escopo do TCC) da camada de auditoria e acompanhamento agregado (painel administrativo, recorte de IHC).

`[H] H01` — Analistas de triagem e auditoria conseguirão localizar casos críticos e revisar classificações preliminares da IA com apoio de explicabilidade legal (RAG), corrigindo eventuais divergências e consolidando indicadores sem depender de inspeção manual em logs brutos.

`[H] H02` — A vítima teria acesso a um mecanismo externo e de baixa fricção para encaminhar ao chatbot uma mensagem ou conversa suspeita e obter uma primeira leitura fundamentada sobre possíveis indícios de violência psicológica, auxiliando-a a identificar sinais de alerta e canais de apoio.

## 1.5 O que é mérito técnico/científico do TCC e o que seria uma possível aplicação prática?

| Mérito/contribuição técnica | Possível aplicação/valor em uso |
|---|---|
| Classificação automática de indícios e categorias de violência psicológica em texto/transcrição | Oferecer à vítima uma avaliação inicial preliminar sobre uma conversa suspeita via WhatsApp (escopo do TCC) |
| Fundamentação do resultado por meio de RAG com referências legais/acadêmicas (Art. 147-B) | Tornar a classificação explicável e auditável, permitindo verificar os critérios que motivaram o alerta |
| Exposição do pipeline por API e integração com WhatsApp | Permitir que a capacidade técnica seja acessada por um canal já familiar ao usuário |
| Consolidação, auditoria humana (*human-in-the-loop*) e visualização de dados agregados (recorte de IHC) | Permitir à analista validar a qualidade das classificações e acompanhar indicadores, categorias recorrentes e evolução temporal |

---

# 2. Entendendo as pessoas envolvidas

## 2.1 Quem interage diretamente com o produto, se já existe interface prevista?

Se não houver interface prevista no TCC, escreva `NÃO SE APLICA AO ESCOPO ORIGINAL` e prossiga para 2.2.

`[F — Implementação atual do TCC]` Hoje, o único ponto de interação implementado no TCC é o próprio WhatsApp: a pessoa envia uma mensagem de texto ou um áudio para o número do bot (Twilio) e recebe de volta uma mensagem automática com o resultado preliminar da análise. O painel administrativo web não faz parte da entrega técnica do TCC, sendo projetado conceitualmente na disciplina de IHC.

## 2.2 Quem poderia **usar, configurar, administrar, operar, interpretar ou tomar decisões** a partir da contribuição técnica?

Considere perfis profissionais e stakeholders, não apenas consumidores finais.

| Perfil | Relação com a contribuição | O que faria | Status/evidência |
|---|---|---|---|
| {{DBA / analista / gestor / técnico / pesquisador / usuário final...}} | {{...}} | {{...}} | F / H / ? |
| **Analista de Triagem e Auditoria** *(Perfil priorizado em IHC)* | Usuária direta da interface web administrativa projetada em IHC | Atua em contexto institucional/de pesquisa ou supervisão de qualidade do serviço. Consulta dashboard, histórico e conversas anonimizadas (`#ID`); aplica filtros por risco; confronta mensagens com o parecer RAG da IA; aprova ou reclassifica o nível de risco mediante justificativa; e exporta relatórios consolidados. **Limites de atuação:** não realiza diagnóstico clínico nem emite laudo pericial judicial; sua decisão restringe-se à validação da qualidade da triagem do sistema e consolidação estatística. | `[F]` (perfil definido no recorte de IHC) / `[H]` (rotina operacional detalhada a investigar) |
| Vítima (usuária final) | Usuária direta do chatbot no TCC (contexto de origem dos dados) | Envia texto/áudio suspeito no WhatsApp, lê a orientação preliminar e decide se busca rede de apoio | `[F]` (fluxo existente no TCC) / `[H]` (compreensão e uso a investigar) |
| Profissional de rede de apoio (Psicóloga / Assistente Social) | Pode receber relatórios estatísticos ou acolher usuárias encaminhadas | Auxilia na interpretação da situação e nos próximos passos de acolhimento | `[H]` |
| Responsável técnico pelo sistema | Mantém e configura a solução técnica do TCC | Atualiza integrações, modelos, limiares de confiança, base de referência RAG e políticas de anonimização | `[F]` (papel técnico do TCC) |

## 2.3 Existem pessoas afetadas que não usariam a interface diretamente?

| Stakeholder | Como é afetado | Usa interface? | Status/evidência |
|---|---|---|---|
| Interlocutor / Suposto Agressor | Autor das mensagens encaminhadas pela usuária ao sistema para análise. Seus textos são processados e armazenados de forma anonimizada (`#ID`), exigindo rigor ético e conformidade com a LGPD para evitar exposição indevida ou interpretação punitiva automatizada. | Não | `[F]` (fluxo de dados do sistema) |
| CVV / Ligue 180 / rede de apoio a vítimas | Recebe encaminhamento indireto (a pessoa busca contato após o alerta do chatbot) | Não | `[H]` |

## 2.4 Que características desses perfis podem influenciar a interação?

Considere conhecimento do domínio, experiência tecnológica, frequência de uso, necessidades de acessibilidade, responsabilidade profissional, familiaridade com métricas, linguagem técnica, urgência etc.

`[H]` **Analista de Triagem e Auditoria (usuário priorizado em IHC):** Possui familiaridade básica com sistemas web administrativos e conhecimento conceitual sobre violência psicológica (Art. 147-B), mas **não é especialista em Machine Learning**. Precisará lidar com uma quantidade maior de registros e tomar decisões de navegação e interpretação a partir de dados agregados e evidências textuais. A interface deve favorecer leitura rápida de indicadores, filtros claros, busca eficiente e explicabilidade compreensível dos *scores* da IA. Como os dados tratados são sensíveis, também são relevantes controle de acesso, anonimização (`#ID`), rastreabilidade das revisões e diferenciação entre informação agregada e conteúdo detalhado das conversas.

`[H]` **Vítima (contexto de origem dos dados):** Pode estar emocionalmente vulnerável, com medo, vergonha ou dúvida sobre a própria percepção; precisa de discrição e privacidade máxima no celular, o que impede a coleta de dados pessoais identificáveis (nome, telefone, localização) que alimentariam o painel.

---

# 3. Entendendo objetivos e atividades

## 3.1 O que o usuário está tentando conseguir no mundo real?

Não responda “usar o algoritmo”, “clicar no sistema” ou “ver o dashboard”.

**Analista de Triagem e Auditoria (usuário priorizado em IHC):** Garantir que as triagens automatizadas realizadas pelo sistema sejam confiáveis e coerentes com o enquadramento de violência psicológica (Art. 147-B), localizar rapidamente casos críticos que exigem revisão humana e consolidar panoramas estatísticos claros sobre os tipos de abuso mais recorrentes sem violar a privacidade das pessoas atendidas.

`[H]` **Vítima (contexto):** Entender se o que está vivendo em mensagens configura indícios de violência psicológica, para poder tomar uma decisão informada sobre buscar ajuda, se proteger ou conversar sobre o assunto com alguém de confiança.

## 3.2 Quais são as atividades mais importantes?

| ID | Atividade/objetivo | Quem realiza | Frequência/criticidade inicial | Status/evidência |
|---|---|---|---|---|
| A01 | *(Dependência externa do ecossistema — escopo TCC)* Enviar ao chatbot uma mensagem ou conversa suspeita para análise | Vítima | Pontual / alta criticidade | `[F]` (implementado no TCC) |
| A02 | *(Dependência externa do ecossistema — escopo TCC)* Ler e interpretar a orientação preliminar individual | Vítima | Ocorre junto com A01 / alta criticidade | `[H]` |
| A03 | Monitorar indicadores gerais de volume, risco e categorias predominantes do sistema | Analista de Triagem e Auditoria | Frequente (esperada) / média criticidade | `[H]` (frequência a validar) |
| A04 | Consultar, filtrar e localizar atendimentos no histórico por risco, período ou código anônimo (`#ID`) | Analista de Triagem e Auditoria | Frequente (esperada) / alta criticidade | `[H]` (frequência a validar) |
| A05 | Abrir e auditar o detalhe de uma conversa/parecer RAG, aprovando ou reclassificando o nível de risco | Analista de Triagem e Auditoria | Conforme demanda / **altíssima criticidade** | `[H]` |
| A06 | Avaliar métricas de concordância do modelo e exportar relatórios consolidados | Analista de Triagem e Auditoria | Periódica / média criticidade | `[H]` |

## 3.3 Qual atividade parece mais frequente? Por quê?

`[H]` Para o usuário priorizado em IHC, estima-se que as atividades mais frequentes sejam **A03** e **A04**: consultar uma visão geral e navegar pelo histórico usando filtros por nível de risco. Elas funcionam como ponto de entrada para decidir quando aprofundar uma auditoria em **A05** ou gerar relatórios em **A06**. A frequência real deverá ser validada em etapas posteriores com participantes representativos.

## 3.4 Qual parece mais crítica? Que consequência existe se for mal executada?

`[H]` **A05** — auditar o detalhe de uma conversa/parecer da IA é a atividade administrativa mais crítica, porque uma interpretação incorreta ou aceitação acrítica (viés de automação) pode validar classificações equivocadas e distorcer os relatórios de qualidade do sistema. **A03** e **A06** também exigem cuidado: visualizações agregadas mal apresentadas podem induzir a confundir o volume de análises realizadas no bot com a prevalência real de violência psicológica na população. Para a vítima (contexto), **A02** continua altamente crítica, pois a comunicação do resultado preliminar não pode gerar falsa sensação de segurança nem alarme indevido.

---

# 4. Entendendo o problema ou processo atual

## 4.1 Como essas atividades são realizadas hoje, antes da interface imaginada na disciplina?

Pode existir software concorrente, linha de comando, planilha, notebook, script, painel técnico, processo manual, consulta a logs, análise visual, troca de mensagens, decisão por especialista etc.

`[F — Estado atual do TCC]` Atualmente, o pipeline do TCC gera saídas individuais via API/WhatsApp e as registra em arquivos/logs técnicos no servidor, sem uma interface web consolidada para exploração.

`[H]` Para a Analista de Triagem e Auditoria, realizar revisão de qualidade sem um painel dedicado exigiria inspecionar logs brutos, planilhas exportadas manualmente ou saídas isoladas em JSON/banco, dificultando filtrar casos de alto risco, ler o diálogo cronológico lado a lado com as citações legais do RAG ou registrar justificativas de reclassificação de forma rastreável.

`[H]` Para a vítima (contexto), o reconhecimento de violência psicológica costuma depender de autopercepção, conversas com pessoas de confiança, acompanhamento profissional ou conteúdos educativos dispersos.

## 4.2 O que é difícil, demorado, confuso, repetitivo, arriscado ou pouco transparente?

`[H]` **Para a Analista:** Consolidar dezenas de registros individuais manualmente é demorado e repetitivo; ler textos brutos sem destaque visual das frases sinalizadas pela IA torna a auditoria cansativa; e manipular planilhas soltas aumenta o risco de exposição indevida de conteúdo sensível (LGPD) ou perda de rastreabilidade das revisões humanas.

`[H]` **Para a vítima (contexto):** A principal dificuldade é reconhecer e nomear o possível abuso sutil no cotidiano.

## 4.3 Que informações o profissional precisa interpretar para tomar decisão?

`[F — Estrutura de saída do pipeline]` **No nível individual (auditoria de caso):** Código anônimo do atendimento (`#ID`), data/hora, transcrição cronológica das mensagens enviadas pelo interlocutor, trechos destacados com alerta, nível de risco preliminar (`ALTO`, `MÉDIO`, `BAIXO`), categoria predominante (ex.: manipulação emocional, humilhação, ameaça, isolamento social), grau de confiança do modelo e fundamentação jurídica associada (Art. 147-B).

`[H]` **No nível agregado (gestão e relatórios):** Quantidade de análises no período, distribuição por nível de risco e categoria, status de auditoria (`Pendente`, `Aprovado`, `Reclassificado`) e taxa de concordância humana. Esses indicadores devem ser apresentados de forma que não confundam volume de análises realizadas com prevalência real de violência psicológica na população.

`[?]` **Lacunas sobre indicadores e localização:** Ainda é necessário precisar a unidade de contagem nos gráficos (se cada registro representa uma *sessão de atendimento* ou uma *mensagem individual*) e registrar que **dados geográficos não serão exibidos** no painel, pois o WhatsApp não coleta localização confiável e exibir mapas violaria a minimização de dados sensíveis (LGPD).

## 4.4 O que acontece quando a atividade falha ou quando o resultado é interpretado incorretamente?

`[H]` **No âmbito administrativo (foco de IHC):** Se a analista interpretar o *score* de confiança da IA (`94%`) ou o rótulo de risco como uma "sentença jurídica definitiva" em vez de um *indício preliminar de triagem*, os relatórios consolidados perderão rigor técnico. Além disso, se a interface dificultar a localização ou a reclassificação de casos divergentes, erros sistemáticos do modelo NLP (falsos positivos ou falsos negativos) deixarão de ser corrigidos.

`[H]` **No âmbito da vítima (contexto):** Um falso negativo pode reforçar a sensação de que "não é nada demais", atrasando a busca por ajuda numa situação real. Um falso positivo pode gerar alarme desnecessário, confusão ou fazer a pessoa duvidar da credibilidade da ferramenta em usos futuros.

## 4.5 Conte uma situação concreta.

Escreva uma pequena narrativa com pessoa, objetivo, atividade, contexto, dificuldade e consequência. **Não descreva ainda a futura solução.**

`[H]` **Situação 1 — Perfil priorizado (Analista de Triagem e Auditoria):** Camila, 32 anos, atua como analista responsável por auditar a qualidade das triagens de um projeto piloto de apoio psicossocial que utiliza o sistema automatizado. No início da semana, ela precisa revisar os atendimentos classificados como alto risco nos últimos dias para verificar se o modelo enquadrou corretamente as mensagens no Art. 147-B e preparar um relatório mensal para a coordenação. Sem uma interface consolidada, ela recebe uma exportação bruta com dezenas de linhas de texto sem formatação, sem filtro por status de revisão e com as referências legais separadas das mensagens. Para cada caso, Camila precisa cruzar manualmente o texto da conversa com o parecer da IA, anotar suas discordâncias em uma planilha paralela e contabilizar à mão quantos casos foram validados — um processo lento, cansativo e sujeito a falhas de rastreabilidade.

`[H]` **Situação 2 — Contexto do ecossistema (Vítima):** Uma jovem de 24 anos troca mensagens diárias com o parceiro. Ao longo dos meses, ele passa a questionar suas saídas, dizer que ela "inventa coisas" quando discordam sobre o que foi dito antes, e chamá-la de "dramática" quando ela expressa desconforto com esse padrão. Isoladamente, cada conversa parece só mais uma discussão de casal — ela nunca ouviu falar em "gaslighting" e não tem certeza se o que sente é exagero seu ou algo mais sério. Ela não conversa sobre isso com ninguém, por vergonha de estar "fazendo tempestade em copo d'água".

## 4.6 Que evidência existe hoje?

| Evidência/fonte | O que sustenta | Limitação |
|---|---|---|
| {{...}} | {{...}} | {{...}} |
| **Código e arquitetura atual do TCC** (`api.py`, `analyzer.py`, `rag.py`, `transcriber.py`) `[F]` | Comprova a existência da entrada por texto/áudio no WhatsApp e da saída estruturada com risco, categorias e fundamentação no Art. 147-B | Não contém validação de usabilidade ou compreensão humana com usuários reais |
| **Formulário IAVP (Indicadores de Avaliação de Violência Psicológica — Ministérios Públicos / CNMP)** `[F]` | Há um instrumento institucional de triagem relacionado à mesma base legal (Art. 147-B), preenchido por profissional humano | Não realiza a mesma análise automatizada de conversas proposta pelo TCC |
| **Lei nº 14.188/2021 (Art. 147-B do Código Penal) e Lei nº 11.340/2006 (Lei Maria da Penha)** `[F]` | Fundamentam as categorias de abuso emocional e enquadramento legal recuperadas pelo RAG | Linguagem jurídica densa exige tradução clara para uso cotidiano na interface |
| **Lumira, Be Safe Mulher, Rede Mulher e Instituto Glória** `[F]` | Existem soluções/análogos que atuam em necessidades próximas do domínio de apoio à mulher | Focam na usuária final (vítima), não revelando convenções de interfaces administrativas de auditoria (investigados na Entrega 2) |

---

# 5. Entendendo o contexto de uso

## 5.1 Onde e em quais situações a interação poderia ocorrer?

`[H]` **Analista de Triagem e Auditoria:** Em ambiente de trabalho institucional, escritório ou home office, utilizando a interface web durante turnos regulares de revisão de qualidade, auditoria de casos críticos e fechamento de relatórios.

`[F]` (dispositivo/canal) / `[H]` (contexto emocional) **Vítima (contexto):** No próprio celular, dentro do WhatsApp, possivelmente em momento privado e emocionalmente sensível, após receber uma mensagem ou participar de uma conversa suspeita.

## 5.2 Em quais dispositivos/equipamentos?

`[H]` **Painel administrativo:** Será prioritariamente utilizado em computador/notebook (resolução padrão Desktop `1440 × 1024 px`), por exigir leitura de tabelas, filtros simultâneos, gráficos e visualização lado a lado (*split-screen*) entre transcrição e fundamentação RAG.

`[F]` **Chatbot:** A vítima utiliza principalmente smartphone via WhatsApp.

## 5.3 Existem condições físicas relevantes?

Considere iluminação, ruído, mobilidade, conexão, privacidade, uso compartilhado, interrupções, pressão de tempo etc.

`[H]` **Para a Analista:** São importantes conforto visual em sessões prolongadas (como tema escuro / *Dark Mode* com bom contraste), densidade de informação controlada e capacidade de alternar entre visão agregada e detalhe sem perder contexto. Como há conteúdo emocionalmente sensível, a interface deve evitar exposição desnecessária de conversas completas na tela inicial caso o ambiente seja compartilhado.

`[H]` **Para a vítima (contexto):** Privacidade e discrição são críticas, pois o agressor pode ter acesso ao aparelho ou às notificações.

## 5.4 Existem fatores sociais ou organizacionais?

Considere papéis, chefias, equipes, permissões, aprovação, responsabilidade profissional, auditoria, turnos e colaboração.

`[H]` O painel administrativo pressupõe perfis autorizados. Portanto, controle de acesso, anonimização de registros (`#ID`), responsabilidade sobre dados sensíveis (LGPD), rastreabilidade das revisões e exigência de justificativa escrita ao reclassificar um parecer da IA são fatores organizacionais relevantes. A vítima não faz parte dessa estrutura administrativa.

## 5.5 Existe necessidade de histórico, rastreabilidade ou auditoria?

`[F — Requisito do recorte de IHC]` Sim. O histórico é uma necessidade explícita do painel administrativo: a analista autorizada deverá consultar análises anteriores, localizar registros, aplicar filtros e abrir detalhes para auditoria.

`[H]` Também é necessário registrar o status do ciclo de revisão (`Pendente`, `Aprovado`, `Reclassificado`) e a justificativa da analista quando alterar o nível de risco sugerido pela IA. Para a vítima, a persistência do histórico no WhatsApp continua sendo uma questão de privacidade distinta.

## 5.6 Um erro pode produzir consequência relevante? Qual?

`[H]` Sim. No painel administrativo, interpretar uma classificação preliminar da IA como verdade absoluta (sem verificar as mensagens e o contexto) pode gerar relatórios imprecisos e mascarar falhas do modelo. No fluxo da vítima, um falso negativo pode deixar de alertar uma pessoa em risco e um falso positivo pode gerar alarme desnecessário e perda de confiança na ferramenta.

---

# 6. Entendendo mercado e alternativas existentes

> Nesta entrega faça apenas um **levantamento inicial**. A análise aprofundada ocorre na Entrega 2.

## 6.1 Como pessoas resolvem problemas semelhantes hoje?

| Alternativa atual | Quem usa | Para quê | Status/evidência |
|---|---|---|---|
| Planilhas eletrônicas e inspeção manual de logs | Equipes técnicas / analistas de projetos piloto | Conferir saídas de modelos de IA e contabilizar categorias manualmente | `[H]` |
| Atendimento psicológico / Triagem presencial (IAVP) | Pessoas que suspeitam de abuso e profissionais de redes de apoio | Diagnóstico, acolhimento e acompanhamento profissional | `[F]` (IAVP) / `[H]` (uso geral) |
| Linha CVV / Ligue 180 | Pessoas em crise emocional ou situação de violência | Suporte emocional imediato e orientação | `[F]` (serviços públicos reais já referenciados no sistema) |

## 6.2 Existem produtos que atuam na mesma área, mesmo sem serem equivalentes ao TCC?

`[F]` Foram identificados como alternativas e produtos análogos do domínio: **Lumira**, **Be Safe Mulher**, **Rede Mulher** e **Instituto Glória**, além do instrumento institucional **IAVP** dos Ministérios Públicos (que utiliza a mesma base legal do Art. 147-B em triagem presencial). Essas soluções não são equivalentes ao TCC, pois concentram-se na autoavaliação ou atendimento direto à vítima, sem oferecer um painel administrativo de auditoria explicável (*RAG + Human-in-the-Loop*) sobre conversas classificadas por IA.

## 6.3 Quais interfaces profissionais esse público já conhece?

Exemplos possíveis: ferramentas de banco, IDEs, consoles de nuvem, dashboards, plataformas de dados, ferramentas de monitoramento, painéis de IA, sistemas administrativos.

`[H]` Para o perfil de Analista de Triagem e Auditoria, interfaces de dashboards analíticos, sistemas de gestão de filas/chamados, tabelas administrativas com filtros multifacetados e visualizadores de documentos lado a lado são referências relevantes. A Entrega 2 investigará produtos concretos representativos dessas tarefas (como plataformas de moderação/rotulagem de dados e sistemas administrativos de auditoria) para identificar convenções familiares.

## 6.4 O que essas soluções parecem fazer bem?

`[H]` Interfaces profissionais de análise organizam grande volume de informação em níveis progressivos: visão geral, filtros por severidade/status, lista/histórico e inspeção detalhada. Esse padrão é especialmente relevante para o painel proposto, pois a analista precisa primeiro perceber tendências e depois auditar casos específicos.

## 6.5 O que parecem fazer mal, dificultar ou não atender?

`[H]` Dashboards genéricos podem se tornar visualmente carregados, apresentar métricas sem conectar aos registros que as originaram ou exibir *scores* algorítmicos como "caixas-pretas" sem justificativa compreensível para profissionais não técnicos. Além disso, há o risco de expor conteúdo sensível demais na visão geral ou induzir a interpretar número de análises como prevalência real na população.

## 6.6 Que padrões de interface ou vocabulário parecem familiares a esse público?

`[?]` Padrões específicos de navegação, badges de status de auditoria e apresentação de explicabilidade de IA a investigar na Entrega 2.

---

# 7. Derivando o escopo de IHC da disciplina

## 7.1 Escolha o caminho do projeto

### Caminho A — TCC já possui interface

Explique qual parte da interface será usada como recorte da disciplina e por que esse fluxo é relevante.

`[F]` O projeto se enquadra no **Caminho A**, pois já existe uma interação conversacional implementada no TCC via WhatsApp. Como extensão conceitual para a disciplina de IHC (sem obrigação de implementação no TCC), o recorte concentrará o projeto de interação **exclusivamente em um painel web administrativo**, pois ele exige projetar tarefas complexas de triagem, visualização de indicadores, filtragem por risco, busca por código anônimo, auditoria *split-screen* com explicabilidade RAG e reclassificação humana (*human-in-the-loop*). O chatbot da vítima continuará sendo considerado apenas como contexto e origem externa dos dados exibidos no painel.

### Caminho B — TCC não possui interface prevista

`NÃO SE APLICA` (o projeto utiliza o Caminho A).

Faça o exercício de transferência de uso:

> **Imagine que o TCC foi concluído com sucesso e uma empresa, laboratório ou organização quer transformar a contribuição em algo utilizável. Quem precisaria interagir com ela e para quê?**

Responda:

1. quem poderia contratar/adotar a solução? `NÃO SE APLICA (Caminho A)`
2. quem seria o usuário direto? `NÃO SE APLICA (Caminho A)`
3. quem administraria/configuraria? `NÃO SE APLICA (Caminho A)`
4. quem interpretaria resultados? `NÃO SE APLICA (Caminho A)`
5. quem tomaria decisões? `NÃO SE APLICA (Caminho A)`
6. quais dados/entradas seriam necessários? `NÃO SE APLICA (Caminho A)`
7. quais resultados deveriam ser compreendidos? `NÃO SE APLICA (Caminho A)`
8. que erros/rupturas seriam possíveis? `NÃO SE APLICA (Caminho A)`

## 7.2 Qual perfil será priorizado no projeto de IHC?

**Analista de Triagem e Auditoria** (profissional autorizada responsável por revisar classificações preliminares da IA e acompanhar indicadores consolidados).

**Por que esse perfil foi escolhido?** Porque será o usuário direto da interface web projetada em IHC e executará tarefas que dependem fortemente de decisões de interação: compreender informação agregada sem viés, navegar entre visão geral e detalhe, aplicar filtros, confrontar evidências textuais com justificativas de IA (RAG) e registrar reclassificações humanas com segurança e privacidade.

A vítima continua sendo usuária direta do chatbot no TCC (WhatsApp), mas seus fluxos não serão o foco de modelagem e prototipação na disciplina.

## 7.3 Qual objetivo desse usuário será priorizado?

Inspecionar, validar ou reclassificar com precisão e segurança as classificações preliminares produzidas pela IA, além de acompanhar e exportar indicadores confiáveis sobre os indícios de violência psicológica identificados sem comprometer a privacidade das pessoas atendidas.

## 7.4 Que interface será explorada na disciplina?

Complete:

> **Para fins da disciplina de IHC, será projetada uma interface web administrativa que permita à `Analista de Triagem e Auditoria` utilizar `os resultados preliminares e referências legais (RAG) produzidos pelo sistema de detecção de violência psicológica` para `acompanhar indicadores gerais, filtrar atendimentos por risco, auditar transcrições lado a lado com o parecer da IA, reclassificar divergências e exportar relatórios consolidados`, no contexto de `uso profissional em computador/notebook com dados sensíveis anonimizados (LGPD) e necessidade de explicabilidade`.**

## 7.5 Qual é a relação dessa interface com o TCC?

- [ ] Já fazia parte do TCC.
- [ ] É um aprofundamento de algo parcialmente previsto.
- [X] É uma extensão conceitual criada para a disciplina.
- [ ] É um protótipo demonstrativo de aplicação potencial.
- [ ] Outra: {{...}}.

> **Declaração:** o painel administrativo foi concebido como uma camada complementar de auditoria e visualização exclusivamente para os exercícios de modelagem, prototipação e avaliação da disciplina de IHC, não integrando o escopo de implementação técnica do TCC.

---

# 8. Levantando possibilidades de interação — sem desenhar ainda

A equipe pode registrar possibilidades para investigação. **Não significa que todas serão implementadas.**

Marque apenas as que parecem plausíveis e explique o objetivo correspondente.

| Possibilidade | Pode fazer sentido? | Objetivo/tarefa que justificaria | Evidência atual |
|---|---|---|---|
| Dashboard/visão geral | **Sim (Recorte principal)** | Acompanhar rapidamente volume de análises, alertas de alto risco e categoria predominante (`A03`) | `[F]` — definido no recorte de IHC |
| Histórico com busca/filtros | **Sim (Recorte principal)** | Localizar análises anteriores por nível de risco (`ALTO`, `MÉDIO`, `BAIXO`) ou código anônimo `#ID` (`A04`) | `[F]` — definido no recorte de IHC |
| Explicabilidade/detalhamento (*Split-Screen*) | **Sim (Recorte principal)** | Confrontar mensagens sinalizadas com o enquadramento legal (Art. 147-B) e confiança da IA (`A05`) | `[F]` — valor central do RAG |
| Reclassificação humana (Modal *Human-in-the-Loop*) | **Sim (Recorte principal)** | Permitir corrigir o risco estimado pela IA mediante justificativa técnica obrigatória (`A05`) | `[H]` — mitiga viés de automação |
| Relatório/resultados e análises estatísticas | **Sim (Recorte principal)** | Acompanhar concordância IA × humano e exportar laudos consolidados em PDF/CSV (`A06`) | `[H]` |
| Configuração/parametrização | **Sim (Secundário)** | Ajustar limiares de sensibilidade da IA e políticas de anonimização LGPD | `[H]` |
| Usuários/perfis/permissões | **Sim (Restrição de acesso)** | Restringir acesso a dados sensíveis conforme perfil autorizado | `[H]` |
| Auditoria/logs | **Sim (Rastreabilidade)** | Registrar status de revisão (`Pendente`, `Aprovado`, `Reclassificado`) e justificativas | `[H]` |
| Entrada/upload/seleção de dados | **Fora do recorte de IHC** *(Dependência externa do TCC)* | Fluxo da vítima no WhatsApp que alimenta a base de dados do painel (`A01`) | `[F]` — já implementado no TCC |
| Acompanhamento de processamento | **Fora do recorte de IHC** *(Dependência externa do TCC)* | Feedback no WhatsApp enquanto o bot transcreve/analisa | `[H]` |
| Alertas/ocorrências | **Parcial (via badges/KPIs)** | Destacar registros de alto risco na tabela e nos cards, sem módulo separado | `[H]` |
| Ajuda/documentação | **Parcial (via notas LGPD/legais)** | Explicar critérios do Art. 147-B e limites da classificação preliminar da IA | `[H]` |
| Mapas geográficos | **Fora do recorte** | Descartado por privacidade (LGPD): o bot não coleta localização confiável | `[F]` — restrição de privacidade |
| CRUD genérico de entidade do domínio | **Fora do recorte** | Não se aplica: registros entram via fluxo automatizado anonimizado, sem cadastro manual | `[F]` — arquitetura do TCC |

> **Atenção:** “login + dashboard + CRUD” não é uma solução universal. Cada padrão deve surgir de uma tarefa real.

---

# 9. Benefícios e ações iniciais

## 9.1 Qual benefício concreto o projeto de IHC pretende oferecer?

| Benefício esperado | Problema/necessidade | Usuário | Status/evidência |
|---|---|---|---|
| Obter visão geral do funcionamento e dos resultados do sistema sem expor identidades | Registros isolados dificultam perceber tendências e exigem proteção de dados sensíveis | Analista de Triagem e Auditoria | `[H]` (`H04`) |
| Localizar e auditar rapidamente análises específicas com explicabilidade | Ler logs brutos sem contexto legal torna a revisão lenta e propensa a erros | Analista de Triagem e Auditoria | `[H]` (`H01`, `H03`) |
| Manter o fluxo individual de análise acessível como origem de dados | Dependência externa do TCC que alimenta o painel de forma discreta | Vítima (contexto) | `[F]` (implementado no TCC) |

## 9.2 Que ações o usuário deverá conseguir realizar?

| ID | O usuário precisa conseguir... | Para alcançar... | Prioridade inicial |
|---|---|---|---|
| F01 | Visualizar indicadores gerais no dashboard (`A03`) | Entender rapidamente o estado dos dados analisados (`H04`) | alta |
| F02 | Filtrar o conjunto de análises por risco (`ALTO`, `MÉDIO`, `BAIXO`) e pesquisar por `#ID` (`A04`) | Responder perguntas específicas e localizar casos críticos sem examinar todos os registros (`H01`) | alta |
| F03 | Abrir o detalhe de uma conversa/parecer RAG lado a lado (`A05`) | Avaliar as evidências textuais e a fundamentação legal da IA (`H03`) | alta |
| F04 | Aprovar o parecer da IA ou reclassificar o nível de risco com justificativa obrigatória (`A05`) | Validar a qualidade da triagem e registrar revisão humana (`H03`) | alta |
| F05 | Consultar métricas de desempenho do RAG e exportar relatórios consolidados (`A06`) | Acompanhar a acurácia do modelo e documentar resultados (`H04`) | média |
| *(Dep.)* | *(Dependência externa — fora do recorte de IHC)* Receber análises geradas pelo envio de mensagens da vítima no WhatsApp (`A01`, `A02`) | Alimentar a base de casos anonimizados do painel (`H02`) | dependência externa |

## 9.3 Tecnologias/restrições já definidas no TCC

A tecnologia aparece **agora**, depois do entendimento do uso.

| Tecnologia/restrição | Por que existe | Possível impacto na interação |
|---|---|---|
| Twilio/WhatsApp | Canal de entrada/saída externo da vítima no TCC | Alimenta o painel de forma assíncrona; não coleta dados identificáveis como nome ou localização |
| Transcrição de áudio (Faster Whisper) | Permite analisar mensagens de áudio encaminhadas | Eventuais imprecisões de transcrição exigem que a analista possa revisar o texto e reclassificar o caso |
| RAG com referências legais/acadêmicas (Art. 147-B) | Fundamenta tecnicamente o parecer preliminar | A justificativa deve ser exibida lado a lado com as mensagens sinalizadas em linguagem clara |
| Interface web administrativa (extensão conceitual IHC) | Permitir auditoria humana e exploração dos dados na disciplina | Exige arquitetura de informação limpa, filtros rápidos, visualizações sem viés e controle de acesso |
| Dados sensíveis de conversas e LGPD | O domínio envolve conteúdo potencialmente íntimo | Exige anonimização (`#C001`), ausência de mapas/dados pessoais e separação entre visão agregada e detalhe |
| FastAPI | Disponibiliza as funcionalidades do sistema por meio de API | A interface deve tratar estados de carregamento, busca sem resultados (vazio) e falhas de consulta |
| Classificação automatizada (BERT) | Produz os níveis de risco preliminares apresentados | A interface deve comunicar que o resultado é um *indício preliminar* (não sentença definitiva) e permitir correção humana |

---

# 10. Hipóteses e dúvidas prioritárias

| ID | Hipótese/dúvida | Por que importa | Como poderá ser investigada |
|---|---|---|---|
| **H01** | Analistas de triagem e auditoria conseguem localizar atendimentos específicos e filtrar casos de alto risco com rapidez utilizando busca por `#ID` e filtros de severidade, sem depender de logs brutos. | A localização ágil de registros críticos é uma das tarefas centrais do painel administrativo. | Testes de usabilidade com protótipos e tarefas cronometradas de busca e filtragem (Entregas 7 e 12–14). |
| **H02** | *(Contexto do ecossistema)* Usuárias do chatbot conseguem compreender as classificações preliminares e orientações apresentadas no WhatsApp sem confundi-las com diagnóstico clínico ou parecer jurídico definitivo. | Garante que os dados que chegam ao painel provenham de um fluxo claro e seguro para a vítima. | Revisão de linguagem e testes de compreensão com material simulado (Entrega 7). |
| **H03** | A apresentação lado a lado (*split-screen*) entre mensagens sinalizadas e fundamentação RAG (Art. 147-B) permite que a analista compreenda o motivo da classificação preliminar da IA e decida com segurança quando aprovar ou reclassificar o risco. | Evita o viés de automação e torna a explicabilidade da IA acionável para profissionais não especialistas em ML. | Testes de compreensão e tarefas de auditoria/reclassificação com participantes representativos (Entregas 7 e 12–14). |
| **H04** | A separação entre indicadores agregados (visão geral/relatórios) e detalhamento individual (auditoria) permite interpretar tendências sem confundir volume de análises com prevalência populacional e sem expor dados sensíveis desnecessariamente. | Previne conclusões estatísticas equivocadas e garante conformidade ética e privacidade (LGPD). | Inspeção semiótica e entrevistas pós-tarefa sobre interpretação dos gráficos (Entregas 12–14). |

Registre em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

---

# 11. Síntese da equipe

| Pergunta | Síntese atual |
|---|---|
| Qual é a contribuição central do TCC? | Classificar indícios de violência psicológica em conversas, fundamentar o resultado preliminar via RAG (Art. 147-B) e devolver orientação individual à vítima. |
| O TCC já previa interface? | Parcialmente — o TCC prevê e implementa apenas o chatbot no WhatsApp; o painel administrativo web foi criado como extensão conceitual para a disciplina de IHC. |
| Quem é o usuário prioritário de IHC? | **Analista de Triagem e Auditoria** (profissional autorizada a revisar classificações e acompanhar indicadores). |
| O que ela precisa alcançar? | Validar ou reclassificar a triagem preliminar da IA com apoio de explicabilidade, localizar casos críticos e consolidar indicadores confiáveis sem perder contexto nem comprometer a privacidade. |
| Qual problema/atividade será estudado? | Transformar registros brutos de análises de conversas em um fluxo estruturado de triagem, auditoria *human-in-the-loop* e relatórios consolidados. |
| Como isso acontece hoje? | O pipeline do TCC gera resultados individuais em logs/API, sem interface administrativa consolidada para exploração e revisão. |
| Qual é o contexto de uso? | Ambiente administrativo web em computador/notebook (`1440 × 1024 px`), com dados sensíveis anonimizados (`#ID`) sob requisitos da LGPD. |
| Que interface/recorte será explorado? | Painel web administrativo com Visão Geral (dashboard), filtros por risco, histórico de casos, auditoria *split-screen* (mensagens × RAG), modal de reclassificação, análises estatísticas e relatórios. |
| Como a interface se relaciona ao TCC? | É uma extensão conceitual desenvolvida para a disciplina de IHC e não será implementada no TCC. |
| Quais pontos ainda são hipóteses? | Eficiência da busca e filtragem (`H01`), clareza da saída do chatbot (`H02`), acionabilidade da explicabilidade RAG na auditoria (`H03`) e interpretação correta dos indicadores agregados (`H04`). |

### Delimitação

**Dentro do escopo de IHC:** painel administrativo web; dashboard; indicadores; filtros por risco e busca por `#ID`; histórico de casos; auditoria *split-screen* com explicabilidade RAG; modal de reclassificação humana; análises estatísticas e relatórios; navegação entre visão geral e detalhe; estados de sistema (vazio, erro, sucesso, cancelamento); privacidade e permissões na interação.  
**Fora do escopo de IHC:** treinamento e ajuste do modelo BERT, implementação interna do RAG/Whisper, infraestrutura de backend/Twilio, coleta de localização geográfica/mapas, definição de políticas públicas a partir dos dados e desenvolvimento dos fluxos completos do chatbot no WhatsApp (tratado apenas como origem externa dos dados).  
**Dentro do escopo formal do TCC:** pipeline de NLP/áudio (Faster Whisper, spaCy, BERT), fundamentação via RAG (Art. 147-B), API FastAPI e integração via WhatsApp/Twilio.  
**Interface da disciplina será implementada no TCC?** **Não.** O painel administrativo foi concebido como artefato de modelagem, prototipação e avaliação exclusivo da disciplina de IHC.

---

# 12. Como esta entrega alimenta as próximas

- **Entrega 2:** verifica mercado, concorrentes e interfaces profissionais representativas do perfil de Analista de Triagem.
- **Entrega 3:** detalha perfis (Camila Rocha) e contexto organizacional.
- **Entrega 4:** aprofunda situações problemáticas de triagem, auditoria e reclassificação.
- **Entrega 5:** modela tarefas centrais.
- **Entrega 6:** experimenta alternativas em baixa fidelidade.
- **Entrega 7:** investiga hipóteses (`H01`–`H04`) com dados.
- **Entrega 8:** define restrições e metas de usabilidade.
- **Entregas 9–11:** transformam o recorte em modelo de interação (MoLIC) e protótipo navegável no Figma.
- **Entregas 12–14:** avaliam a interface construída na disciplina.

A Entrega 1 é uma **fotografia inicial do conhecimento**. Ela pode e deve ser revisada quando surgirem evidências.

---

# 13. Relação com INOVA e comunicação do projeto

Prepare uma explicação de até três frases:

1. **Problema/atividade humana:** Pessoas em situação de violência psicológica podem ter dificuldade para reconhecer padrões sutis de abuso em mensagens e conversas, enquanto analistas que supervisionam ferramentas automatizadas de triagem precisam auditar a confiabilidade das classificações sem violar a privacidade dos atendimentos.
2. **Contribuição técnica do TCC:** Um sistema que analisa mensagens e áudios transcritos para identificar indícios de violência psicológica e fundamenta cada classificação preliminar com referências legais (Art. 147-B do Código Penal) e acadêmicas.
3. **Como uma pessoa poderia utilizar essa contribuição:** A vítima encaminha ao chatbot no WhatsApp uma mensagem suspeita e recebe uma orientação preliminar discreta; em uma aplicação institucional complementar (explorada na disciplina de IHC), analistas autorizadas poderiam utilizar um painel web seguro para auditar os pareceres da IA, reclassificar divergências e acompanhar indicadores consolidados.

Essa síntese ajuda a apresentar o projeto para público não especializado sem reduzir seu mérito técnico.

---

# Checklist de qualidade

- [x] Está clara a diferença entre tema do TCC, escopo formal do TCC e escopo de IHC.
- [x] A equipe declarou se o TCC já previa interface.
- [x] Se não previa, foi derivado um usuário plausível e um objetivo de uso.
- [x] A interface de IHC não foi apresentada como obrigação automática do TCC.
- [x] A contribuição do TCC foi descrita sem começar por tecnologias de implementação.
- [x] Usuários diretos e stakeholders foram diferenciados.
- [x] Foram considerados profissionais que configuram, administram, interpretam ou decidem, quando pertinente.
- [x] Objetivo do usuário não foi confundido com objetivo do projeto.
- [x] Processo/problema atual foi descrito antes da solução.
- [x] Existe situação concreta de uso/problema.
- [x] Contexto físico, social/organizacional, dispositivos e consequências de erro foram considerados.
- [x] Mercado/alternativas existentes foram levantados inicialmente.
- [x] Possibilidades como dashboard, relatório, histórico, filtros e CRUD foram tratadas como hipóteses de solução, não como requisitos automáticos.
- [x] Cada possibilidade de interface tem um objetivo/tarefa que poderia justificá-la.
- [x] Afirmações relevantes estão marcadas `[F]`, `[H]` ou `[?]`.
- [x] Hipóteses prioritárias receberam IDs e foram para a rastreabilidade.
- [x] O recorte de IHC é viável para modelar, prototipar e avaliar no semestre.
- [x] A equipe consegue explicar problema humano → contribuição computacional → forma de uso.
