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
| UT01 | Identificar indicadores gerais e explorar a classificação/filtragem por nível de risco (`ALTO`, `MÉDIO`, `BAIXO`) e status na listagem. | Que a simulação ocorre na perspectiva de um analista de triagem. | O nome dos cards KPI ou onde clicar para filtrar os casos. |
| UT02 | Testar estado de busca sem resultados e recuperar a visualização completa da listagem. | Que existe simulação de pesquisa sem correspondência (`tela de erro`). | O rótulo ou posição do botão `Limpar / Restaurar Busca`. |
| UT03 | Abrir um caso sinalizado, interpretar a conversa, o alerta da IA e o artigo legal (`Art. 147-B`), e aprovar o parecer. | Que o protótipo simula casos de violência psicológica. | Onde clicar para abrir a auditoria ou validar o parecer. |
| UT04 | Testar a reclassificação humana do nível de risco e o registro de justificativa do analista. | Que o analista pode rever a classificação sugerida pela IA. | O nome ou localização do botão/modal de reclassificação. |
| UT05 | Explorar as abas de análises estatísticas e relatórios consolidados do sistema. | Que existem outras telas no menu para exploração livre. | Os nomes das abas laterais (`Análises` / `Relatórios`). |

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
