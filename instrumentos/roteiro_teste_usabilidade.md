# Roteiro de teste de usabilidade

## 1. Antes da sessão

- verificar protótipo/versão;
- testar gravação e áudio;
- abrir formulários/planilhas;
- limpar dados de sessão/conta de teste;
- separar instruções das tarefas;
- confirmar consentimento e duração;
- quando o protótipo usar resultados/processamentos simulados, preparar dados realistas e manter a simulação consistente entre participantes.

## 2. Abertura padronizada

- agradecer participação;
- explicar objetivo geral sem revelar hipóteses específicas;
- reforçar que o produto, não a pessoa, está sendo avaliado;
- explicar possibilidade de interrupção;
- obter consentimento;
- explicar *think aloud* apenas se essa técnica for usada.

### Quando a interface é um protótipo de aplicação do tema do TCC

Explique de forma simples que a sessão avalia **como a pessoa interage com o protótipo**, e não a precisão/desempenho científico do algoritmo, modelo ou estudo do TCC.

Se algum resultado técnico estiver simulado, não engane o participante sobre o nível de implementação. Use uma explicação compatível com o objetivo do teste, sem antecipar o caminho da tarefa.

## 3. Perfil pré-teste

Colete somente informações relevantes à interpretação dos resultados: experiência com domínio, frequência de uso de soluções similares, familiaridade com ferramentas profissionais, necessidades de acessibilidade pertinentes etc.

Para perfis especializados (DBA, analista, pesquisador, administrador, técnico), registre os critérios usados para considerar o participante representativo. Se for participante proxy, registre essa condição e a limitação.

## 4. Tarefas

| ID | Instrução ao participante | O moderador pode esclarecer | O moderador não deve dizer |
|---|---|---|---|
| UT01 | {{...}} | {{termos do cenário}} | {{nome/local do botão}} |
| UT01 | *"Você acabou de iniciar seu turno de revisão como analista e precisa verificar quantos atendimentos estão classificados como urgentes hoje e isolar apenas esses registros na listagem principal."* | O significado geral do papel de *Analista de Triagem* e que os dados são simulados. | O nome dos cards KPI superiores (`132` / `28`) ou onde clicar para ativar o filtro `ALTO`. |
| UT02 | *"Uma coordenação pediu para verificar se existe algum registro inexistente na busca. Pesquise e, ao obter tela sem resultados, retorne à visualização completa de todos os casos."* | Que o protótipo possui simulação de busca sem correspondência (`#C999`). | O nome ou localização do botão `LIMPAR FILTROS / RESTAURAR BUSCA`. |
| UT03 | *"Abra um atendimento sinalizado para revisar a conversa registrada, verifique os trechos que motivaram o alerta do sistema e a base legal utilizada, e conclua a validação concordando com a classificação sugerida."* | O contexto jurídico básico do **Art. 147-B** (violência psicológica) e o caráter preliminar do parecer da IA. | Qual botão clicar para abrir a auditoria (`AUDITAR` / `VER DETALHES`) ou aprovar o parecer. |
| UT04 | *"Suponha que, ao revisar um atendimento de alto risco, você discorde da gravidade estimada pelo sistema e considere necessário alterar o nível de risco para um grau menor (Médio), deixando registrado o motivo técnico dessa mudança."* | Que o analista humano possui autonomia para sobrescrever a sugestão preliminar da IA. | O rótulo ou posição do botão `Reclassificar Risco` e do modal de justificativa. |
| UT05 | *"Antes de encerrar o turno, explore as abas de análises e relatórios para verificar a taxa de concordância do sistema e localizar onde pré-visualizar ou exportar um relatório consolidado."* | Que o painel possui visões gerenciais complementares à fila de triagem. | Os nomes exatos dos itens do menu lateral (`Análises` / `Relatórios`) ou os botões de exportação. |

Tarefas podem envolver, conforme o escopo: localizar informação em dashboard; filtrar histórico; configurar análise; comparar resultados; gerar relatório; revisar alerta; editar permissão; recuperar-se de falha.

A tarefa deve expressar **objetivo do usuário**, e não “clique no filtro”, “abra o CRUD” ou “vá ao dashboard”.

## 5. Durante a tarefa

Registrar início/fim, sucesso, erros, hesitações, comentários, pedidos de ajuda e intervenções do moderador. Não transformar silêncio do participante em “problema” sem evidência adicional.

Observe também, quando pertinente:

- compreensão de métricas/termos técnicos;
- percepção de status de processamento;
- escolha e remoção de filtros;
- interpretação de estados vazios/erro;
- prevenção de ações destrutivas;
- entendimento de papéis/permissões;
- confiança ao interpretar resultados/recomendações.

## 6. Pós-tarefa

Aplicar a escala definida no plano (por exemplo 1–7) e registrar comentário curto: “O que tornou essa tarefa fácil ou difícil?”

## 7. Encerramento

- perguntas gerais;
- agradecer;
- confirmar como os dados serão usados;
- salvar registros com ID anônimo;
- registrar limitações de perfil, ambiente ou simulação que afetem a interpretação.
