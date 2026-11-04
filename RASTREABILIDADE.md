# Matriz de rastreabilidade de IHC

A matriz deve ser atualizada ao longo do semestre. Ela ajuda a demonstrar que a interface não surgiu arbitrariamente e registra **como o conhecimento da equipe evoluiu**.

Para projetos cujo TCC não previa interface, esta matriz é especialmente importante: deve ficar visível a passagem da **contribuição técnica do TCC** para um **cenário de uso plausível**, e desse cenário para as decisões de interação.

## 1. Derivação do escopo de IHC a partir do TCC

| Elemento | Registro da equipe | Evidência/justificativa | Estado |
|---|---|---|---|
| Tema do TCC | Sistema de Detecção de Violência Psicológica em Conversas| {{documento/TCC}} | definido |
| Resultado técnico esperado | {{algoritmo, análise, sistema, modelo, API...}Pipeline de NLP (spaCy + BERT) + RAG + API FastAPI + Integração WhatsApp (n8n/Twilio) + Painel Web} | {{...}} | definido |
| O TCC previa interface? | Parcialmente | {{...}} | definido |
| Capacidade/contribuição central | Classificar indícios e categorias de violência psicológica em texto e fundamentar com referências legais/acadêmicas | {{...}} | definido |
| Possíveis beneficiários/stakeholders | Vítimas de violência psicológica, administradores/analistas autorizados do sistema, rede de apoio | {{fonte ou hipótese}} | F / H |
| Usuário escolhido para IHC | {{...}} | {{por que esse perfil}} | F / H / ? |
| Objetivo principal do usuário | {{...}} | {{...}} | F / H / ? |
| Contexto de uso adotado | {{...}} | {{...}} | F / H / ? |
| Interface/recorte de IHC | {{...}} | {{como deriva dos itens acima}} | proposta / revisada |
| Relação com o TCC | parte prevista / extensão conceitual / protótipo demonstrativo / outra | {{...}} | definido |

> Se o escopo de IHC mudar ao longo do semestre, preserve a decisão anterior no histórico e registre **qual evidência motivou a mudança**.

## 2. Registro de hipóteses e lacunas da Entrega 1

Use esta tabela para itens importantes marcados como `[H]` ou `[?]`. Preserve o histórico: não apague uma hipótese refutada.

| ID | Afirmação / dúvida inicial | Tipo | Por que importa | Como/onde investigar | Evidência obtida | Estado atual | Impacto no projeto |
|---|---|---|---|---|---|---|---|
| H01 | {{...}} | H / ? | {{...}} | Entrega 2 / 3 / 7 / outra | {{link/fonte ou PENDENTE}} | aberta / sustentada / refutada / refinada | {{...}} |
| H01 | Analistas de direitos humanos sentem necessidade de explicabilidade jurídica RAG (Art. 147-B) para confiar na classificação da IA. | (H) | Determina a aceitação da ferramenta pelo profissional e reduz o tempo de auditoria manual. | Entrega 7 (Questionário I01 e Análise de Usabilidade) | Revisão de literatura e formulário I01 aplicado a especialistas | Sustentada | Inclusão do painel lateral de explicabilidade RAG na tela P02. |
| H02 | O destaque de excertos diretos nas mensagens reduz a carga cognitiva da analista durante a auditoria. | (H) | Evita a leitura exaustiva de todo o histórico de conversas do WhatsApp. | Entrega 6 (Walkthrough P01) e Entrega 7 (I01) | Teste de percurso cognitivo com protótipo em papel | Sustentada | Manutenção do realce visual nos balões de chat. |
| H03 | O uso de identificadores anônimos (#C001) na listagem principal satisfaz os requisitos de privacidade da LGPD. | (H) | Protege os dados sensíveis da vítima em ambientes de trabalho compartilhados. | Entrega 6 (Walkthrough P01) | Validação no protótipo de baixa fidelidade P01 | Sustentada | Ocultação do nome da vítima na tabela mestre do Painel Web. |
| H04| A disponibilização de botões de acionamento rápido (180/188) no WhatsApp é prioritária após a emissão do diagnóstico. | (?) | Garante encaminhamento de emergência caso a vítima esteja em risco iminente. | Entrega 5 e validação com personas | Análise de tarefas de acolhimento de emergência | Refinada | Inclusão de botões diretos de emergência ao final da resposta da IA. |

## 3. Rastreabilidade entre contribuição técnica, necessidades e artefatos

| ID | Capacidade do TCC utilizada | Necessidade/problema | Persona | Cenário problema | Objetivo/tarefa | HTA/GOMS/CTT | Cenário de interação / signos | MoLIC | Tela(s) Figma | Heurística / problema | Tarefa no teste | Decisão/melhoria |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| R01 | {{ex.: recomendação de otimização}} | {{...}} | {{P01}} | {{C01}} | {{T01}} | {{links}} | {{...}} | {{M01}} | {{F01...}} | {{V01 ou —}} | {{UT01}} | {{...}} |
| R01 | Classificação NLP de Risco + Explicabilidade RAG (Art. 147-B) | Dificuldade em auditar volume alto de chamados com rigor legal e sigilo. | Camila Rocha (P01) | C01 — Auditoria Semanal de Atendimentos | T01: Auditar histórico e validar fundamentação RAG | HTA T01 | Identificadores mascarados (#C001), badges de risco, cards RAG | M01 (Painel Web) | P01 (Histórico) / P02 (Detalhe RAG) | Visibilidade do estado do sistema / Carga cognitiva | UT01: Localizar caso grave e validar RAG | Adicionado campo opcional de observação da auditoria. |
| R02 | Transcrição de áudio (Faster-Whisper) + Diagnóstico Acolhedor | Necessidade de avaliação rápida e discreta de conduta abusiva em momentos de dúvida. | Beatriz Mendes (P02) | C02 — Acolhimento Emergencial via WhatsApp | T02: Submeter conversa e receber diagnóstico | GOMS T02 | Mensagens acolhedoras, destaques em texto, botões 180/188 | M02 (Chatbot) | Fluxo Chatbot WhatsApp | Prevenção de erros / Acessibilidade | UT02: Encaminhar texto/áudio e ler orientação | Resposta formatada em tópicos curtos sem jargões jurídicos excessivos. |
| R03 | Agregação estatística de indicadores e filtros por risco | Necessidade de triagem diária para isolar casos de risco alto sem abrir registo por registo. | Camila Rocha (P01) | C01 — Triagem Diária de Casos | T03: Filtrar casos por nível de risco e emitir parecer | CTT T03 | Indicadores KPI (Total, Alto Risco, Categoria), filtros ALTO/MÉDIO/BAIXO | M01 (Painel Web) | P01 (Painel / Histórico Geral) | Reconhecimento em vez de recuperação | UT03: Filtrar lista por risco ALTO | Adicionado contador no rodapé e paginação.

## 4. Rastreabilidade de padrões de interface

Use esta tabela quando o projeto incorporar padrões como dashboard, relatório, histórico, filtros ou administração. O objetivo é **justificar o padrão**, não apenas listar telas.

| ID da tela/fluxo | Padrão de interface | Objetivo/tarefa que justifica | Informação/ação principal | Evidência de necessidade | Artefatos relacionados |
|---|---|---|---|---|---|
| P01 | Dashboard com KPIs agregados | T03: Triagem rápida de casos e visualização da carga de trabalho diária. | Total de casos (132), alertas de alto risco (28), categoria mais frequente. | H01 / Validação no Walkthrough da Entrega 6 | C01, T03 (CTT), Protótipo P01 |
| P01 | Tabela mestre com filtros dinâmicos e busca | T01 / T03: Isolar atendimentos por nível de risco (ALTO, MÉDIO, BAIXO) e buscar por ID anônimo (#C001). | ID mascarado, data, risco, categoria principal, proporção de mensagens (28/30), botão `AUDITAR`. | H03 / Princípios de privacidade LGPD e redução de esforço de busca | C01, T01 (HTA), Protótipo P01 |
| P02 | Visão Detalhada Mestre-Detalhe (*Split-screen*) | T01: Auditar mensagens destacadas do WhatsApp e validar fundamentação do RAG (Art. 147-B). | Transcrição com destaques no lado esquerdo; Card de lei RAG, parecer e botões `Aprovar`/`Reclassificar` no lado direito. | H01, H02 / Necessidade de explicabilidade e auditoria *Human-in-the-loop* | C01, T01 (HTA), Protótipo P02 |
| **Fluxo WhatsApp** | Interface de conversa (*Chatbot*) | T02: Submissão de relatos de abuso por texto ou áudio e recepção de orientação acolhedora. | Balões de mensagem com diagnóstico simples, nível de risco e números de apoio direto (180/188). | H04 / Baixa barreira de entrada e familiaridade com a ferramenta | C02, T02 (GOMS), Fluxo WhatsApp |

## 5. Registro de mudanças de escopo

| Data | O que mudou | Evidência/feedback que motivou | Artefatos afetados | Responsável |
|---|---|---|---|---|
| 17/09/2026 | Inclusão da proporção de mensagens processadas (ex: 28/30) na tabela P01. | Simulação do HTA T01: a analista precisava de uma métrica prévia de densidade do abuso antes de abrir o detalhe. | HTA T01, Protótipo P01, RASTREABILIDADE.md | Laura de Souza Parente |
| 18/09/2026 | Adoção estrita de IDs mascarados (#C001, #C002) na listagem principal da P01. | Feedback do walkthrough da Entrega 6: necessidade de evitar a exposição indevida de dados sensíveis da vítima em ambiente compartilhado. | Protótipo P01, Entrega 6, RASTREABILIDADE.md | Laura de Souza Parente |
| 29/10/2026 | Formalização da técnica de questionário I01 focada na triagem da P01 e na explicabilidade RAG. | Definição da Entrega 7: necessidade de validar estatisticamente a utilidade dos cartões KPI e a confiança no Art. 147-B. | Entrega 7, RASTREABILIDADE.md | Laura de Souza Parente |

## Como usar

- Use identificadores estáveis (`H01`, `P01`, `C01`, `T01`, `M01`, `F01`, `UT01`).
- Quando uma necessidade/problema tiver origem em hipótese da Entrega 1, cite o ID correspondente.
- Em TCC sem interface original, pelo menos uma linha deve mostrar claramente **como uma capacidade técnica chega até uma tarefa de usuário e uma tela/fluxo**.
- Uma linha pode se desdobrar quando um objetivo possui múltiplos caminhos.
- Não force relação inexistente: se algo ainda não foi modelado, marque `PENDENTE`.
- Ao remover uma funcionalidade, registre a decisão em vez de apagar silenciosamente o histórico.
- Dashboard, CRUD, filtros e relatórios só devem aparecer quando houver objetivo/tarefa que os justifique.
