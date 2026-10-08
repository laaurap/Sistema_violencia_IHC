# Entrega 5 — Análise de tarefas: HTA, GOMS e CTT

**Data:** 17/09/2026  
**Status:** 🟨 em andamento
**Responsabilidade:** cada integrante modela pelo menos 1 HTA, 1 GOMS e 1 CTT. As três técnicas podem abordar a mesma funcionalidade ou funcionalidades distintas, conforme a orientação da disciplina.

## Objetivo da atividade

Modelar tarefas importantes sob perspectivas complementares: decomposição hierárquica (HTA), estrutura de metas/métodos/operações (GOMS) e relações temporais entre tarefas (CTT). O diagrama deve ser acompanhado de interpretação textual.

## Para projetos cujo TCC não previa interface

Modele **tarefas humanas relacionadas ao uso da contribuição técnica**, e não a implementação interna do algoritmo. Exemplos de boas tarefas para análise:

- investigar uma consulta de baixo desempenho;
- configurar uma análise e selecionar parâmetros;
- submeter um dataset e verificar sua validade;
- acompanhar uma execução demorada;
- comparar dois resultados/modelos;
- interpretar uma recomendação e decidir se a aceita;
- localizar uma execução anterior usando busca/filtros;
- gerar e compartilhar um relatório;
- administrar papéis/permissões quando isso for parte do trabalho real;
- revisar um alerta e registrar uma decisão.

Um CRUD pode gerar tarefas relevantes, mas “cadastrar usuário” só merece modelagem se tiver significado no domínio (papéis, validações, riscos, permissões, dependências).

## Seleção das tarefas

| ID | Tarefa | Persona/cenário de origem | Frequência/criticidade | Autor responsável |
|---|---|---|---|---|
| T01 | Auditar histórico de atendimentos e validar explicabilidade legal (RAG) | Camila Rocha (P01) / Cenário C01 | Frequência semanal / Alta criticidade (Garante rigor técnico e sigilo) | Laura de Souza Parente |
| T02 | Submeter conversa suspeita via WhatsApp e receber diagnóstico acolhedor | Beatriz Mendes (P02) / Cenário C02 | Frequência pontual/crítica / Altíssima criticidade (Acolhimento de emergência) | Laura de Souza Parente |
| T03 | Filtrar casos por nível de risco e emitir parecer consolidado | Camila Rocha (P01) / Cenário C01 | Frequência diária / Média-Alta criticidade (Triagem de casos graves) | {Laura de Souza Parente |

> Priorize tarefas necessárias para que o usuário alcance objetivos centrais. Não desperdice a modelagem em ações triviais isoladas, como “clicar em login”, se o objetivo relevante é maior. Da mesma forma, não modele o funcionamento interno do algoritmo como se fosse uma tarefa humana.

---

## HTA — T01 Auditar histórico de atendimentos e validar explicabilidade legal (RAG)

**Autor(a):** Laura de Souza Parente — 22.123.033-7

### Descrição da tarefa

{{objetivo, ponto de início, conclusão esperada, contexto}}

- Objetivo: Localizar um atendimento de alto risco no painel web, examinar o bloco de mensagens processadas pelo modelo de NLP e validar se a fundamentação gerada pelo módulo RAG (Art. 147-B do Código Penal) está adequada para aprovação do parecer.
  
- Ponto de início: A analista Camila acessa o painel administrativo na tela de histórico geral de atendimentos.
     
- Conclusão esperada: O parecer de auditoria do atendimento é registrado no sistema como "Validado", salvaguardando a fundamentação jurídica e a proteção dos dados.
  
- Contexto: Estação de trabalho em ambiente de escritório compartilhado, necessitando de navegação rápida e preservação de sigilo visual. 

### Diagrama

![HTA T01](../assets/05_tarefas/hta_t01.svg)

### Decomposição e planos

| ID | Objetivo/operação | Plano/ordem | Problema ou decisão de design observada |
|---|---|---|---|
| 0 | Auditar atendimento e validar fundamentação legal (RAG) | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 1 | Acessar a lista geral de históricos de atendimentos | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 1.1 | Aplicar filtro por nível de Risco "Alto" | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 1.2 | Buscar por data ou código do atendimento | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 2 | Selecionar e abrir o detalhe do registro de atendimento | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 2.1 | Clicar na ação "Auditar / Ver Detalhes RAG" | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 3 | Examinar mensagens e fundamentação legal recuperada | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 3.1 | Ler as mensagens do bloco identificadas com indício de abuso | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 3.2 | Analisar o artigo do Código Penal (Art. 147-B) e a justificativa RAG | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 4 | Registrar decisão de auditoria | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 4.1 | Confirmar e aprovar veredicto da IA | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |
| 4.2 | Reclassificar nível de risco ou ajustar observação | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |

**Verificação do HTA:**

- O objetivo 0 representa uma meta do usuário? O objetivo 0 representa a meta real do utilizador (garantir auditoria rápida e fundamentada).
- As subtarefas são necessárias e suficientes? As subtarefas cobrem desde a triagem até ao registo final.
- Os **planos** indicam ordem, alternativa, repetição ou condição? Os planos definem sequências, condições de decisão e alternativas.
- A decomposição parou em nível útil para projeto de interação? A decomposição foi interrompida no nível de clique/leitura, ideal para prototipagem.

---

## GOMS — T02 Submeter conversa suspeita via WhatsApp e receber diagnóstico acolhedor

**Autor(a):** Laura de Souza Parente — 22.123.033-7

### Goal

`G0: Obter avaliação de risco e orientação segura sobre uma conversa suspeita recebida no WhatsApp`

### Métodos, operadores e regras de seleção

- **Method M1:** {{...}}
  - Operators: {{perceber, apontar, clicar, digitar, decidir... conforme o nível adotado}}
- **Method M2:** {{...}}
  - Operators: {{...}}
- **Selection Rule SR1:** usar M1 quando {{condição}}; usar M2 quando {{condição}}.

> Não chame qualquer passo de “método”. Em GOMS, métodos são sequências alternativas capazes de atingir uma meta; regras de seleção explicam quando escolher entre eles.

---

## CTT — T03 Filtrar casos por nível de risco e emitir parecer consolidado

**Autor(a):** Laura de Souza Parente — 22.123.033-7

### Descrição

A tarefa T03 descreve as relações temporais e a concorrência entre as ações da analista (Camila) e o processamento do sistema web ao realizar a triagem diária de atendimentos, aplicando filtros dinâmicos de risco, gerando pré-visualizações do RAG e exportando um relatório consolidado do período.

### Diagrama

![CTT T03](../assets/05_tarefas/ctt_t03.svg)

### Legenda e relações temporais usadas

| Operador/relação | Significado no diagrama | Exemplo no modelo |
|---|---|---|
| {{...}} | {{...}} | {{...}} |

Identifique, quando aplicável, tarefas de usuário, sistema, interação e tarefas abstratas. Verifique se concorrência, escolha, habilitação, desabilitação e repetição estão representadas corretamente segundo a notação adotada em aula.


#### Tarefas identificadas no CTT:
- Tarefa Abstrata (Retângulo simples):
- Triar e Auditar Casos Semanais de Violência (Meta global que se decompõe).
- Tarefa de Usuário (Ícone de pessoa): Analisar Pertinência do Artigo Penal 147-B (Processo cognitivo humano).
- Tarefa do Sistema (Ícone de computador): Recuperar Trechos e Gerar Explicabilidade RAG* (Processamento automatizado do servidor).
- Tarefa de Interação (Ícone de pessoa/computador): Selecionar Filtro de Risco Alto na Tabela* (Ação direta na interface).

---

## Síntese da equipe

Quais problemas de interação, oportunidades e requisitos apareceram a partir das modelagens? Quais tarefas irão para o protótipo e para o teste de usabilidade?

## Checklist

- [X] Cada integrante produziu ao menos 1 HTA, 1 GOMS e 1 CTT.
- [X] Cada artefato identifica autor e tarefa.
- [X] Diagramas são legíveis e possuem fonte editável quando possível.
- [X] HTA contém planos, não apenas árvore de tópicos.
- [X] GOMS distingue Goals, Operators, Methods e Selection Rules.
- [X] CTT usa operadores temporais e tipos de tarefa coerentes.
- [X] Há texto explicando cada diagrama.
- [X] Tarefas estão ligadas a cenários/personas na rastreabilidade.
- [X] Em TCC técnico, as tarefas descrevem o que a pessoa faz com a contribuição/resultados, não passos internos do código.
- [X] CRUDs, relatórios, filtros e atividades administrativas foram escolhidos por relevância ao objetivo do usuário.
