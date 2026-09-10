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
| Usuários | {{...}} | {{...}} |
| Tarefas | {{...}} | {{...}} |
| Equipamentos | {{...}} | {{...}} |
| Ambiente físico | {{...}} | {{...}} |
| Ambiente social/organizacional | {{...}} | {{...}} |
| Papéis/permissões/governança | {{...}} | {{...}} |
| Volume de dados/histórico | {{...}} | {{...}} |

## 4. Jornada do usuário — equipe

**Persona:** {{P01}}  
**Objetivo da jornada:** {{...}}  
**Início e fim da jornada:** {{...}}

| Etapa | Situação/ação | Objetivo | Pensamento/emoção | Dor | Oportunidade de design | Evidência |
|---|---|---|---|---|---|---|
| 1 | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |

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
