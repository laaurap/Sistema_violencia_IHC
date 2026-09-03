# Entrega 2 — Público-alvo e análise de concorrência

**Data:** 27/08/2026 
**Status:** 🟨 em andamento 
**Responsabilidade mínima:** cada integrante analisa pelo menos 1 concorrente/interface representativa; a equipe produz síntese comparativa.

## Objetivo da atividade

Compreender soluções do mesmo domínio **e também interfaces familiares ao público-alvo**. O objetivo não é copiar telas, mas identificar convenções, padrões, affordances percebidas, problemas recorrentes, expectativas e oportunidades de design.

> **Concorrente não precisa ser idêntico ao produto.** Pode atuar na mesma área, resolver objetivo semelhante ou disputar a mesma necessidade. Quando não houver concorrente direto, use produtos análogos e softwares que o público já utiliza.

### Para TCCs que não previam interface

Não procure apenas um “concorrente do algoritmo”. Investigue **interfaces profissionais que materializam atividades semelhantes** às que o usuário escolhido precisaria realizar.

Exemplos:

- TCC de banco de dados → consoles de administração, ferramentas para DBA, monitoramento e análise de consultas;
- TCC de LLM/ML → painéis de experimentos, gestão de modelos/datasets, comparação de métricas, revisão de resultados;
- TCC de análise de dados → dashboards, ferramentas de BI, filtros, relatórios e exploração;
- TCC de infraestrutura/API → portais administrativos, observabilidade, logs, gestão de credenciais e uso;
- TCC de cibersegurança → consoles de alertas, triagem, histórico e auditoria.

A pergunta é: **“que convenções esse perfil já conhece para executar tarefas equivalentes?”**

## Entrada obrigatória da Entrega 1

Retome o mapa inicial de alternativas e produtos citado na Entrega 1. Aqui a equipe deixa de trabalhar apenas com impressão inicial e passa a **investigar sistematicamente** cada solução.
| Item citado na Entrega 1 | Tipo | Por que foi citado | Status inicial | Decisão nesta entrega |
|---|---|---|---|---|
| Lumira, Be Safe Mulher, Rede Mulher, Instituto Glória | concorrentes/análogos do domínio | Atuam em necessidades próximas, como orientação, autoavaliação, acolhimento e emergência | F | manter no levantamento e aprofundar os mais representativos |
| IAVP (Ministérios Públicos) | análogo institucional |	Mesma base legal (Art. 147-B do Código Penal) usada como referência oficial de triagem, porem preenchido por profissional humano | F | manter como referência institucional) |
| Dashboards analíticos / ferramentas de BI | análogos de interface | O administrador precisa visualizar indicadores e tendências em grande volume de dados | H | analisar pelo menos uma interface representativa |
| Sistemas administrativos com histórico, busca e filtros | análogos de interface |	O administrador precisa localizar análises anteriores e abrir registros específicos | H | analisar pelo menos uma interface representativa |
| Sistemas de monitoramento/triagem com lista + detalhe | análogos de interface |	O administrador precisa sair de uma visão geral para o detalhe de uma análise | H | investigar convenções de navegação e priorização |

Se uma hipótese da Entrega 1 for confirmada ou refutada durante esta análise, atualize `H01`, `H02`... em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

## 1. Público-alvo desta análise

Conforme definido na Entrega 1, o usuário principal priorizado para IHC é o administrador/analista autorizado do sistema. Esse usuário acessará a interface web administrativa para acompanhar e compreender os dados gerados pelas análises de conversas.

Seu objetivo principal é conseguir transformar um conjunto grande de registros individuais em informação útil, realizando tarefas como:

- visualizar indicadores gerais no dashboard;

- consultar o histórico de análises;

- aplicar filtros por período, nível de risco e categoria;

- pesquisar registros específicos;

- abrir e analisar o detalhe de uma conversa/resultado;

- observar tendências e padrões no conjunto de dados;

- interpretar os resultados sem perder o contexto e sem expor informações sensíveis desnecessariamente.

A vítima continua sendo usuária direta do sistema, porém do outro ponto de interação: ela recebe uma mensagem ou conversa suspeita do possível agressor, encaminha esse conteúdo ao chatbot pelo WhatsApp e recebe a análise individual. Esse fluxo é importante para entender a origem dos dados, mas não é o foco principal da interface administrativa estudada nesta entrega.

## 2. Concorrentes diretos/indiretos

### Análise C01 — IAVP (Instrumento de Avaliação de Violência Psicológica, Grupo de Trabalho Pandora / Ministérios Públicos estaduais)

**Autor(a):** Laura de Souza Parente — 22.123.033-7 
**Tipo:** análogo  (protocolo metodológico, não é software autônomo)
**Link oficial:** [{{URL}}](https://iavppandora.insightlab.ufc.br/iavp)  
**Data de acesso:** 27/08/2026

#### Contexto e proposta

Instrumento criado por um grupo interdisciplinar de nove profissionais (Direito, Psicologia e Psiquiatria), lançado pelo Núcleo de Gênero do MPSP e depois replicado por Ministérios Públicos de outros estados (RJ, MG, ES, PR). O objetivo declarado é identificar condutas de violência psicológica tipificadas no artigo 147-B do Código Penal e dimensionar o dano emocional sofrido pela vítima, para uso por promotores, peritos e profissionais de saúde/assistência social.

#### Funcionalidades relevantes

| Funcionalidade | Como é realizada | Evidência/print | Observação de IHC |
|---|---|---|---|
| Formulário estruturado de triagem | Preenchido pela propria vitima, mas é recomendado quando possivel se preenchido por profissional habilitado, buscando identificar constrangimento, humilhação, manipulação, isolamento, ameaças, violência digital, entre outras categorias | `../assets/02_concorrencia/...` | {{...}} |

#### Experiência do usuário e opiniões

Use avaliações públicas, relatos, estudos, testes próprios ou outra fonte identificável. Não trate opinião isolada como verdade universal.

#### Preço/modelo de negócio

{{...}}

#### Padrões e tendências percebidos

{{...}}

#### Pontos positivos, limitações e lições

| Ponto | Evidência | Implicação para nosso projeto |
|---|---|---|
| Mesma base legal (Art. 147-B do Código Penal) usada como referência oficial por Ministérios Públicos de múltiplos estados | {{...}} | {{...}} |
| É preenchido por profissional especializado, não por IA | Manual do IAVP exige "expertise para atuar em casos de violência psicológica" | {{...}} |

> Repita a subseção para C02, C03... até atender à quantidade da equipe.

## 3. Softwares que o público-alvo usa no cotidiano

Analise interfaces que moldam a expectativa do público, mesmo que não sejam concorrentes.

| Software | Por que o público usa | Padrões relevantes | Prints | O que aprender |
|---|---|---|---|---|
| Ferramenta de BI/dashboard | Principal canal de comunicação pessoal no Brasil; é também o canal que o próprio Ligue 180 passou a usar oficialmente | Conversas em bolhas, indicadores de "digitando...", confirmação de leitura, notificações push | {{link local}} | O bot deve seguir as convenções de conversa do WhatsApp (mensagens curtas, tom direto) em vez de se comportar como um formulário longo |
| WhatsApp | Principal canal de comunicação pessoal no Brasil; é também o canal que o próprio Ligue 180 passou a usar oficialmente | Conversas em bolhas, indicadores de "digitando...", confirmação de leitura, notificações push | {{link local}} | O bot deve seguir as convenções de conversa do WhatsApp (mensagens curtas, tom direto) em vez de se comportar como um formulário longo |
| WhatsApp | Principal canal de comunicação pessoal no Brasil; é também o canal que o próprio Ligue 180 passou a usar oficialmente | Conversas em bolhas, indicadores de "digitando...", confirmação de leitura, notificações push | {{link local}} | O bot deve seguir as convenções de conversa do WhatsApp (mensagens curtas, tom direto) em vez de se comportar como um formulário longo |
| WhatsApp | Principal canal de comunicação pessoal no Brasil; é também o canal que o próprio Ligue 180 passou a usar oficialmente | Conversas em bolhas, indicadores de "digitando...", confirmação de leitura, notificações push | {{link local}} | O bot deve seguir as convenções de conversa do WhatsApp (mensagens curtas, tom direto) em vez de se comportar como um formulário longo |

## 3.1 Padrões de interface relevantes ao escopo de IHC

Registre somente padrões encontrados nas soluções analisadas e que possam ter relação com objetivos reais da equipe.

| Padrão observado | Produto(s) | Para qual tarefa serve | Vantagem percebida | Risco/limitação | Aplicável ao nosso escopo? |
|---|---|---|---|---|---|
| dashboard | {{...}} | {{...}} | {{...}} | {{...}} | sim/não/talvez |
| relatório | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |
| histórico + filtros | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |
| administração/CRUD | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |
| comparação de resultados | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |

> O objetivo não é concluir “todo concorrente tem dashboard, então teremos um”. O padrão só será adotado se apoiar uma tarefa rastreável.

## 4. Síntese comparativa da equipe

| Critério | C01 (IAVP) | C02 (Lumira) | C03 | Oportunidade para o projeto |
|---|---|---|---|---|
| Navegação |  |  |  |  |
| Feedback/estado |  |  |  |  |
| Prevenção/recuperação de erro |  |  |  |  |
| Terminologia |  |  |  |  |
| Acessibilidade |  |  |  |  |
| Eficiência |  |  |  |  |

## 5. Recomendações derivadas

Liste recomendações com origem explícita.

- **RC01:** {{recomendação}} — derivada de {{C01/C02/evidência}}.
- **RC02:** {{...}}

## Referências

{{fontes dos produtos, avaliações e literatura}}

## Checklist

- [ ] O mapa inicial de alternativas da Entrega 1 foi revisitado e aprofundado.
- [ ] Hipóteses relevantes sobre mercado/padrões foram atualizadas na rastreabilidade quando surgiram evidências.
- [ ] Há pelo menos uma análise completa por integrante.
- [ ] Cada análise contém prints legíveis da interface.
- [ ] Prints mostram telas/estados relevantes, não apenas logos/homepage.
- [ ] Foram analisados concorrentes e/ou interfaces representativas ao público.
- [ ] Em TCC sem interface original, foram investigadas ferramentas profissionais análogas às atividades do usuário escolhido.
- [ ] Padrões como dashboard, relatório, filtros e CRUD foram analisados como soluções para tarefas, não como requisitos automáticos.
- [ ] Opiniões de UX têm fonte.
- [ ] A síntese compara critérios comuns e produz recomendações.
- [ ] Não há “copiar porque o concorrente faz”; há justificativa de adequação ao público/contexto.
