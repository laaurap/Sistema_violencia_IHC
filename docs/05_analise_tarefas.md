# Entrega 5 — Análise de tarefas: HTA, GOMS e CTT

**Data:** 17/09/2026  
**Status:** 🟩 concluída
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
| T03 | Filtrar casos por nível de risco e emitir parecer consolidado | Camila Rocha (P01) / Cenário C01 | Frequência diária / Média-Alta criticidade (Triagem de casos graves) | Laura de Souza Parente |

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
| 0 | Auditar atendimento e validar fundamentação legal (RAG) | Plano 0: Executar 1 -> 2 -> 3 -> 4 / 1 ou 2 etc.> | Ações encadeadas dependem da clareza da explicabilidade visual do RAG. |
| 1 | Acessar a lista geral de históricos de atendimentos | Plano 1: Executar 1.1 depois 1.2 (ou 1.2 direto se o registro já estiver visível na tela) | Exibir indicadores de risco agregados evita a abertura desnecessária de registros. |
| 1.1 | Aplicar filtro por nível de Risco "Alto" | Operação de seleção do botão "ALTO" ou digitação no campo de busca | {{...}} |
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

- **Method M1:** Envio por encaminhamento de texto direto
  - Operators: {{perceber, apontar, clicar, digitar, decidir... conforme o nível adotado}}
  - Operator O1: Perceber conduta abusiva na conversa de terceiros no WhatsApp.
  - Operator O2: Selecionar e copiar/encaminhar o bloco de mensagens suspeitas.
  - Operator O3: Abrir a conversa com a assistente virtual (Guardiã AI) no WhatsApp.
  - Operator O4: Colar o texto no chat e clicar no botão "Enviar".
  - Operator O5: Aguardar o processamento do pipeline (NLP + RAG).
  - Operator O6: Ler a mensagem de resposta com o diagnóstico de risco, justificativa e números de apoio (180/188).
  - Operator O7: Decidir se aciona um canal de emergência ou salva a orientação recebida.
  - 
- **Method M2:** Envio por mensagem de áudio transcrito
  - Operators: {{...}}
  - Operator O1: Receber/gravar áudio com relato ou fala suspeita do agressor.
  - Operator O2: Encaminhar o arquivo de áudio para o chat da assistente no WhatsApp.
  - Operator O3: Aguardar a transcrição automática (Faster-Whisper) e o processamento de análise.
  - Operator O4: Ler a confirmação da transcrição e o diagnóstico de risco gerado.
  - Operator O5: Decidir pela leitura dos canais de apoio disponibilizados.
  - 
- **Selection Rule SR1:** usar M1 quando a usuária tiver mensagens de texto digitadas ou cópias de chats de conversa; usar M2 quando a interação for proveniente de gravações de voz ou mensagens de áudio encaminhadas.


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
| `>>` (Habilitação | A conclusão de uma tarefa habilita o início automático da tarefa seguinte. | Acessar lista `>>` Exibir lista* / *Definir aprovação `>>` Salvar decisão* |
| `[]=` (Escolha | O utilizador escolhe e executa uma entre várias tarefas alternativas. | *Aprovar veredicto `[]=` Reclassificar risco* |
| `|||` (Concorrência | As tarefas podem ser executadas de forma simultânea ou alternada sem ordem fixa. | *Ler mensagens `|||` Verificar RAG sugerido* |
| `*` (Repetição | A tarefa é executada repetidamente até que uma condição de término seja satisfeita. | *Auditar Registro de Atendimento\** |
| `[|]` (Desativação | Uma tarefa de interrupção cancela a tarefa principal que estava em processamento. | *Cancelar Auditoria `[|]` Processar Análise* |


Identifique, quando aplicável, tarefas de usuário, sistema, interação e tarefas abstratas. Verifique se concorrência, escolha, habilitação, desabilitação e repetição estão representadas corretamente segundo a notação adotada em aula.


#### Tarefas identificadas no CTT:
- Tarefa Abstrata (Retângulo simples): Auditar atendimento e validar RAG
- Tarefa de Usuário (Ícone de pessoa): Analisar Pertinência do Artigo Penal 147-B (Processo cognitivo humano).
- Tarefa do Sistema (Ícone de computador): Recuperar Trechos e Gerar Explicabilidade RAG* (Processamento automatizado do servidor).
- Tarefa de Interação (Ícone de pessoa/computador): Selecionar Filtro de Risco Alto na Tabela* (Ação direta na interface).

---

## Síntese da equipe

Quais problemas de interação, oportunidades e requisitos apareceram a partir das modelagens? Quais tarefas irão para o protótipo e para o teste de usabilidade?


A partir das modelagens HTA, GOMS e CTT, emergiram importantes requisitos de usabilidade e oportunidades de design para as próximas etapas de prototipagem:

- Padrão Master-Detail para Redução de Carga Cognitiva: O HTA revelou a necessidade de manter a lista de atendimentos visível enquanto o detalhe do RAG é examinado, evitando que a analista perca o contexto de busca ao auditar múltiplos casos.

- Explicabilidade RAG em Bloco: A análise GOMS e as diretrizes técnicas confirmaram que o módulo RAG não deve apenas exibir o texto da lei, mas fornecer uma frase explicativa curta vinculando o trecho do abuso à norma jurídica (ex: Art. 147-B), reduzindo o tempo de tomada de decisão do profissional.   

- Padrões Acolhedores no WhatsApp: A modelagem GOMS do fluxo do WhatsApp indicou que a resposta da IA precisa manter a barreira de entrada baixa, fornecendo um diagnóstico limpo e botões diretos de emergência (180 e 188) sem sobrecarregar a vítima com jargões técnicos.  

- Demandas para Protótipo: As tarefas T01 e T03 serão a base para os protótipos de papel da Entrega 6, enquanto a tarefa T02 guiará o fluxo do chatbot.

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
