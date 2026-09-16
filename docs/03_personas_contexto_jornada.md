# Entrega 3 — Personas, mapa de empatia, contexto de uso e jornada

**Data:** 05/08/2026  
**Status:** 🟨 em andamento 
**Responsabilidade:** 1 persona por integrante; 1 mapa de empatia, 1 contexto de uso consolidado e 1 jornada por equipe (salvo orientação diferente do docente).

## Objetivo da atividade

Representar grupos de usuários de forma útil para decisões de design. Persona não é personagem decorativo: suas características devem alterar requisitos, prioridades, linguagem, fluxos ou critérios de avaliação.

## Atenção a projetos técnicos

Em TCCs sem interface original, a persona pode representar um **profissional que se apropria da contribuição técnica**: DBA, analista, cientista de dados, administrador, pesquisador, técnico, operador, gestor ou especialista de domínio.

Não escolha um perfil apenas porque “parece combinar” com a tecnologia. Explique **qual objetivo esse perfil teria e qual parte da contribuição do TCC produziria valor para ele**. Se ainda for hipótese, mantenha como hipótese/proto-persona a validar.

Também considere papéis diferentes quando houver tarefas distintas, por exemplo:

- operador que executa análises;
- administrador que configura e gerencia permissões;
- especialista que interpreta resultados;
- gestor que consulta relatórios e decide;
- auditor que revisa histórico.

## Entradas da Entrega 1

Antes de criar personas, retome os tipos de usuários, características relevantes, objetivos e hipóteses registradas na Entrega 1. A persona **não deve transformar uma hipótese inicial em fato por meio de uma história fictícia**.

| Item da Entrega 1 | Status inicial | Evidência disponível agora | Como será tratado nesta entrega |
|---|---|---|---|
| Administrador/ | F | Alinhamento com orientador e escopo do painel web | incorporar / manter como hipótese / descartar / investigar |
| Vítima (usuária do chatbot WhatsApp) | F/H | Interface atual via WhatsApp/Twilio | incorporar / manter como hipótese / descartar / investigar |
| {{usuário/objetivo/característica/H01...}} | F / H / ? | {{...}} | incorporar / manter como hipótese / descartar / investigar |
| {{usuário/objetivo/característica/H01...}} | F / H / ? | {{...}} | incorporar / manter como hipótese / descartar / investigar |

## 1. Personas

### Persona P01 — Camila Rocha

**Autor(a):** Laura de Souza Parente — 22.123.033-7
**Tipo:** Primária  
**Base de evidências:** proto-persona a validar
**Hipóteses da Entrega 1 relacionadas:** H01, H03

![Persona P01](../assets/03_personas/persona_p01.svg)

| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | 34 anos; atua em ambiente de escritório/home office com foco em análise de dados e acompanhamento operacional. |
| Ocupação/papel | Analista Responsável pela Interface Administrativa do Sistema. |
| Conhecimento do domínio | Alto em análise de dados e interpretação de indicadores; médio em conceitos jurídicos (Art. 147-B). |
| Experiência tecnológica | Avançada em sistemas web, ferramentas de BI (Power BI/Looker Studio) e dashboards operacionais. |
| Objetivos | Acompanhar o volume de análises em tempo real, filtrar registros por nível de risco/categoria e auditá-los com agilidade. |
| Necessidades | Visualizar tendências agregadas sem perder a capacidade de inspecionar conversas e justificativas (RAG) individuais. |
| Dores/frustrações | Ter que abrir múltiplos registros manualmente; dashboards poluídos com métricas irrelevantes; risco de exposição de dados sensíveis. |
| Motivadores | Garantir a acurácia do sistema e extrair relatórios/indicadores consistentes para melhoria contínua da solução. |
| Restrições/acessibilidade | Trabalha com múltiplos monitores; necessita de alta densidade de informação com legibilidade e contraste adequados. |
| Ambiente típico de uso | Computador de mesa ou notebook em ambiente de trabalho controlado/escritório. |
| Comportamentos relevantes | Costuma aplicar filtros logo na entrada do sistema e alternar rapidamente entre a lista de registros e a visão detalhada. |

**Decisões de design influenciadas por P01:**

- Estruturação do painel em layout de duas colunas ou modal de detalhe para transição rápida entre lista e conteúdo detalhado.

- Presença de filtros globais destacados no topo (período, categoria de violência, nível de risco).

- Ocultação por padrão de dados pessoais identificáveis na visão em lista, priorizando a privacidade.

  ### Persona P02 — Beatriz Mendes

**Autor(a):** Laura de Souza Parente — 22.123.033-7
**Tipo:** Primária  
**Base de evidências:** Proto-persona baseada no cenário
**Hipóteses da Entrega 1 relacionadas:** H01, H02

![Persona P02](../assets/03_personas/persona_p01.svg)

| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | 24 anos; vivencia trocas de mensagens com o parceiro que geram dúvida e desgaste emocional. |
| Ocupação/papel | Usuária direta do chatbot no WhatsApp. |
| Conhecimento do domínio | Baixo/leigo; não reconhece termos como gaslighting ou invalidação emocional e dúvida de suas próprias percepções. |
| Experiência tecnológica | Familiarizada com uso diário de smartphones e aplicativos de troca de mensagens (WhatsApp). |
| Objetivos | Encaminhar uma conversa suspeita (A01) e obter uma leitura inicial rápida e fundamentada sobre indícios de violência psicológica. |
| Necessidades | Retorno discreto, linguagem simples sem jargões excessivos, preservação de sua privacidade e indicação de redes de apoio. |
| Dores/frustrações | Medo de estar "fazendo tempestade em copo d'água"; receio de que o parceiro acesse o celular ou as notificações. |
| Motivadores | Entender se o que vive é exagero ou algo sério, para poder tomar uma decisão informada sobre buscar ajuda. |
| Restrições/acessibilidade | Uso em smartphone via WhatsApp em momentos sensíveis; requer mensagens objetivas e acolhedoras. |
| Ambiente típico de uso | Smartphone pessoal em momentos privados. |
| Comportamentos relevantes | Copia e cola mensagens de texto ou envia transcrições de áudio do possível agressor para o número do bot. |

**Decisões de design influenciadas por P02:**

- As mensagens geradas pelo chatbot devem ser diretas e discretas para proteger P02 caso o aparelho seja visualizado por terceiros.  
- As análises originadas por P02 devem ser tratadas como dados sensíveis no painel administrativo de P01, exigindo controle de acesso e anonimização.

> Repita para P02, P03... Cada integrante deve produzir ao menos uma persona.

### Síntese das personas

Explique diferenças entre os perfis e qual persona é prioritária. Evite personas duplicadas que só mudam nome/foto.

## 2. Mapa de empatia — equipe

**Persona escolhida:** Camila Rocha
**Justificativa:** É o perfil de usuário priorizado para o recorte do projeto de interface web em IHC.

![Mapa de empatia](../assets/03_personas/mapa_empatia.svg)

Documente também em texto: o que vê; ouve; diz/faz; pensa/sente; dores; ganhos. Diferencie **evidência** de **hipótese**.

## 3. Contexto de uso — consolidação

| Dimensão | Descrição | Implicação de design |
|---|---|---|
| Usuários | Camila Rocha (P01 - Analista/Administradora) e Beatriz Mendes (P02 - Vítima) | Projetar o painel web focado na eficiência de P01, respeitando a sensibilidade das interações de P02. |
| Tarefas | Visualizar indicadores (A03), filtrar histórico (A04), abrir detalhes e justificativa RAG (A05) e observar tendências (A06). | Arquitetura de informação clara: Dashboard -> Histórico Filtrável -> Detalhe do Registro com Explicabilidade |
| Equipamentos | Computadores de mesa ou notebooks para P01 (Seção 5.2); smartphones via WhatsApp para P02 (Seção 5.2). | Interface web responsiva e otimizada para telas médias e grandes (1920x1080) com suporte a tabelas largas. |
| Ambiente físico | Ambiente de trabalho ou estudo/escritório para P01 (Seção 5.1); local privado para P02 (Seção 5.1). | Layout do painel web com contraste adequado, controle de densidade e opção de mascaramento em tela (Seção 5.3). |
| Ambiente social/organizacional | Perfis autorizados com necessidade de controle de acesso, responsabilidade sobre dados e auditoria (Seção 5.4). | Exibir indicação visual de sessão autenticada, níveis de permissão e registros de auditoria/rastreabilidade (Seção 5.5). |
| Papéis/permissões/governança | Restrição de acesso aos dados sensíveis conforme o perfil do administrador (Seção 5.4 e 8) | Diferenciar permissão de visão geral agregada e permissão para abrir o texto completo da conversa (Seção 2.4). |
| Volume de dados/histórico | Acompanhamento de grande volume de registros de análises gerados pelo pipeline (Seção 4.1 e 7.4). | Padrão de busca instantânea, ordenação por nível de risco/data e filtros combinados de alto desempenho (Seção 9.2). |

## 4. Jornada do usuário — equipe

**Persona:** Camila Rocha (P01 — Analista/Administradora) 
**Objetivo da jornada:** Consultar o histórico de análises do sistema, filtrar registros de "Risco Alto" e examinar o detalhe e a justificativa legal (RAG) de um caso específico  
**Início e fim da jornada:** Inicia na abertura do Painel Web Administrativo e termina na conclusão da revisão do detalhe de uma conversa com registro de status.

| Etapa | Situação/ação | Objetivo | Pensamento/emoção | Dor | Oportunidade de design | Evidência |
|---|---|---|---|---|---|---|
| 1 | Acessa o painel web e observa os indicadores gerais de volume, riscos e categorias | Ter um panorama imediato do estado das análises do sistema. | "Quero checar se houve aumento nos registros de risco alto nesta semana." (Alerta / Foco) | Indicadores poluídos ou dificuldade em diferenciar volume de análises da prevalência real. | Cards sintéticos no topo com contagens por risco (Alto, Médio, Baixo) e notas explicativas sobre as métricas. | F/H |
| 2 | Navega até a seção de histórico e aplica filtros por período e nível de risco "Alto" | Isolar rapidamente os registros críticos sem examinar todos os dados | "Preciso filtrar os casos de risco alto para fazer a revisão necessária." (Eficiência) | Filtros confusos ou lentos que forçam consultas manuais pesadas (Seção 4.2). | Barra de filtros em destaque no topo da tabela com atualização imediata e tags de critérios ativos | F/H |
| 3 | {{...}} | {{...}} | {{...}} | Perder a posição da lista ou os filtros aplicados ao abrir um item específico | Painel lateral deslizante (Drawer) ou divisão Master-Detail mantendo a lista visível à esquerda | H |
| 4 | Analisa a conversa, o veredicto (SIM/POSSÍVEL/NÃO) e a fundamentação do Art. 147-B recuperada pelo RAG. | Compreender com clareza como o algoritmo e o RAG fundamentaram o resultado. | "Excelente, os trechos em destaque e a citação da base legal mostram o motivo da classificação." (Confiança) | Dificuldade em interpretar o resultado por falta de clareza na justificativa da IA. | Exibir caixa de explicabilidade com destaques no texto analisado e card com a citação legal do Art. 147-B. | F/H |
| 5 | Marca o caso como "Revisado", aplica uma nota de acompanhamento e fecha o detalhe. | Finalizar a revisão do registro e avançar para o próximo item da lista | "Registro auditado com sucesso. O sistema fundamentou corretamente o resultado." (Dever cumprido) | Falta de feedback de que a revisão foi concluída ou perda da navegação. | Atualização do badge de status na linha do histórico para "Auditado" com feedback visual discreto. | H |

> A jornada pode incluir etapas **antes, durante e depois** do uso do produto. Não transforme a jornada em lista de telas.

## Síntese

Quais necessidades e objetivos devem obrigatoriamente aparecer nos cenários e nas tarefas seguintes?

## Checklist

- [ ] Existe pelo menos uma persona por integrante.
- [ ] As personas não são apenas diferenças demográficas superficiais.
- [ ] Está claro o que é dado real e o que é hipótese/proto-persona.
- [ ] A persona não “validou por ficção” uma hipótese da Entrega 1; afirmações continuam marcadas como hipótese quando não há evidência.
- [ ] Objetivos e dores têm consequência para o design.
- [ ] Contexto de uso está coerente com a Entrega 1.
- [ ] Em TCC sem interface original, a persona possui relação explícita com a contribuição técnica.
- [ ] Papéis administrativos, técnicos e decisórios só foram criados quando possuem objetivos/tarefas diferentes.
- [ ] Jornada possui etapas, dores e oportunidades e não é apenas wireflow.
- [ ] IDs das personas foram adicionados à rastreabilidade.
