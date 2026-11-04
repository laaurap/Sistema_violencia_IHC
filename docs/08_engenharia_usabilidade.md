# Entrega 8 — Ciclo de vida e engenharia de usabilidade

**Data:** 02/11/2026
**Status:** 🟩 concluída
**Responsabilidade:** 1 solução por equipe

## Objetivo da atividade

Transformar o conhecimento acumulado sobre usuários, tarefas, plataforma e contexto em princípios e **metas de usabilidade verificáveis**, mantendo o caráter iterativo do projeto.

## Delimitação do sistema interativo

Antes das características da plataforma, separe:

| Camada | O que pertence ao projeto | O que será avaliado em IHC |
|---|---|---|
| contribuição técnica do TCC | Pipeline de NLP (Faster-Whisper para áudio, spaCy/BERT para classificação de texto), módulo de RAG contextualizado com a legislação brasileira (Art. 147-B do Código Penal) e API REST em FastAPI. | Desempenho do modelo (acurácia, precisão, *recall* do RAG), sendo tratado como precondição técnica do TCC. |
| camada de interação da disciplina | Painel Web Administrativo Mestre e interface conversacional via WhatsApp. | Compreensão da interface, eficácia na triagem de casos graves, tempo de localização de informações, clareza da explicabilidade jurídica do RAG, prevenção de erros e satisfação do auditor. |
| integrações/dados simulados | Histórico de mensagens do WhatsApp simulado por cenários fictícios de abuso (`#C001`, `#C002`), respostas pré-geradas pelo modelo RAG nos testes em papel/baixa fidelidade. | O protótipo em papel (P01) simula o comportamento dos botões de filtro e a navegação de auditoria para avaliar a viabilidade da arquitetura de informação. |

Em um protótipo de disciplina, é aceitável simular processamento ou resultados quando a implementação técnica não estiver integrada, desde que isso seja declarado e a simulação seja suficiente para avaliar a interação.

## 1. Características da plataforma

| Característica | Descrição | Consequência para IHC |
|---|---|---|
| Software | Aplicação Web Responsiva (Painel de Auditoria) + Chatbot Conversacional (WhatsApp Business API). | Necessidade de layouts limpos para desktop na auditoria (Camila) e fluxos de conversa curtos e acolhedores no dispositivo móvel (Beatriz). |
| Hardware/dispositivos | Monitores de desktop/laptop (estação de trabalho da analista) e smartphones (Android/iOS da utilizadora). | A interface P01 deve maximizar a densidade de informação em ecrãs widescreen sem gerar sobrecarga visual. |
| Capacidades | Exibição agregada de métricas estatísticas (KPIs), filtragem dinâmica por Risco (Alto, Médio, Baixo), busca por ID anónimo e explicabilidade RAG. | Exige componentes visuais de alto contraste (badges de cor para Risco Alto) e navegação direta em 1 clique para auditoria. |
| Restrições | Espaço de ecrã limitado em protótipos de baixa fidelidade e restrições de exibição de dados pessoais sensíveis (LGPD). |  Mascaramento obrigatório de dados pessoais na tabela mestre (uso de `#C001` em vez do nome da vítima) para permitir auditoria em escritórios compartilhados. |
| Conectividade/latência | Dependência de rede para processamento dos modelos de linguagem e recuperação de textos jurídicos via RAG. | Necessidade de indicadores claros de progresso/carregamento (*spinners* ou esqueletos de tela) durante o processamento das conversas. |
| Segurança/privacidade | Manipulação de dados de elevado impacto emocional e potencial risco à integridade da vítima. | Interface não deve emitir notificações sonoras |
| Volume de dados/histórico | Elevado volume diário de mensagens e blocos de conversas processadas pelo sistema. | Implementação de paginação ("Mostrando 4 de 130 casos"), filtros dinâmicos rápidos e barra de busca textual para evitar rolagem exaustiva. |
| Tempo de processamento |  Análise de áudio e consulta ao RAG podem levar alguns segundos no backend. |  Exposição prévia da proporção de mensagens processadas (ex: 28/30) na tabela para priorização antes da leitura do relatório completo. |
| Papéis/permissões |  Acesso restrito a analistas e auditores autorizados de redes de apoio/direitos humanos. | Separação estrita entre o canal de acolhimento (WhatsApp) e a plataforma de gestão/auditoria (Painel Web). |


## 2. Princípios gerais do projeto

Inclua apenas normas, leis, padrões e princípios realmente relevantes, explicando **como** afetam o projeto. Não transforme esta seção em lista de links.

| Princípio/norma | Aplicabilidade ao contexto | Decisão/requisito decorrente | Fonte |
|---|---|---|---|
| Contexto de uso | Analistas realizam triagem diária em ambientes corporativos/institucionais com interrupções frequentes. | Painel de visualização imediata com cartões de KPI no topo da ecrã (P01) para retomar o estado de trabalho sem esforço cognitivo. |  Entregas 1, 3 e 5 |
| LGPD, se aplicável | Tratamento de dados pessoais sensíveis relativos a alegações de violência e abusos psicológicos. | Minimização estrita de dados: anonimização automática com identificadores sintéticos (`#C001`) na interface mestre de auditoria. | Legislação Oficial (LGPD) |
| Acessibilidade | Visibilidade do estado do sistema, prevenção de erros e reconhecimento em vez de memorização |  Botões de ação destacados com rótulos claros (`AUDITAR`, `ALTO`), contraste adequado nas etiquetas de risco e contadores visíveis. | WCAG 2.1 / Heurísticas de Nielsen |
| Lei nº 14.188/2021 (Art. 147-B CP) | Tipificação do crime de violência psicológica contra a mulher. | Inclusão de módulo visual de explicabilidade jurídica associando trechos das conversas diretamente ao Art. 147-B do CP no RAG. | Código Penal Brasileiro |


## 3. Metas de usabilidade

Usabilidade deve ser discutida **no contexto de uso**. Metas quantitativas devem dizer o que será medido, em qual tarefa, com qual população e qual limite será considerado aceitável.

### 3.1 Metas qualitativas

| Meta | Para quem/tarefa | Evidência desejada | Justificativa |
|---|---|---|---|
| Compreensão clara da fundamentação legal RAG | Analista Camila / T01 (Auditar histórico) | Participante expressa verbalmente entender por que o caso foi classificado como alto risco ao ler o enquadramento do Art. 147-B. | A confiança da analista na IA depende da transparência e clareza da explicabilidade jurídica oferecida pelo modelo. |
| Perceção de privacidade e segurança | Analista Camila / T03 (Triagem diária) | Participante reconhece espontaneamente que a utilização de IDs anónimos (#C001) protege os dados da vítima no ecrã. | Garante conformidade com os princípios éticos de IHC e proteção de dados sensíveis em ambientes de trabalho compartilhados. |
| Simplicidade no acolhimento emergencial | Vítima Beatriz / T02 (Submeter relato) | Utilizadora considera a interação com o bot no WhatsApp direta, acolhedora e isenta de jargões técnicos complexos. | Minimiza a fricção de uso em momentos de elevado estresse emocional ou urgência. |

### 3.2 Metas quantitativas

| ID | Dimensão | Métrica | Tarefa/escopo | Meta | Como medir | Justificativa |
|---|---|---|---|---|---|---|
| MU01 | eficácia | taxa de conclusão de triagem de casos graves sem ajuda | T03 (Filtrar e identificar casos de Risco Alto na P01) | ≥ 90% |Teste de usabilidade observado com tarefas guiadas. | A analista deve conseguir isolar emergências na listagem mestre de forma autónoma e sem cometer erros. |
| MU02 | eficiência | tempo mediano para acionar a auditoria de um caso prioritário | T01 (Localizar o caso #C001 e clicar em `AUDITAR`) | ≤ 15 segundos | Medição via cronómetro durante o teste de percurso cognitivo. | A priorização de atendimento a situações de risco iminente exige acesso rápido a partir da ecrã principal. |
| MU03 | satisfação | avaliação da clareza da interface e explicabilidade RAG | T01–T03 (Avaliação global das telas e do questionário I01) | ≥ 4,0 / 5,0 | Média obtida na escala Likert do Questionário I01. | Garante aceitação do sistema pelos profissionais de direitos humanos e suporte social. |


### 3.3 Priorização das metas (se exigida na disciplina)

Se o professor solicitar porcentagens que somem 100%, trate-as como **peso de prioridade**, não como métrica de usabilidade.

| Meta | Peso de prioridade | Justificativa |
|---|---:|---|
| MU01 | 45% | A identificação correta dos casos graves é crítica; falhar na triagem de um caso de risco alto pode ter consequências graves para a vítima. |
| MU02 | 30% | Reduzir o tempo de auditoria é fundamental para lidar com o elevado volume diário de chamados recebidos pelo sistema. |
| MU03 | 25% | A aceitação e a confiança na explicabilidade jurídica do RAG garantem a adoção contínua da ferramenta pelos profissionais. |
| Total | 100% | |

## 4. Como o ciclo será iterado

Explique que artefatos serão revisitados após protótipos e avaliações.

1. Revisão dos Artefatos de Análise (Entregas 1–5): As correções recebidas dos docentes sobre as personas, cenários, HTA/GOMS/CTT e rastreabilidade alimentam os ajustes do protótipo.
2. Avaliação do Protótipo de Baixa Fidelidade (Entrega 6): As fragilidades identificadas durante o walkthrough da Tela P01 (ex: necessidade de exibir a proporção de mensagens 28/30) foram corrigidas diretamente na arquitetura de informação.
3. Validação do Instrumento de Recolha (Entrega 7): As métricas do questionário I01 servem de base para validar se as metas qualitativas e quantitativas (MU01, MU02, MU03) são atingidas.
4. Refinamento para Alta Fidelidade (Entregas 9–10): As metas definidas nesta Entrega 8 guiarão a construção dos wireframes e protótipos interativos no Figma, assegurando que o layout final respeite os limites de eficiência e clareza estabelecidos.

## Checklist

- [X] Capacidades e restrições têm impacto de IHC explicitado.
- [X] Está claro o limite entre contribuição técnica do TCC e camada interativa da disciplina.
- [X] Resultados/processamento simulados no protótipo foram explicitados.
- [X] Metas de usabilidade avaliam a interação, não substituem métricas técnicas do TCC.
- [X] Normas/princípios estão contextualizados, não apenas copiados.
- [X] Metas quantitativas são mensuráveis e associadas a tarefas/público.
- [X] Eficácia, eficiência e satisfação são consideradas quando pertinentes.
- [X] Metas poderão ser verificadas nas Entregas 12–14.
