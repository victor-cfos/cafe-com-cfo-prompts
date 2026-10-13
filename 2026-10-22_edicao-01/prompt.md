# Prompt da semana #1: o que você faz duas vezes

**Café com CFO #1 · 22/10/2026 · por Victor Prada (CFOs.AI)**

Para que serve: você cola a lista de tarefas do seu fechamento mensal e a IA classifica cada uma em três baldes (faço uma vez, duas vezes ou sempre). A partir daí, indica se a tarefa vira workflow automatizado, candidata a agente de IA ou continua com pessoa, e aponta onde um erro da IA seria difícil de perceber. No final, entrega um workflow de 5 passos para a primeira tarefa, com o ponto exato onde alguém valida e assina.

Como usar:
1. Copie o prompt abaixo no ChatGPT, no Claude ou no Copilot da Microsoft.
2. Substitua a lista de tarefas de exemplo pela sua (anonimize: troque nome de sistema, fornecedor e colaborador por marcadores como `[SISTEMA ERP]` ou `[RESPONSÁVEL]`).
3. Leia o risco de cada tarefa antes de decidir se automatiza. Confira o workflow com quem executa a tarefa hoje.

Os dados do exemplo são fictícios.

```text
Você é especialista em automação de processos financeiros e IA aplicada à controladoria.
Contexto: a empresa quer mapear quais tarefas do fechamento mensal podem virar automação e quais precisam de pessoa. O critério inicial é a frequência: tarefa feita uma vez por mês pode virar workflow simples; feita duas vezes (ou verificada duas vezes) pode virar agente de IA que executa e confere; tarefa feita sempre (juízo a cada linha) continua com pessoa.

Abaixo está a lista de tarefas do fechamento mensal, anonimizada.

1. Classifique cada tarefa em uma tabela com as colunas:
   nº | tarefa | frequência (1x, 2x ou sempre) | destino (workflow, agente ou pessoa) | justificativa em 1 frase.

2. Para cada tarefa, adicione uma coluna "risco de erro invisível" (Alto/Médio/Baixo) e outra "facilidade de conferência" (Fácil/Média/Difícil). Explique em 1 frase onde um erro da IA passaria despercebido e onde seria fácil de conferir.

3. Escolha a tarefa nº 1 da lista e entregue um workflow em exatamente 5 passos. Cada passo tem: ação, quem executa (sistema, agente ou pessoa), entrada, saída e critério de aceite. Indique em qual passo alguém valida e assina antes de seguir.

Regras:
a. Use só o texto da lista abaixo. Se faltar contexto para classificar, escreva "não consta" e diga o que precisaria saber.
b. Não invente nome de ferramenta, preço, prazo de implantação nem fornecedor. Se a tarefa mencionar sistema, use o marcador que eu mandei.
c. Não prometa que o fechamento vai rodar sozinho. Sempre indique o ponto de validação humana.
d. Se uma tarefa tiver mais de uma interpretação, liste as duas e peça para eu confirmar.

Lista de tarefas do fechamento (anonimizada):
"""
[COLE AQUI A SUA LISTA DE TAREFAS DO FECHAMENTO]
"""
```

## Quer testar antes? Use esta lista fictícia

Totalmente inventada, sem dados reais. Cole no lugar de `[COLE AQUI A SUA LISTA DE TAREFAS DO FECHAMENTO]`.

```text
1. Importar extrato bancário do [BANCO A] e do [BANCO B] no [SISTEMA ERP].
2. Conciliar as entradas do extrato com os títulos a receber.
3. Revisar as provisões de despesas (folha, aluguel, serviços).
4. Lançar as notas fiscais de serviço recebidas no mês.
5. Conferir se o saldo de estoque do [SISTEMA ERP] bate com a contagem física.
6. Calcular e lançar a depreciação dos ativos imobilizados.
7. Revisar os lançamentos contábeis feitos pelo estagiário.
8. Gerar o balancete e enviar para o [RESPONSÁVEL] aprovar.
```

**O que observar:** se a IA marca as tarefas 2, 5 e 7 como "sempre" ou "difícil de conferir", se ela não inventa nome de sistema ou prazo, e se o workflow da tarefa 1 tem um passo claro de validação humana antes de fechar.

**Cuidado:** automação sem ponto de conferência vira problema. Antes de implementar qualquer workflow, valide o desenho com quem executa a tarefa hoje e com o responsável pelo fechamento.
