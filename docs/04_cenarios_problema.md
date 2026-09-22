# Entrega 4 — Cenários de análise/problema

**Data:** 16/09/2026
**Status:** 🟩 concluída
**Responsabilidade:** 1 solução completa por integrante

## Objetivo da atividade

Descrever situações atuais em que o usuário tenta alcançar um objetivo e encontra dificuldades. O cenário de análise/problema deve tornar visível **o contexto, os atores, as ações e as rupturas**, sem antecipar a interface que será projetada.

> **Regra central:** cenário de problema é a “história do problema”. Se o texto já diz “o sistema mostra”, “o aplicativo resolve” ou descreve botões/telas futuras, provavelmente está misturando problema com solução.

Sempre que possível, o cenário deve aprofundar uma **situação concreta já registrada na Entrega 1**.

### Quando o TCC não possuía interface

O cenário continua sendo uma história de **problema/atividade humana**, não uma história do futuro sistema. Descreva como o profissional realiza hoje uma atividade semelhante ou como lida atualmente com dados, resultados, configurações, logs, decisões e limitações que o tema do TCC pretende apoiar.

Exemplo: em vez de “o DBA abre o novo dashboard e executa o algoritmo”, descreva “o DBA precisa investigar uma consulta lenta, reúne informações em ferramentas distintas, compara planos manualmente e tem dificuldade para estimar o impacto de uma mudança”.

A interface da disciplina aparecerá somente depois, nos cenários de interação.

Se o integrante escolher um novo problema/situação, explique por que ele passou a ser relevante e indique a evidência que motivou sua inclusão.

## Cenário C01 — Triagem Manual de Relatos de Abuso Psicológico e Mapeamento Fragmentado de Reincidência

**Autor(a):** Laura de Souza Parente — 22.123.033-7  
**Persona(s) relacionada(s):** Camila Rocha (P01 — Analista/Administradora) 
**Necessidade relacionada:** R01 e R02 (Consolidação de dados, filtragem de risco e auditoria)
**Situação concreta da Entrega 1 relacionada:** Seção 4.1 e 4.2 (Análise de relatórios dispersos e planilhas sem centralização de inteligência) 
**Hipóteses ainda presentes:** H01 (Necessidade de navegação via indicadores agregados) e H03 (Proteção e sigilo no manuseio de dados sensíveis)

### 1. Cenário inicial

Em um dia de plantão com alto volume de atendimentos no centro de apoio, Camila precisa revisar os relatos recebidos ao longo da semana para identificar casos graves de violência psicológica (como manipulação, chantagem emocional e isolamento) e verificar se há agressores reincidentes em múltiplos atendimentos. Atualmente, sem nenhuma ferramenta automatizada ou pipeline de inteligência artificial focado no problema, Camila abre individualmente arquivos de texto, transcrições de áudios e folhas de cálculo exportadas de diferentes canais de atendimento. Para classificar o tipo de violência, ela lê longos blocos de mensagens e busca manualmente termos-chave como "louca", "sem mim você não é nada" ou "proibida de sair". Quando encontra um caso suspeito, Camila consulta manualmente o Código Penal (Art. 147-B) e manuais em PDF para avaliar se o comportamento descrito atinge os critérios legais de dano emocional. Como trabalha numa bancada compartilhada, a leitura de conversas brutas na ecrã do seu computador expõe constantemente os nomes e desabafos de vítimas a colegas de trabalho que passam pelo local. No final do dia, Camila gasta horas a preencher uma folha de cálculo consolidada para contabilizar os totais de ocorrências, mantendo a sensação de que casos graves podem ter passado despercebidos devido ao cansaço da leitura manual.

### 2. Questões de refinamento

Use os tipos de questões/taxonomia definidos na aula. As perguntas devem revelar informações **ainda ausentes** do cenário, não repetir o que já foi respondido.

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | Qual o volume médio de relatórios e mensagens que Camila precisa ler e interpretar individualmente numa auditoria semanal? | Para quantificar a sobrecarga cognitiva e medir o tempo gasto no processo puramente manual.  | Mapeamento do fluxo operacional e levantamento de volume na Entrega 1. |
| Q2 | Como Camila confirma atualmente se uma conduta descrita num relato se enquadra juridicamente no Art. 147-B do Código Penal? | Para evidenciar a dificuldade de aplicar parâmetros legais a textos não estruturados sem apoio de explicabilidade. | Entrevistas sobre processos de triagem jurídica e manuais de apoio técnico. |
| Q3 | De que forma a exposição de dados sensíveis em ecrãs abertos afeta a rotina e a preocupação de privacidade de Camila? | Para explicitar as lacunas de segurança da informação e sigilo no ambiente físico de trabalho. | Levantamento do contexto de trabalho da Persona P01 na Entrega 3. |

### 3. Cenário refinado

Reescreva o cenário incorporando as respostas. Marque o conteúdo novo de forma consistente (por exemplo, `**[NOVO: ...]**`).

Em um dia de plantão com alto volume de atendimentos no centro de apoio, Camila precisa revisar os relatos recebidos ao longo da semana [NOVO: cerca de 250 a 300 transcrições longas e ficheiros de texto] para identificar casos graves de violência psicológica (como manipulação, chantagem emocional e isolamento) e verificar se há agressores reincidentes em múltiplos atendimentos. Atualmente, sem nenhuma ferramenta automatizada ou pipeline de inteligência artificial focado no problema, Camila abre individualmente arquivos de texto, transcrições de áudios e folhas de cálculo exportadas de diferentes canais de atendimento. Para classificar o tipo de violência, ela lê longos blocos de mensagens e busca manualmente termos-chave como "louca", "sem mim você não é nada" ou "proibida de sair". Quando encontra um caso suspeito, [NOVO: Camila gasta cerca de 20 minutos comparando o depoimento com a redação em PDF do Art. 147-B do Código Penal, anotando num bloco de notas à parte as frases do agressor que fundamentam a sua avaliação]. Como trabalha numa bancada compartilhada perto da circulação de pessoas, [NOVO: a leitura de conversas brutas e dados identificáveis das vítimas fica visível para quem passa ao lado do seu monitor, gerando tensão constante pelo receio de violar regras de privacidade]. No final do dia, Camila gasta horas a preencher uma folha de cálculo consolidada para contabilizar os totais de ocorrências, mantendo a sensação de que casos graves podem ter passado despercebidos devido ao cansaço da leitura manual.   
### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | Camila Rocha (Analista de Atendimento / Administradora — P01). |
| Objetivo(s) | Mapear e classificar tipos de violência psicológica, validar o enquadramento no Art. 147-B do Código Penal e identificar casos de alto risco. |
| Contexto | Estação de trabalho em escritório compartilhado, com alto volume de dados brutos e pressão por análise rápida de casos de vulnerabilidade.  |
| Recursos/informações | Transcrições de áudios, ficheiros de texto, folhas de cálculo dispersas, PDF do Código Penal (Art. 147-B) e apontamentos manuais. |
| Ações | Abrir ficheiros individuais; ler mensagens longas na íntegra; buscar palavras-chave manualmente; consultar legislação em PDF separadamente; somar dados em planilhas. |
| Problemas/rupturas | Carga cognitiva excessiva; demora na checagem legal; ausência de agregação visual de indicadores; exposição de dados pessoais no ecrã em local público. |
| Consequências | Lentidão na identificação de perigo; cansaço físico e mental; risco de falha humana/omissão de casos graves; vulnerabilidade no sigilo das vítimas. |

### 5. Implicações para as próximas entregas

Quais tarefas merecem análise? Quais informações precisam ser coletadas? **Não desenhe a solução ainda.**

Análise de Tarefas (Entrega 5): Mapear detalhadamente a decomposição da tarefa humana de filtragem, leitura, enquadramento legal e compilação de relatórios estatísticos.   

Requisitos de Interação e Protótipo (Entregas futuras):
- Criar mecanismos de agregação visual automática para eliminar a necessidade de leitura manual e contagem em planilhas separadas.  
- Oferecer explicabilidade direta do RAG relacionando a frase da mensagem ao Art. 147-B para economizar tempo de consulta.   
- Implementar regras de privacidade e ocultação visual de dados identificáveis na ecrã principal para garantir segurança em ambientes compartilha

> Repita para C02, C03... com autoria individual.

## Checklist

- [X] Há um cenário completo por integrante.
- [X] Cada cenário tem título, ator, objetivo, contexto e problema.
- [X] O cenário possui origem rastreável na Entrega 1 ou justifica claramente a inclusão de uma nova situação.
- [X] O texto descreve a situação atual, sem antecipar a solução.
- [X] Para TCC sem interface original, o cenário descreve uma prática humana plausível relacionada à contribuição técnica, e não “a falta de uma tela”.
- [X] Questões de refinamento acrescentam informação nova.
- [X] O refinamento mostra claramente o que foi adicionado/alterado.
- [X] Cenários são diferentes o suficiente para cobrir objetivos/problemas relevantes.
- [X] Cada cenário está ligado a persona/necessidade na matriz de rastreabilidade.
