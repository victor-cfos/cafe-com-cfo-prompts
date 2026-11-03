# Prompt da semana #6: a alçada do agente em uma página

**Café com CFO #6 · 26/11/2026 · por Victor Prada (CFOs.AI)**

Para que serve: antes de colocar um agente de IA no processo, escrever o que ele pode fazer sozinho, o que ele só prepara para alguém aprovar e o que ele não toca. A IA lê a proposta do time e a tabela de alçadas que a empresa já usa para as pessoas, aponta onde o agente ganharia mais poder do que um analista, separa o que é conta (fórmula e ERP) do que é trabalho de IA e monta a ficha do agente em uma página, com dono, teto, gatilho de escalonamento e o que precisa ficar registrado. No fim, sugere a primeira tarefa para pilotar.

Como usar:
1. Liste as tarefas que o agente faria no processo (contas a pagar, fechamento, cobrança) e o nível que o time propõe para cada uma.
2. Cole junto a tabela de alçadas vigente das pessoas e, se tiver, a distribuição de volume por faixa de valor.
3. Copie o prompt abaixo no ChatGPT, no Claude ou no Copilot da Microsoft e troque o documento de exemplo pelo seu.
4. Leve a ficha da parte 5 para o controller e para quem cuida dos controles internos. Dono e teto quem decide são pessoas, não a IA.

O documento do exemplo é fictício, inclusive a empresa e os números.

```text
Você é um controller sênior de uma empresa brasileira. O time de contas a pagar quer colocar um agente de IA para trabalhar no processo e mandou a proposta abaixo. Seu trabalho é escrever a alçada do agente: o que ele pode fazer sozinho, o que só prepara para alguém aprovar e o que ele não toca. Use a régua de 5 níveis: observar, recomendar, preparar, aprovar, executar.

Para decidir o nível de cada tarefa, pese 4 critérios: valor envolvido (materialidade), se dá para desfazer (reversibilidade), se a tarefa segue regra clara e rotineira, e se alguém de fora da empresa vê o resultado (fornecedor, banco, fisco).

Responda em 6 partes:

1. ALÇADA POR TAREFA. Tabela com: tarefa | nível proposto pelo time | nível que você recomenda | teto em R$ (só se fizer sentido) | dá para desfazer? | o que obriga o agente a parar e chamar uma pessoa | o que precisa ficar registrado.

2. CONFLITOS COM A ALÇADA HUMANA. Liste cada ponto em que a proposta dá ao agente mais poder do que a tabela de alçadas vigente dá às pessoas, ou pula um controle que já existe.

3. CONTA OU IA? Diga quais tarefas têm um resultado que precisa sair de fórmula, regra do ERP ou planilha (sempre o mesmo resultado para o mesmo dado), e qual o papel da IA nelas.

4. COBERTURA. Com o teto que você recomendar para a tarefa T3, quantos títulos de outubro e que percentual do total ficariam na faixa do agente? Mostre a conta.

5. FICHA DO AGENTE (uma página). Campos: identificador | dono do negócio | dono do controle | transações que pode tocar | nível em cada uma | teto em R$ | reversibilidade | o que força escalonamento | evidência que deixa. Use [A DEFINIR] em tudo que o documento não informa.

6. PRIMEIRO PILOTO. Escolha UMA tarefa para começar: baixo risco, dá para desfazer e o erro aparece rápido. Justifique em até 3 linhas.

Regras:
- Use só o que está no documento. Não invente cargo, sistema, valor ou prazo. Não cite lei, norma, pesquisa nem benchmark.
- O agente nunca pode ter teto maior do que a alçada de quem delega a tarefa para ele.
- Pagamento que sai da empresa e dado bancário de fornecedor nunca ficam no nível "executar".
- Histórico de conversa não é evidência suficiente: diga o que falta registrar.
- Mostre toda conta que fizer. Seja direto, sem elogiar a proposta.

Documento (fictício):

Empresa: Distribuidora Exemplo Ltda. Processo: contas a pagar.
Dono do negócio (proposto): coordenadora de contas a pagar.
Dono do controle: a definir.
Evidência proposta: "o histórico da conversa do agente fica salvo".

TABELA DE ALÇADAS VIGENTE (pessoas)
- Analista de contas a pagar: aprova títulos de até R$ 5.000, com pedido de compra e recebimento conferidos.
- Coordenadora de contas a pagar: até R$ 50.000.
- Gerente financeiro: até R$ 250.000.
- Diretor financeiro: acima de R$ 250.000.
- Cadastro e alteração de dados bancários de fornecedor: só a área de cadastro, com confirmação por telefone no número que já está no cadastro.
- Liberação do lote de pagamento no banco: sempre dois aprovadores (gerente financeiro e diretor financeiro).

TÍTULOS PAGOS EM OUTUBRO/2026, POR FAIXA DE VALOR
- Até R$ 1.000: 412
- De R$ 1.000,01 a R$ 5.000: 236
- De R$ 5.000,01 a R$ 50.000: 97
- De R$ 50.000,01 a R$ 250.000: 18
- Acima de R$ 250.000: 4
- Total: 767

PROPOSTA DO TIME
T1. Ler notas e boletos que chegam por e-mail e extrair fornecedor, CNPJ, valor e vencimento. Proposta: executar.
T2. Conferir nota x pedido de compra x recebimento e marcar divergências. Proposta: executar.
T3. Aprovar títulos com as três vias conferidas e sem divergência. Proposta: executar, até R$ 80.000.
T4. Calcular multa e juros de títulos pagos com atraso e lançar no ERP. Proposta: a IA calcula e lança.
T5. Alterar os dados bancários do fornecedor quando ele pedir por e-mail. Proposta: executar, para ganhar agilidade.
T6. Montar o lote de pagamentos do dia. Proposta: preparar.
T7. Liberar o lote no banco quando o total for menor que R$ 100.000. Proposta: executar.
T8. Responder e-mails de fornecedores sobre status de pagamento. Proposta: executar.
T9. Escrever o comentário mensal de variação das despesas para a controladoria. Proposta: preparar.
```

**O que um bom resultado deve apontar no exemplo** (para você saber se a IA leu direito):
- T3: teto de R$ 80.000 é maior que a alçada da coordenadora (R$ 50.000), que é a dona do negócio. O agente não pode ter mais alçada do que quem delega; o prudente é ficar na alçada do analista (R$ 5.000) ou só preparar;
- T5: trocar dado bancário a pedido por e-mail pula a área de cadastro e a confirmação por telefone. No máximo, o agente observa e encaminha;
- T7: liberar o lote sozinho pula os dois aprovadores, não dá para desfazer e o banco vê. No máximo, preparar;
- T4: multa e juros saem de fórmula ou regra do ERP, não da IA. A IA explica e aponta exceção;
- T8: e-mail para fornecedor sai da empresa. Executar sem revisão é ponto fraco;
- dono do controle "a definir" vira [A DEFINIR], e precisa ser outra pessoa que não a dona do negócio;
- histórico de conversa não é evidência: falta registrar dado de entrada, regra aplicada, resultado, quem aprovou e quando;
- cobertura com teto de R$ 5.000: 412 + 236 = 648 títulos, 84,5% dos 767 de outubro. Com R$ 80.000 a conta exata não sai das faixas do documento (R$ 80 mil cai no meio de uma faixa);
- primeiro piloto: T1 ou T2, tarefas internas e reversíveis.

Se a IA aceitar o teto de R$ 80.000, deixar o agente liberar o lote ou trocar dado bancário, ela não leu direito.

**Testado em 02/11/2026** no ChatGPT gratuito, sem login (cerca de 40 segundos): achou o teto acima da alçada da coordenadora, o dado bancário, o lote sem os dois aprovadores, a multa "calculada pela IA" e o histórico de conversa como evidência fraca, e acertou a cobertura (648 títulos, 84,49%). Armadilha: deixou o agente responder fornecedor sozinho (executar), mesmo admitindo que o e-mail sai da empresa.

**Cuidados:** a ficha é ponto de partida para a conversa com o controller e com quem cuida dos controles internos, não substitui a política de alçadas da empresa. Antes de colar, troque nome de fornecedor, de pessoas e valores sensíveis por marcadores.
