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

- [ ] Sim, a interface já faz parte do TCC.
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
| Vítima (usuária final) | Usuária direta que envia a conversa suspeita e recebe o veredicto | Envia texto/áudio, lê o resultado, decide se busca ajuda | H |
| Profissional/rede de apoio | Pode receber o resultado caso a vítima decida compartilhá-lo | Auxilia na interpretação da situação e nos próximos passos | H |
| Responsável técnico pelo sistema | Mantém e configura a solução técnica | Atualiza integrações, modelos, base de referência e monitora falhas técnicas | H |

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

## 3.2 Quais são as atividades mais importantes?

| ID | Atividade/objetivo | Quem realiza | Frequência/criticidade inicial | Status/evidência |
|---|---|---|---|---|
| A01 | Enviar uma conversa (texto ou áudio) suspeita para análise | Vítima | Provavelmente pontual, mas alta criticidade | H |
| A02 | Ler e interpretar o resultado (veredicto, nível de risco, fundamentação) | Vítima | Ocorre junto com A01 | H |
| A03 | Buscar apoio (CVV, psicólogo) após um alerta de risco | Vítima | Rara, mas a mais crítica de todas | H |

## 3.3 Qual atividade parece mais frequente? Por quê?

[?] Não sabemos ainda — não há dados de uso real. A hipótese é que A01 e A02 ocorrem sempre juntas (a pessoa manda a mensagem e imediatamente lê a resposta), mas a frequência com que alguém repete esse envio ao longo do tempo é uma lacuna de conhecimento relevante.

## 3.4 Qual parece mais crítica? Que consequência existe se for mal executada?

[H] A03 (buscar apoio) é a mais crítica. Se o sistema falha em alertar corretamente (falso negativo) numa situação real de risco, a pessoa pode permanecer na situação de abuso por mais tempo, reforçada pela falsa sensação de que "não é nada demais". Se o sistema gera um alarme falso (falso positivo) repetidamente, corre o risco de minar a confiança na ferramenta como um todo.

---

# 4. Entendendo o problema ou processo atual

## 4.1 Como essas atividades são realizadas hoje, antes da interface imaginada na disciplina?

Pode existir software concorrente, linha de comando, planilha, notebook, script, painel técnico, processo manual, consulta a logs, análise visual, troca de mensagens, decisão por especialista etc.

[H] Para a vítima, o reconhecimento de violência psicológica ainda costuma depender de autopercepção, conversas com pessoas de confiança, acompanhamento profissional ou conteúdos educativos dispersos.

[H] 

## 4.2 O que é difícil, demorado, confuso, repetitivo, arriscado ou pouco transparente?

[H] Para a vítima, a principal dificuldade é reconhecer e nomear o possível abuso.

[H] O mais difícil é justamente o reconhecimento do próprio abuso — as táticas mais citadas na literatura (gaslighting, normalização gradual, chantagem emocional) têm como efeito direto dificultar que a vítima nomeie o que está vivendo. Além disso, buscar informação sozinha é um processo disperso (múltiplas fontes, sem fundamentação clara) e emocionalmente custoso.

## 4.3 Que informações o profissional precisa interpretar para tomar decisão?

[F] Com base na saída atual do analisador: o veredicto (SIM/POSSÍVEL/NÃO), o nível de risco (NENHUM/BAIXO/MÉDIO/ALTO), as categorias específicas identificadas (ex: gaslighting, controle), a justificativa fundamentada com fonte, e uma recomendação de próximo passo (ex: ligar para o CVV).

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
| Lumira, Be Safe Mulher, Rede Mulher e Instituto Glória | {{...}} | {{...}} |

---

# 5. Entendendo o contexto de uso

## 5.1 Onde e em quais situações a interação poderia ocorrer?

[H] No próprio celular da pessoa, dentro do WhatsApp, provavelmente em momentos privados — sozinha, longe do parceiro/agressor, possivelmente à noite ou logo após um episódio de conflito.

## 5.2 Em quais dispositivos/equipamentos?

[F] Smartphone — o canal escolhido (WhatsApp) é majoritariamente mobile no Brasil.

## 5.3 Existem condições físicas relevantes?

Considere iluminação, ruído, mobilidade, conexão, privacidade, uso compartilhado, interrupções, pressão de tempo etc.

[H] Privacidade é a condição mais crítica: a pessoa pode não querer que o agressor veja a conversa, uma notificação na tela de bloqueio, ou o histórico de mensagens. Pode haver situações de urgência emocional, e a pessoa pode ter acesso limitado ou monitorado ao próprio celular.

## 5.4 Existem fatores sociais ou organizacionais?

Considere papéis, chefias, equipes, permissões, aprovação, responsabilidade profissional, auditoria, turnos e colaboração.

[H] Não há hierarquia profissional envolvida diretamente no uso pela vítima, mas existe uma "rede de apoio" que pode ser acionada a partir do resultado (CVV, psicólogos, delegacias especializadas) — o sistema atua como uma ponte para esses processos institucionais já existentes.

## 5.5 Existe necessidade de histórico, rastreabilidade ou auditoria?

[H] Pode haver necessidade de histórico para a própria vítima acompanhar análises anteriores, mas esse recurso também cria um risco relevante de privacidade caso o aparelho seja compartilhado ou monitorado. Por isso, a necessidade real de histórico, sua persistência e formas de proteção ainda precisam ser investigadas antes de tratá-lo como requisito.

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

{{[F/H/?] ...}}

## 6.4 O que essas soluções parecem fazer bem?

{{[F/H/?] ...}}

## 6.5 O que parecem fazer mal, dificultar ou não atender?

{{[F/H/?] ...}}

## 6.6 Que padrões de interface ou vocabulário parecem familiares a esse público?

{{[F/H/?] ...}}

---

# 7. Derivando o escopo de IHC da disciplina

## 7.1 Escolha o caminho do projeto

### Caminho A — TCC já possui interface

Explique qual parte da interface será usada como recorte da disciplina e por que esse fluxo é relevante.

O projeto se enquadra melhor no Caminho A, pois já existe uma interação mínima prevista e implementada por WhatsApp. O recorte da disciplina será aprofundar o fluxo em que a vítima envia uma conversa em texto ou áudio, recebe o resultado da análise, compreende o nível de risco e a justificativa e encontra uma orientação segura sobre o que fazer a seguir. Esse fluxo é relevante porque concentra as atividades A01, A02 e A03 e ocorre em um contexto emocionalmente sensível, no qual clareza, discrição e prevenção de interpretações equivocadas são essenciais.

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

A vítima — a pessoa que efetivamente recebe a notificação/resultado da análise pelo WhatsApp.

**Por que esse perfil foi escolhido?** Porque é quem recebe diretamente o resultado e precisa transformá-lo em entendimento e ação. Além disso, é o perfil mais afetado pelas consequências de uma comunicação inadequada.

## 7.3 Qual objetivo desse usuário será priorizado?

Reconhecer, de forma clara, acolhedora e sem linguajar técnico, se uma conversa apresenta indícios de violência psicológica — e entender com segurança o que fazer a seguir.

## 7.4 Que interface será explorada na disciplina?

Complete:

> **Para fins da disciplina de IHC, será projetada uma interface que permita a `vítima de violência psicológica` utilizar `a análise automatizada de conversas (texto ou áudio)` para `reconhecer indícios de abuso na própria relação`, no contexto de `uso privado, muitas vezes urgente e emocionalmente sensível, pelo celular.`.**
>

{{...}}

## 7.5 Qual é a relação dessa interface com o TCC?

- [ ] Já fazia parte do TCC.
- [X] É um aprofundamento de algo parcialmente previsto.
- [ ] É uma extensão conceitual criada para a disciplina.
- [ ] É um protótipo demonstrativo de aplicação potencial.
- [ ] Outra: {{...}}.

> **Declaração:** a interface desenvolvida nesta disciplina é um artefato de aprendizagem de IHC baseado no tema do TCC.

---

# 8. Levantando possibilidades de interação — sem desenhar ainda

A equipe pode registrar possibilidades para investigação. **Não significa que todas serão implementadas.**

Marque apenas as que parecem plausíveis e explique o objetivo correspondente.

| Possibilidade | Pode fazer sentido? | Objetivo/tarefa que justificaria | Evidência atual |
|---|---|---|---|
| Dashboard/visão geral | sim/não/talvez | {{...}} | {{...}} |
| Configuração/parametrização | sim/não/talvez | {{...}} | {{...}} |
| Entrada/upload/seleção de dados | sim | Enviar o texto ou áudio da conversa a ser analisada | F (já é o fluxo atual via WhatsApp) |
| Acompanhamento de processamento | sim/não/talvez | {{...}} | {{...}} |
| Relatório/resultados | sim/não/talvez | {{...}} | {{...}} |
| Histórico com busca/filtros | sim/não/talvez | {{...}} | {{...}} |
| Comparação de resultados | sim/não/talvez | {{...}} | {{...}} |
| Explicabilidade/detalhamento | sim | 	Mostrar de forma acessível por que aquele veredicto foi dado (a fundamentação do RAG) | F (já existe tecnicamente, precisa virar UI acessível) |
| Administração/configurações globais | sim/não/talvez | {{...}} | {{...}} |
| Usuários/perfis/permissões | sim/não/talvez | {{...}} | {{...}} |
| CRUD de entidade do domínio | sim/não/talvez | {{...}} | {{...}} |
| Auditoria/logs | sim/não/talvez | {{...}} | {{...}} |
| Alertas/ocorrências | sim |	É o núcleo do produto — o alerta de risco é a razão de existir da interação | F |
| Ajuda/documentação | sim | Explicar o que é o CVV, o que o resultado significa, e deixar claro que não substitui diagnóstico profissional | H |

> **Atenção:** “login + dashboard + CRUD” não é uma solução universal. Cada padrão deve surgir de uma tarefa real.

---

# 9. Benefícios e ações iniciais

## 9.1 Qual benefício concreto o projeto de IHC pretende oferecer?

| Benefício esperado | Problema/necessidade | Usuário | Status/evidência |
|---|---|---|---|
| Reconhecer, sem depender só de terceiros, se uma conversa parece configurar violência psicológica | Dificuldade de autopercepção do abuso, agravada pelas próprias táticas do agressor (gaslighting, normalização) | Vítima | H |

## 9.2 Que ações o usuário deverá conseguir realizar?

| ID | O usuário precisa conseguir... | Para alcançar... | Prioridade inicial |
|---|---|---|---|
| F01 | Enviar uma conversa (texto ou áudio) para análise | Obter uma avaliação inicial de risco | alta |
| F02 | Entender o resultado, mesmo sem vocabulário técnico sobre o tema | Tomar uma decisão informada sobre o que fazer | alta |
| F03 | {{ação}} | {{objetivo}} | alta/média/baixa |

## 9.3 Tecnologias/restrições já definidas no TCC

A tecnologia aparece **agora**, depois do entendimento do uso.

| Tecnologia/restrição | Por que existe | Possível impacto na interação |
|---|---|---|
| Twilio/WhatsApp como canal de entrega | canal de entrega	Já era o canal usado nos testes do sistema, é popular e familiar ao público-alvo| {{...}} |
| {{...}} | {{...}} | {{...}} |
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
| Qual é a contribuição central do TCC? | Classificar indícios de violência psicológica em conversas, com fundamentação legal/acadêmica via RAG |
| O TCC já previa interface? | Parcialmente — existe interação via WhatsApp, mas nada formalmente desenhado |
| Quem é o usuário prioritário de IHC? | A vítima, que recebe a notificação diretamente |
| O que ele precisa alcançar? | Reconhecer indícios de abuso na própria relação e saber o que fazer a seguir |
| Qual problema/atividade será estudado? | {{...}} |
| Como isso acontece hoje? | De forma dispersa e não fundamentada: autopercepção, conversas informais, conteúdo educativo genérico |
| Qual é o contexto de uso? | Celular pessoal, provavelmente em momento privado, com forte necessidade de discrição |
| Que interface/recorte será explorado? | {{...}} |
| Como a interface se relaciona ao TCC? | {{...}} |
| Quais pontos ainda são hipóteses? | {{H01...}} |

### Delimitação

**Dentro do escopo de IHC:** {{...}}  
**Fora do escopo de IHC:** {{...}}  
**Dentro do escopo formal do TCC:** {{...}}  
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

1. **Problema/atividade humana:** Vítimas de violência psicológica frequentemente não conseguem reconhecer sozinhas o abuso que estão vivendo, por causa das próprias táticas usadas pelo agressor.
2. **Contribuição técnica do TCC:** Um sistema que analisa conversas de texto ou áudio e classifica indícios de violência psicológica, explicando o resultado com base em critérios legais e acadêmicos reais.
3. **Como uma pessoa poderia utilizar essa contribuição:** {{...}}

Essa síntese ajuda a apresentar o projeto para público não especializado sem reduzir seu mérito técnico.

---

# Checklist de qualidade

- [ ] Está clara a diferença entre tema do TCC, escopo formal do TCC e escopo de IHC.
- [ ] A equipe declarou se o TCC já previa interface.
- [ ] Se não previa, foi derivado um usuário plausível e um objetivo de uso.
- [ ] A interface de IHC não foi apresentada como obrigação automática do TCC.
- [ ] A contribuição do TCC foi descrita sem começar por tecnologias de implementação.
- [ ] Usuários diretos e stakeholders foram diferenciados.
- [ ] Foram considerados profissionais que configuram, administram, interpretam ou decidem, quando pertinente.
- [ ] Objetivo do usuário não foi confundido com objetivo do projeto.
- [ ] Processo/problema atual foi descrito antes da solução.
- [ ] Existe situação concreta de uso/problema.
- [ ] Contexto físico, social/organizacional, dispositivos e consequências de erro foram considerados.
- [ ] Mercado/alternativas existentes foram levantados inicialmente.
- [ ] Possibilidades como dashboard, relatório, histórico, filtros e CRUD foram tratadas como hipóteses de solução, não como requisitos automáticos.
- [ ] Cada possibilidade de interface tem um objetivo/tarefa que poderia justificá-la.
- [ ] Afirmações relevantes estão marcadas `[F]`, `[H]` ou `[?]`.
- [ ] Hipóteses prioritárias receberam IDs e foram para a rastreabilidade.
- [ ] O recorte de IHC é viável para modelar, prototipar e avaliar no semestre.
- [ ] A equipe consegue explicar problema humano → contribuição computacional → forma de uso.
