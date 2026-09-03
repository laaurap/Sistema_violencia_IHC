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
| Lumira | concorrente/análoga do domínio | Atua em necessidade próxima de orientação e identificação de violência | F/H | analisar como C02 |
| IAVP (Ministérios Públicos) | análogo institucional |	Mesma base legal (Art. 147-B do Código Penal) usada como referência oficial de triagem, porem preenchido por profissional humano | F | analisar como C01 |
| Be Safe Mulher | concorrente/análoga do domínio | Atua em contexto de proteção, orientação e apoio à mulher | F/H | analisar como C03 |
| Rede Mulher | concorrente/análoga do domínio |	Atua em acolhimento/orientação e rede de apoio | F/H | analisar em resumo ou como C04 |
| Instituto Glória | concorrente/análoga do domínio |	Atua em apoio, orientação e enfrentamento à violência | F/H | analisar em resumo ou como C05 |

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

- interpretar os resultados sem perder o contexto.

A vítima continua sendo usuária direta do sistema, porém do outro ponto de interação: ela recebe uma mensagem ou conversa suspeita do possível agressor, encaminha esse conteúdo ao chatbot pelo WhatsApp e recebe a análise individual. Esse fluxo é importante para entender a origem dos dados, mas não é o foco principal da interface administrativa estudada nesta entrega.

## 2. Concorrentes diretos/indiretos

### Análise C01 — IAVP (Instrumento de Avaliação de Violência Psicológica, Grupo de Trabalho Pandora / Ministérios Públicos estaduais)

**Autor(a):** Laura de Souza Parente — 22.123.033-7 
**Tipo:** análogo institucional / metodológico
**Link oficial:** [{{URL}}](https://iavppandora.insightlab.ufc.br/iavp)  
**Data de acesso:** 27/08/2026

#### Contexto e proposta

O IAVP foi desenvolvido pelo Grupo Pandora, formado por profissionais das áreas de Direito, Psicologia e Psiquiatria. Seu objetivo é auxiliar na identificação de condutas de violência psicológica e do dano emocional associado, tomando como referência o art. 147-B do Código Penal.

O instrumento pode ser preenchido diretamente pela vítima, embora o próprio material de aplicação recomende, quando possível, o acompanhamento de profissional capacitada nas áreas de saúde, assistência social, segurança pública ou jurídica.

Para o nosso projeto, o IAVP é relevante principalmente porque demonstra uma forma estruturada, fundamentada e institucional de organizar a avaliação de violência psicológica, mesmo sem realizar análise automatizada de conversas.

#### Funcionalidades relevantes

| Funcionalidade | Como é realizada | Evidência/print | Observação de IHC |
|---|---|---|---|
| Formulário estruturado de avaliação | Preenchido pela propria vitima, mas é recomendado quando possivel se preenchido por profissional habilitado, buscando identificar constrangimento, humilhação, manipulação, isolamento, ameaças, violência digital, entre outras categorias | PRINT | A divisão em etapas reduz a quantidade de informação apresentada de uma vez, mas aumenta o número de passos |
| Identificação de condutas de violência psicológica | O instrumento apresenta perguntas relacionadas a constrangimento, humilhação, controle, isolamento, ameaças e outras condutas | PRINT | Estrutura e terminologia podem ajudar a organizar categorias exibidas no detalhe de uma análise |
| Avaliação de dano emocional | Há uma parte específica voltada aos impactos emocionais associados à situação de violência | PRINT | Mostra a importância de separar comportamento identificado de consequência emocional |
| Aviso de privacidade e tratamento de dados sensíveis | A interface informa que os dados são sensíveis e apresenta orientações antes do preenchimento | `../assets/02_concorrencia/...` | Transparência sobre dados é especialmente relevante para nosso painel administrativo |
| Salvamento local do rascunho | A interface informa que o rascunho pode ser mantido localmente no dispositivo e permite desabilitar esse recurso | `../assets/02_concorrencia/...` | Demonstra preocupação explícita com privacidade e controle do usuário |

#### Experiência do usuário e opiniões

Use avaliações públicas, relatos, estudos, testes próprios ou outra fonte identificável. Não trate opinião isolada como verdade universal.

Nas fontes oficiais consultadas não foram encontradas avaliações públicas de usuários em quantidade suficiente para concluir que a interface é fácil ou difícil de usar. Portanto, não é adequado tratar satisfação ou usabilidade percebida como fato.

Em uma análise exploratória da própria interface, entretanto, é possível observar alguns elementos objetivos: o formulário é dividido em seções, campos obrigatórios são identificados, existe aviso de coleta de dados sensíveis e a interface comunica o comportamento do salvamento local. Esses pontos ajudam a reduzir incerteza durante o preenchimento, mas a quantidade de perguntas e a extensão do instrumento podem aumentar o esforço necessário para conclusão.

#### Preço/modelo de negócio

Não foi identificado modelo comercial ou cobrança para utilização do instrumento na página oficial consultada. O IAVP é apresentado como uma ferramenta institucional de apoio à identificação e enfrentamento da violência psicológica.

#### Padrões e tendências percebidos

- formulário dividido em etapas;

- uso de linguagem vinculada ao domínio jurídico e psicológico;

- separação entre condutas do agressor e dano emocional;

- indicação explícita de campos obrigatórios;

- aviso de privacidade antes da coleta de dados sensíveis;

- preocupação em orientar quem deve preencher e em qual contexto.

#### Pontos positivos, limitações e lições

| Ponto | Evidência | Implicação para nosso projeto |
|---|---|---|
| Base técnica e jurídica explícita | IAVP organizado a partir do art. 147-B e desenvolvido por equipe interdisciplinar | O painel deve deixar clara a origem/fundamentação das categorias e resultados |
| Estrutura padronizada | Instrumento dividido em partes e perguntas organizadas | Categorias e informações do nosso sistema também devem seguir uma organização consistente |
| Preocupação com privacidade | A interface apresenta aviso sobre dados sensíveis e armazenamento | O painel administrativo precisa comunicar e limitar o acesso a conteúdo sensível || Avaliação manual e estruturada | O preenchimento depende de respostas fornecidas pela vítima/profissional | Nosso sistema se diferencia ao analisar automaticamente mensagens/conversas |
| Não possui foco em análise agregada de muitos casos | A interface observada é voltada ao preenchimento individual | Existe oportunidade para nosso dashboard apoiar visão geral, histórico e comparação |

> Repita a subseção para C02, C03... até atender à quantidade da equipe.

## 3. Softwares que o público-alvo usa no cotidiano

Analise interfaces que moldam a expectativa do público, mesmo que não sejam concorrentes.

| Software | Por que o público usa | Padrões relevantes | Prints | O que aprender |
|---|---|---|---|---|
| Power BI | Referência profissional para acompanhamento de indicadores e exploração de dados | dashboard, cards, gráficos, filtros, tabelas | {{link local}} | Como organizar visão geral e permitir aprofundamento sem perder contexto |
| Looker Studio | Referência de relatórios e dashboards interativos | iltros visíveis, controles, gráficos, páginas de relatório | {{link local}} | Como permitir exploração visual do conjunto de dados |
| Excel / planilha eletrônica | Referência comum para consulta, ordenação e filtragem de registros | linhas/colunas, busca, ordenação, filtros | {{link local}} | Como tornar o histórico eficiente para localizar registros |
| WhatsApp | Canal usado pela vítima para enviar a conversa suspeita e receber a resposta | conversa em mensagens, histórico cronológico, feedback de envio | {{link local}} | Entender a origem do conteúdo que depois aparece no painel administrativo |


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

- GRUPO PANDORA. IAVP: Instrumento de Avaliação de Violência Psicológica. Disponível em: https://iavppandora.insightlab.ufc.br/iavp
- INSTITUTO GLÒRIA. Disponível em: https://eusouagloria.com.br/home

## Checklist

- [x] O mapa inicial de alternativas da Entrega 1 foi revisitado e aprofundado.
- [ ] Hipóteses relevantes sobre mercado/padrões foram atualizadas na rastreabilidade quando surgiram evidências.
- [ ] Há pelo menos uma análise completa por integrante.
- [ ] Cada análise contém prints legíveis da interface.
- [ ] Prints mostram telas/estados relevantes, não apenas logos/homepage.
- [x] Foram analisados concorrentes e/ou interfaces representativas ao público.
- [ ] Em TCC sem interface original, foram investigadas ferramentas profissionais análogas às atividades do usuário escolhido.
- [x] Padrões como dashboard, relatório, filtros e CRUD foram analisados como soluções para tarefas, não como requisitos automáticos.
- [ ] Opiniões de UX têm fonte.
- [ ] A síntese compara critérios comuns e produz recomendações.
- [x] Não há “copiar porque o concorrente faz”; há justificativa de adequação ao público/contexto.
