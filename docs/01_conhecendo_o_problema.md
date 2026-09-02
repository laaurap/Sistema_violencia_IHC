# Entrega 1 — Conhecendo o projeto, o usuário e o problema

**Data:** 13/08/2026
**Status:** 🟨 em andamento  
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

**Descrição:** O TCC produz um pipeline de processamento de linguagem natural que classifica indícios de violência psicológica em texto (digitado ou transcrito de áudio), A vítima encaminha ao chatbot, via WhatsApp, uma mensagem ou trecho de conversa recebido do possível agressor; o sistema processa o conteúdo, classifica os indícios encontrados, fundamenta o resultado com referências legais/acadêmicas e devolve uma resposta individual à vítima. O projeto também passa a prever uma interface web administrativa, destinada a administradores/analistas autorizados, para consultar o histórico de análises, revisar conversas e acompanhar indicadores agregados.
Tecnicamente, o pipeline combina pré-processamento com spaCy, classificação zero-shot com modelo BERT multilíngue, RAG para recuperação de referências, API HTTP em FastAPI e integração por n8n/Twilio para o WhatsApp. O painel administrativo será uma camada adicional de interação sobre os dados gerados pelo sistema.

## 0.5 O TCC já previa desenvolvimento de interface com usuário?

- [X] Sim, a interface já faz parte do TCC.
- [X] Parcialmente; existe alguma interação, mas ainda não está bem definida.
- [ ] Não. O TCC é predominantemente técnico e não previa interface.

**Explique o que está formalmente previsto no TCC:**  O sistema possui dois pontos principais de interação. O primeiro é o chatbot no WhatsApp, usado pela vítima: ela envia uma mensagem ou conversa suspeita recebida do possível agressor e recebe a análise individual do conteúdo. O segundo é uma interface web administrativa, alinhada com o orientador, destinada a administradores/analistas autorizados. Nesse painel será possível visualizar um dashboard com indicadores, consultar o histórico de análises, filtrar registros, abrir conversas para análise detalhada e observar padrões agregados.

Para a disciplina de IHC, o recorte principal será a interface administrativa, porque concentra maior variedade de tarefas de interação, visualização, busca, filtragem, comparação e interpretação de dados. O fluxo da vítima pelo WhatsApp continua fazendo parte do sistema e deve permanecer coerente com o painel administrativo.

> Esta resposta serve para separar o compromisso do TCC do projeto da disciplina. Mesmo quando a opção for **não**, a equipe irá definir uma interface para exercitar IHC.

---

# 1. Entendendo a contribuição do projeto

## 1.1 Explique o TCC em uma frase, sem citar linguagem de programação, framework ou banco de dados.

O TCC analisa mensagens e conversas para identificar possíveis indícios de violência psicológica, devolve uma orientação individual à vítima e organiza os resultados em uma interface administrativa para acompanhamento e análise de padrões.

## 1.2 Qual situação, atividade ou problema do mundo real motivou o TCC?

[H] Vítimas que sofrem violência psicológica podem ter dificuldade de reconhecer que determinados comportamentos configuram abuso e, consequentemente, de decidir quando buscar ajuda ou se afastar da situação.

## 1.3 Qual é a **capacidade/contribuição central** produzida pelo TCC?

Complete, se ajudar:

> “Nosso TCC produz, melhora, analisa ou permite `classificar automaticamente a presença e o tipo de violência psicológica em um texto de conversa, e fundamentar essa classificação com referências legais/acadêmicas recuperadas por similaridade semântica."`.”

Exemplos: otimizar consultas; classificar imagens; detectar anomalias; comparar modelos; identificar padrões; prever demanda; analisar desempenho; gerar resumos; recomendar configurações.

Classificar automaticamente a presença e o tipo de indício de violência psicológica em uma conversa e apresentar uma justificativa fundamentada em referências legais e acadêmicas recuperadas pelo sistema.

## 1.4 O que se espera que esteja diferente **para pessoas, organizações ou processos** se essa contribuição for bem-sucedida?

[F/H] H01 — A vítima teria acesso a um mecanismo externo e de baixa fricção para encaminhar ao chatbot uma mensagem ou conversa suspeita e obter uma primeira leitura fundamentada sobre possíveis indícios de violência psicológica.

[F] Após alinhamento com o orientador, o sistema também deverá permitir que administradores/analistas autorizados acompanhem os dados produzidos pelas análises em uma interface própria. Isso poderá transformar registros individuais em informação útil para acompanhamento do sistema, identificação de padrões e análise histórica.


## 1.5 O que é mérito técnico/científico do TCC e o que seria uma possível aplicação prática?

| Mérito/contribuição técnica | Possível aplicação/valor em uso |
|---|---|
| Classificação automática de indícios e categorias de violência psicológica em texto/transcrição | Oferecer à vítima uma avaliação inicial sobre uma conversa suspeita |
| Fundamentação do resultado por meio de RAG com referências legais/acadêmicas| Tornar o resultado mais explicável e menos dependente de uma resposta sem justificativa |
| Exposição do pipeline por API e integração com WhatsApp | Permitir que a capacidade técnica seja acessada por um canal já familiar ao usuário |
|Consolidação e visualização de dados agregados | Permitir ao administrador acompanhar indicadores, categorias recorrentes e evolução temporal |

---

# 2. Entendendo as pessoas envolvidas

## 2.1 Quem interage diretamente com o produto, se já existe interface prevista?

Se não houver interface prevista no TCC, escreva `NÃO SE APLICA AO ESCOPO ORIGINAL` e prossiga para 2.2.

[F] Hoje, o único ponto de interação existente é o próprio WhatsApp: a pessoa envia uma mensagem de texto ou um áudio para o número do bot (Twilio) e recebe de volta uma mensagem automática com o resultado da análise. Não há tela, app ou painel — a "interface" atual é a conversa de WhatsApp em si.

## 2.2 Quem poderia **usar, configurar, administrar, operar, interpretar ou tomar decisões** a partir da contribuição técnica?

Considere perfis profissionais e stakeholders, não apenas consumidores finais.

| Perfil | Relação com a contribuição | O que faria | Status/evidência |
|---|---|---|---|
| {{DBA / analista / gestor / técnico / pesquisador / usuário final...}} | {{...}} | {{...}} | F / H / ? |
| Vítima (usuária final) | Usuária direta do chatbot | Envia texto/áudio, lê o resultado, decide se busca ajuda | F/H |
| Profissional/rede de apoio | Pode receber o resultado caso a vítima decida compartilhá-lo | Auxilia na interpretação da situação e nos próximos passos | H |
| Responsável técnico pelo sistema | Mantém e configura a solução técnica | Atualiza integrações, modelos, base de referência e monitora falhas técnicas | H |
|Administrador | Usuário direto da interface web e perfil priorizado em IHC | Consulta dashboard, histórico e conversas; aplica filtros; acompanha indicadores; | F |


## 2.3 Existem pessoas afetadas que não usariam a interface diretamente?

| Stakeholder | Como é afetado | Usa interface? | Status/evidência |
|---|---|---|---|
| CVV / rede de apoio a vítimas | Recebe encaminhamento indireto (a pessoa liga após o alerta) | Não | H |

## 2.4 Que características desses perfis podem influenciar a interação?

Considere conhecimento do domínio, experiência tecnológica, frequência de uso, necessidades de acessibilidade, responsabilidade profissional, familiaridade com métricas, linguagem técnica, urgência etc.

[H] Vítima: pode estar emocionalmente vulnerável, com medo, vergonha ou dúvida sobre a própria percepção; pode precisar de discrição e privacidade; e não deve ser assumida como conhecedora de vocabulário técnico sobre violência psicológica.

[F/H] Administrador/analista: precisará lidar com uma quantidade maior de registros e tomar decisões de navegação e interpretação a partir de dados agregados. A interface deve favorecer leitura rápida de indicadores, filtros claros, busca eficiente ev comparação temporal. Como os dados tratados são sensíveis, também são relevantes controle de acesso, minimização da exposição de dados pessoais, rastreabilidade das consultas e diferenciação entre informação agregada e conteúdo detalhado das conversas.

---

# 3. Entendendo objetivos e atividades

## 3.1 O que o usuário está tentando conseguir no mundo real?

Não responda “usar o algoritmo”, “clicar no sistema” ou “ver o dashboard”.

[H] - Vitima: Entender se o que está vivendo configura violência psicológica, para poder tomar uma decisão informada sobre buscar ajuda, se proteger, ou conversar sobre o assunto com alguém de confiança.

Administrador/analista: compreender o que está acontecendo no conjunto de análises realizadas pelo sistema, localizar casos específicos quando necessário e identificar padrões relevantes por período, categoria e nível de risco.

## 3.2 Quais são as atividades mais importantes?

| ID | Atividade/objetivo | Quem realiza | Frequência/criticidade inicial | Status/evidência |
|---|---|---|---|---|
| A01 | Enviar ao chatbot uma mensagem ou conversa suspeita para análise | Vítima | Pontual/alta criticidade | F/H |
| A02 | Ler e interpretar o resultado individual | Vítima | Ocorre junto com A01 | F/H |
| A03 | Visualizar indicadores gerais do sistema | Administrador | Frequente | F |
| A04 | Consultar e filtrar histórico de análises | Administrador | Frequente | F |
| A05 | Abrir e analisar o detalhe de uma conversa/resultado | Administrador | Conforme necessidade/alta criticidade | F |
| A06 | Identificar tendências por período, categoria ou nível de risco | Administrador | Periódica | H |

## 3.3 Qual atividade parece mais frequente? Por quê?

[H] Para o usuário priorizado em IHC, as atividades mais frequentes tendem a ser A03 e A04: consultar uma visão geral e navegar pelo histórico usando filtros. Elas funcionam como ponto de entrada para decidir quando aprofundar uma análise em A05 ou explorar padrões específicos em A06. A frequência real deverá ser validada em etapas posteriores.

## 3.4 Qual parece mais crítica? Que consequência existe se for mal executada?

[H] A05 — analisar o detalhe de uma conversa/resultado é uma das atividades administrativas mais críticas, porque uma interpretação incorreta pode levar a conclusões equivocadas sobre um registro. A06 também exigem cuidado: visualizações agregadas ou mapas mal apresentados podem sugerir relações que os dados não sustentam. Para a vítima, A02 continua altamente crítica, pois a comunicação do resultado não pode gerar falsa sensação de segurança nem alarme indevido.

---

# 4. Entendendo o problema ou processo atual

## 4.1 Como essas atividades são realizadas hoje, antes da interface imaginada na disciplina?

Pode existir software concorrente, linha de comando, planilha, notebook, script, painel técnico, processo manual, consulta a logs, análise visual, troca de mensagens, decisão por especialista etc.

[H] Para a vítima, o reconhecimento de violência psicológica ainda costuma depender de autopercepção, conversas com pessoas de confiança, acompanhamento profissional ou conteúdos educativos dispersos.

[F/H] Para o administrador/analista, antes do painel proposto, os resultados produzidos pelo pipeline não contam com uma interface consolidada para exploração. Consultar registros isolados, logs ou dados brutos dificulta ter uma visão do conjunto, localizar casos, comparar períodos, identificar categorias recorrentes ou perceber concentração geográfica das análises.

## 4.2 O que é difícil, demorado, confuso, repetitivo, arriscado ou pouco transparente?

[H] Para a vítima, a principal dificuldade é reconhecer e nomear o possível abuso.

[H] Para o administrador/analista, os principais problemas são transformar muitos registros individuais em informação compreensível, localizar rapidamente um caso relevante, interpretar métricas sem perder o contexto e evitar conclusões erradas a partir de dados agregados. Sem filtros, histórico organizado e visualizações adequadas, a análise tende a ser mais lenta e dependente de consultas manuais.

## 4.3 Que informações o profissional precisa interpretar para tomar decisão?

[F] No nível individual, o administrador poderá interpretar o veredicto (SIM/POSSÍVEL/NÃO), o nível de risco (NENHUM/BAIXO/MÉDIO/ALTO), categorias identificadas, justificativa e referências associadas à análise.

[F/H] No nível agregado, o painel deverá permitir interpretar quantidade de análises, distribuição por nível de risco e categoria, evolução temporal e distribuição geográfica por região/localidade disponível. Esses indicadores deverão ser apresentados de forma que não confundam volume de análises realizadas com prevalência real de violência psicológica na população.

## 4.4 O que acontece quando a atividade falha ou quando o resultado é interpretado incorretamente?

[H] Um falso negativo pode reforçar a sensação de que "não é nada demais", atrasando a busca por ajuda numa situação real. Um falso positivo pode gerar alarme desnecessário, confusão, ou fazer a pessoa duvidar da credibilidade da ferramenta em usos futuros.

## 4.5 Conte uma situação concreta.

Escreva uma pequena narrativa com pessoa, objetivo, atividade, contexto, dificuldade e consequência. **Não descreva ainda a futura solução.**

[H] — Uma jovem de 24 anos troca mensagens diárias com o parceiro. Ao longo dos meses, ele passa a questionar suas saídas, dizer que ela "inventa coisas" quando discordam sobre o que foi dito antes, e chamá-la de "dramática" quando ela expressa desconforto com esse padrão. Isoladamente, cada conversa parece só mais uma discussão de casal — ela nunca ouviu falar em "gaslighting" e não tem certeza se o que sente é exagero seu ou algo mais sério. Ela não conversa sobre isso com ninguém, por vergonha de estar "fazendo tempestade em copo d'água".

## 4.6 Que evidência existe hoje?

| Evidência/fonte | O que sustenta | Limitação |
|---|---|---|
| {{...}} | {{...}} | {{...}} |
| IAVP dos Ministérios Públicos | Há um instrumento institucional de triagem relacionado à mesma base legal (Art. 147-B), preenchido por profissional humano | Não realiza a mesma análise automatizada de conversas proposta pelo TCC |
| Lumira, Be Safe Mulher, Rede Mulher e Instituto Glória | Existem soluções/análogos que atuam em necessidades próximas do domínio | A análise detalhada das interfaces ainda está em andamento |
| Protótipo atual do TCC | Já existe entrada por texto/áudio e saída com veredicto, risco, categorias, fundamentação e recomendação | Ainda não valida compreensão ou utilidade com usuários reais |

---

# 5. Entendendo o contexto de uso

## 5.1 Onde e em quais situações a interação poderia ocorrer?

[F/H] Vítima: no próprio celular, dentro do WhatsApp, possivelmente em momento privado e emocionalmente sensível, após receber uma mensagem ou participar de uma conversa suspeita.

[F/H] Administrador/analista: em ambiente de trabalho ou estudo, utilizando a interface web para acompanhar o funcionamento do sistema, consultar registros e analisar padrões ao longo do tempo.

## 5.2 Em quais dispositivos/equipamentos?

[F] A vítima utiliza principalmente smartphone via WhatsApp.
[H] O painel administrativo será prioritariamente utilizado em computador/notebook, por exigir leitura de tabelas, gráficos, filtros, mapas e detalhes de registros.

## 5.3 Existem condições físicas relevantes?

Considere iluminação, ruído, mobilidade, conexão, privacidade, uso compartilhado, interrupções, pressão de tempo etc.

Para a vítima, privacidade e discrição são críticas, pois o agressor pode ter acesso ao aparelho ou às notificações.

Para o administrador, são importantes legibilidade em telas maiores, densidade de informação controlada e capacidade de alternar entre visão agregada e detalhe sem perder contexto. Como pode haver conteúdo sensível, a interface deve evitar exposição desnecessária de conversas em ambientes compartilhados.

## 5.4 Existem fatores sociais ou organizacionais?

Considere papéis, chefias, equipes, permissões, aprovação, responsabilidade profissional, auditoria, turnos e colaboração.

[F/H] O painel administrativo pressupõe perfis autorizados. Portanto, permissões, responsabilidade sobre dados sensíveis, rastreabilidade de acesso e definição de quem pode visualizar conversas completas são fatores organizacionais relevantes. A vítima não precisa fazer parte dessa estrutura administrativa para utilizar o chatbot.

## 5.5 Existe necessidade de histórico, rastreabilidade ou auditoria?

[F] Sim. O histórico passa a ser uma necessidade explícita do painel administrativo: o usuário autorizado deverá consultar análises anteriores, localizar registros, aplicar filtros e abrir detalhes.

[H] Também pode ser necessário registrar ações de acesso ou revisão realizadas por administradores, devido à sensibilidade dos dados. Para a vítima, a persistência do histórico no WhatsApp continua sendo uma questão de privacidade distinta e não deve ser confundida com o histórico administrativo.

## 5.6 Um erro pode produzir consequência relevante? Qual?

[F/H] Sim. Um falso negativo pode significar não alertar uma pessoa realmente em risco; um falso positivo pode gerar alarme desnecessário e reduzir a confiança na ferramenta. Dado o domínio sensível (violência psicológica), ambos os tipos de erro têm consequência potencialmente grave — não é um domínio "de baixo risco" como recomendação de produtos, por exemplo.

---

# 6. Entendendo mercado e alternativas existentes

> Nesta entrega faça apenas um **levantamento inicial**. A análise aprofundada ocorre na Entrega 2.

## 6.1 Como pessoas resolvem problemas semelhantes hoje?

| Alternativa atual | Quem usa | Para quê | Status/evidência |
|---|---|---|---|
| Atendimento psicológico | Pessoas que já suspeitam de abuso e têm acesso a esse recurso | Diagnóstico e acompanhamento profissional | H |
| Linha CVV | Pessoas em crise emocional | Suporte emocional imediato | F (CVV é um serviço real e conhecido, já referenciado no próprio sistema) |

## 6.2 Existem produtos que atuam na mesma área, mesmo sem serem equivalentes ao TCC?

[F] A Entrega 2 identificou, como alternativas e produtos análogos do domínio, Lumira, Be Safe Mulher, Rede Mulher e Instituto Glória. Também foi identificado o IAVP dos Ministérios Públicos como análogo institucional, por utilizar a mesma base legal de referência (Art. 147-B do Código Penal) em uma triagem preenchida por profissional humano. Essas soluções não são equivalentes ao TCC, mas atuam em necessidades próximas, como autoavaliação, orientação, emergência e triagem.

## 6.3 Quais interfaces profissionais esse público já conhece?

Exemplos possíveis: ferramentas de banco, IDEs, consoles de nuvem, dashboards, plataformas de dados, ferramentas de monitoramento, painéis de IA, sistemas administrativos.

[H] Para o novo usuário priorizado, interfaces de dashboards analíticos, sistemas administrativos, ferramentas de BI, históricos com filtros, tabelas de registros e telas de detalhamento passam a ser referências relevantes de interação. A Entrega 2 deverá investigar interfaces representativas desse tipo para identificar convenções familiares ao administrador.

## 6.4 O que essas soluções parecem fazer bem?

[H] Interfaces profissionais de análise tendem a organizar grande volume de informação em níveis: visão geral, filtros, lista/histórico e detalhamento. Esse padrão é especialmente relevante para o painel proposto, pois o administrador precisa primeiro perceber tendências e depois aprofundar casos específicos.

## 6.5 O que parecem fazer mal, dificultar ou não atender?

[H] Dashboards podem se tornar visualmente carregados, apresentar métricas sem contexto ou exigir conhecimento técnico excessivo. Para este projeto, também existe um risco adicional: expor conteúdo sensível demais na visão geral ou induzir o usuário a interpretar número de análises como número real de casos existentes na população.

## 6.6 Que padrões de interface ou vocabulário parecem familiares a esse público?

[?] Padrões a investigar na Entrega 2

---

# 7. Derivando o escopo de IHC da disciplina

## 7.1 Escolha o caminho do projeto

### Caminho A — TCC já possui interface

Explique qual parte da interface será usada como recorte da disciplina e por que esse fluxo é relevante.

O projeto se enquadra melhor no Caminho A, pois já existe uma interação mínima prevista e implementada por WhatsApp. O recorte da disciplina será aprofundar o painel administrativo, pois ele exige projetar tarefas de maior complexidade de interação: compreender indicadores, aplicar filtros, navegar por histórico, localizar registros, abrir detalhes de conversas e explorar padrões geográficos. O chatbot da vítima continuará sendo considerado como parte do ecossistema do produto, principalmente para entender a origem dos dados exibidos no painel.

### Caminho B — TCC não possui interface prevista

Faça o exercício de transferência de uso:

> **Imagine que o TCC foi concluído com sucesso e uma empresa, laboratório ou organização quer transformar a contribuição em algo utilizável. Quem precisaria interagir com ela e para quê?**

Responda:

1. quem poderia contratar/adotar a solução? {{...}}
2. quem seria o usuário direto? A vítima.
3. quem administraria/configuraria? {{...}}
4. quem interpretaria resultados? Primariamente a própria vítima (uso self-service); secundariamente, um profissional de apoio, caso ela compartilhe o resultado.
5. quem tomaria decisões? {{...}}
6. quais dados/entradas seriam necessários? Texto digitado ou áudio de uma conversa.
7. quais resultados deveriam ser compreendidos? Veredicto, nível de risco, categorias identificadas, fundamentação (fontes) e recomendação de próximo passo.
8. que erros/rupturas seriam possíveis? Falso negativo, falso positivo, falha de transcrição de áudio, exposição indevida do histórico a terceiros (risco de segurança física real, não só incômodo).

## 7.2 Qual perfil será priorizado no projeto de IHC?

Administrador/analista autorizado do sistema.

**Por que esse perfil foi escolhido?** Porque será o usuário direto da nova interface web e executará tarefas que dependem fortemente de decisões de IHC: compreender informação agregada, navegar entre diferentes níveis de detalhe, aplicar filtros, interpretar visualizações, localizar conversas e analisar padrões sem perder o contexto ou a segurança dos dados.

A vítima continua sendo usuária direta do chatbot, mas não será o perfil principal para o desenvolvimento da interface administrativa na disciplina.

## 7.3 Qual objetivo desse usuário será priorizado?

Acompanhar e compreender os dados gerados pelas análises de conversas, identificando padrões relevantes e conseguindo localizar e revisar registros específicos com clareza, eficiência e segurança.

## 7.4 Que interface será explorada na disciplina?

Complete:

> **Para fins da disciplina de IHC, será projetada uma interface que permita a `administrador/analista autorizado` utilizar `os resultados produzidos pelo sistema de detecção de violência psicológica` para `acompanhar indicadores, consultar o histórico, analisar conversas e identificar padrões temporais, categóricos e geográficos`, no contexto de `uso administrativo com dados sensíveis e necessidade de navegação entre visão geral e detalhes.`.**
>

{{...}}

## 7.5 Qual é a relação dessa interface com o TCC?

- [X] Já fazia parte do TCC.
- [X] É um aprofundamento de algo parcialmente previsto.
- [ ] É uma extensão conceitual criada para a disciplina.
- [ ] É um protótipo demonstrativo de aplicação potencial.
- [ ] Outra: {{...}}.

> **Declaração:** o painel administrativo explorado na disciplina está alinhado com o novo escopo discutido com o orientador. A disciplina de IHC servirá para estruturar e avaliar essa interação antes ou durante sua implementação.

---

# 8. Levantando possibilidades de interação — sem desenhar ainda

A equipe pode registrar possibilidades para investigação. **Não significa que todas serão implementadas.**

Marque apenas as que parecem plausíveis e explique o objetivo correspondente.

| Possibilidade | Pode fazer sentido? | Objetivo/tarefa que justificaria | Evidência atual |
|---|---|---|---|
| Dashboard/visão geral | sim | Acompanhar rapidamente volume de análises, riscos, categorias e tendências | F — alinhado com o orientador |
| Configuração/parametrização | talvez | Ajustar parâmetros administrativos do painel, filtros padrão ou preferências | H |
| Entrada/upload/seleção de dados | sim (ChatBot) | Permitir que a vítima encaminhe mensagem/conversa suspeita | F (já é o fluxo atual via WhatsApp) |
| Acompanhamento de processamento | sim (ChatBot)  | Informar à vítima que o conteúdo está sendo analisado | H |
| Relatório/resultados | sim | Exibir resultados individuais e indicadores agregados | F |
| Histórico com busca/filtros | sim | Localizar análises anteriores por critérios relevantes | F — alinhado com o orientador |
| Comparação de resultados | sim/talvez | Comparar períodos, categorias ou níveis de risco | H |
| Explicabilidade/detalhamento | sim | 	Mostrar de forma acessível por que aquele veredicto foi dado (a fundamentação do RAG) | F |
| Administração/configurações globais | talvez | Gerenciar aspectos operacionais do painel | H |
| Usuários/perfis/permissões | sim | Restringir acesso a dados sensíveis conforme o perfil autorizado | H |
| CRUD de entidade do domínio | talvez | Gerenciar cadastros administrativos se surgirem necessidades específicas | H |
| Auditoria/logs | sim/talvez | Rastrear acesso/revisão de dados sensíveis | H |
| Alertas/ocorrências | sim/talvez |	Destacar aumento de registros de alto risco ou situações que mereçam atenção | H/F |
| Ajuda/documentação | sim | Explicar o que é o CVV, o que o resultado significa, e deixar claro que não substitui diagnóstico profissional | H |

> **Atenção:** “login + dashboard + CRUD” não é uma solução universal. Cada padrão deve surgir de uma tarefa real.

---

# 9. Benefícios e ações iniciais

## 9.1 Qual benefício concreto o projeto de IHC pretende oferecer?

| Benefício esperado | Problema/necessidade | Usuário | Status/evidência |
|---|---|---|---|
| Obter visão geral do funcionamento e dos resultados do sistema | Registros isolados dificultam perceber tendências | Administrador | F/H |
| Localizar e revisar rapidamente análises específicas | Grande quantidade de registros pode tornar busca manual lenta | Administrador | F/H |
| Manter o fluxo individual de análise acessível | A vítima precisa encaminhar mensagem suspeita e entender o resultado | Vítima | F/H |

## 9.2 Que ações o usuário deverá conseguir realizar?

| ID | O usuário precisa conseguir... | Para alcançar... | Prioridade inicial |
|---|---|---|---|
| F01 | Visualizar indicadores gerais no dashboard | Entender rapidamente o estado dos dados analisados | alta |
| F02 | Filtrar o conjunto de análises por período, risco, categoria | Responder perguntas específicas sem examinar todos os registros | alta |
| F03 | Consultar histórico e pesquisar registros | Localizar uma análise específica | alta |
| F04 | Abrir o detalhe de uma conversa/análise | Entender o contexto e a justificativa de um resultado | alta |
| F05 | Enviar mensagem/conversa suspeita pelo ChatBot e receber resposta | Manter o fluxo principal da vítima | alta |


## 9.3 Tecnologias/restrições já definidas no TCC

A tecnologia aparece **agora**, depois do entendimento do uso.

| Tecnologia/restrição | Por que existe | Possível impacto na interação |
|---|---|---|
| Twilio/WhatsApp | Canal de entrada/saída da vítima | Deve manter fluxo simples e discreto |
| Transcrição de áudio | Permite analisar mensagens de áudio | Erros de transcrição podem afetar a classificação |
| RAG com referências legais/acadêmicas | Fundamenta tecnicamente o resultado | {A justificativa precisa ser compreensível no detalhe da análise |
| Interface web administrativa | {Permitir acompanhamento e exploração dos dados | Exige arquitetura de informação, filtros, visualizações e controle de acesso |
| Dados sensíveis de conversas | O domínio envolve conteúdo potencialmente íntimo | Requer minimização de exposição, permissões e cuidado com exportações e logs |
| {{...}} | {{...}} | {{...}} |

---

# 10. Hipóteses e dúvidas prioritárias

| ID | Hipótese/dúvida | Por que importa | Como poderá ser investigada |
|---|---|---|---|
| H01 | {{...}} | {{...}} | Entrega 2/3/7/... |
| H02 | {{...}} | {{...}} | {{...}} |
| H03 | {{...}} | {{...}} | {{...}} |

Registre em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

---

# 11. Síntese da equipe

| Pergunta | Síntese atual |
|---|---|
| Qual é a contribuição central do TCC? | Classificar indícios de violência psicológica em conversas, fundamentar o resultado e organizar as análises para uso individual e administrativo |
| O TCC já previa interface? | Sim — há o chatbot da vítima e, após alinhamento com o orientador, um painel administrativo web |
| Quem é o usuário prioritário de IHC? | Administrador/analista autorizado |
| O que ele precisa alcançar? | Reconhecer indícios de abuso, acompanhar indicadores, localizar e revisar análises e identificar padrões sem perder contexto |
| Qual problema/atividade será estudado? | {Transformar muitos registros individuais em informação explorável por dashboard, histórico, filtros, detalhe |
| Como isso acontece hoje? | O pipeline gera resultados individuais, mas ainda não há uma interface administrativa consolidada para exploração |
| Qual é o contexto de uso? | Celular pessoal, ambiente administrativo em computador/notebook, com dados sensíveis e necessidade de acesso controlado |
| Que interface/recorte será explorado? | Painel web com dashboard, filtros, histórico, detalhamento de conversa |
| Como a interface se relaciona ao TCC? | Faz parte do escopo atualizado após alinhamento com o orientador |
| Quais pontos ainda são hipóteses? | {{H01...}} |

### Delimitação

**Dentro do escopo de IHC:** painel administrativo; dashboard; indicadores; filtros; histórico; visualização de tendências; detalhe de análises/conversas; explicabilidade; navegação entre visão geral e detalhe; estados de sistema; privacidade e permissões na interação. 
**Fora do escopo de IHC:** treinamento e ajuste do modelo, implementação interna do RAG, infraestrutura de backend e definição de políticas públicas a partir dos dados.  
**Dentro do escopo formal do TCC:** pipeline de NLP, fundamentação via RAG, API, integração via WhatsApp e interface administrativa prevista no alinhamento atual.  
**Interface da disciplina será implementada no TCC?** não definido / sim / não — {{justificativa, se houver}}

---

# 12. Como esta entrega alimenta as próximas

- **Entrega 2:** verifica mercado, concorrentes e interfaces profissionais representativas.
- **Entrega 3:** detalha perfis e contexto.
- **Entrega 4:** aprofunda situações problemáticas.
- **Entrega 5:** modela tarefas centrais.
- **Entrega 6:** experimenta alternativas em baixa fidelidade.
- **Entrega 7:** investiga hipóteses com dados.
- **Entrega 8:** define restrições e metas de usabilidade.
- **Entregas 9–11:** transformam o recorte em modelo de interação e protótipo.
- **Entregas 12–14:** avaliam a interface construída na disciplina.

A Entrega 1 é uma **fotografia inicial do conhecimento**. Ela pode e deve ser revisada quando surgirem evidências.

---

# 13. Relação com INOVA e comunicação do projeto

Prepare uma explicação de até três frases:

1. **Problema/atividade humana:** Vítimas podem ter dificuldade para reconhecer violência psicológica em mensagens e conversas, enquanto organizações ou responsáveis pelo sistema também podem ter dificuldade para compreender padrões quando os registros são vistos isoladamente.
2. **Contribuição técnica do TCC:** Um sistema que analisa mensagens/conversas e classifica indícios de violência psicológica com fundamentação legal e acadêmica.
3. **Como uma pessoa poderia utilizar essa contribuição:** A vítima encaminha ao chatbot uma mensagem ou conversa suspeita e recebe uma análise individual; administradores autorizados utilizam um painel web para acompanhar indicadores, consultar histórico.

Essa síntese ajuda a apresentar o projeto para público não especializado sem reduzir seu mérito técnico.

---

# Checklist de qualidade

- [x] Está clara a diferença entre tema do TCC, escopo formal do TCC e escopo de IHC.
- [x] A equipe declarou se o TCC já previa interface.
- [x] Se não previa, foi derivado um usuário plausível e um objetivo de uso.
- [ ] A interface de IHC não foi apresentada como obrigação automática do TCC.
- [x] A contribuição do TCC foi descrita sem começar por tecnologias de implementação.
- [x] Usuários diretos e stakeholders foram diferenciados.
- [x] Foram considerados profissionais que configuram, administram, interpretam ou decidem, quando pertinente.
- [x] Objetivo do usuário não foi confundido com objetivo do projeto.
- [x] Processo/problema atual foi descrito antes da solução.
- [x] Existe situação concreta de uso/problema.
- [x] Contexto físico, social/organizacional, dispositivos e consequências de erro foram considerados.
- [x] Mercado/alternativas existentes foram levantados inicialmente.
- [x] Possibilidades como dashboard, relatório, histórico, filtros e CRUD foram tratadas como hipóteses de solução, não como requisitos automáticos.
- [ ] Cada possibilidade de interface tem um objetivo/tarefa que poderia justificá-la.
- [x] Afirmações relevantes estão marcadas `[F]`, `[H]` ou `[?]`.
- [ ] Hipóteses prioritárias receberam IDs e foram para a rastreabilidade.
- [x] O recorte de IHC é viável para modelar, prototipar e avaliar no semestre.
- [x] A equipe consegue explicar problema humano → contribuição computacional → forma de uso.
