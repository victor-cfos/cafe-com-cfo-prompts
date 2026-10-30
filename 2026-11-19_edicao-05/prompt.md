# Prompt da semana #5: o advogado do diabo do business case de IA

**Café com CFO #5 · 19/11/2026 · por Victor Prada (CFOs.AI)**

Para que serve: antes de o projeto de IA entrar no orçamento de 2027, a IA faz o papel do controller chato do comitê. Ela refaz as contas do business case, aponta premissa que não para de pé, lista os custos que ficaram de fora e propõe um "botão de desligar": os critérios que dizem quando revisar ou parar o projeto. No fim, dá um veredito: aprovar, aprovar com condições ou devolver.

Como usar:
1. Junte o business case do projeto num texto simples: custos, benefícios, ROI, payback, cronograma e premissas (incluindo o resultado do piloto, se houve).
2. Copie o prompt abaixo no ChatGPT, no Claude ou no Copilot da Microsoft e troque o business case de exemplo pelo seu.
3. Confira na planilha toda conta que a IA refez. A IA mostra a conta para você conferir, não para você acreditar.
4. Leve as perguntas da parte 5 para o dono do projeto antes do comitê.

O business case do exemplo é fictício, inclusive a empresa e os números.

```text
Você é um controller sênior que revisa pedidos de investimento antes do comitê de orçamento de uma empresa brasileira. Vou colar o business case de um projeto de IA. Seu papel é o de advogado do diabo: achar o que não fecha antes que o comitê ache.

Responda em 5 partes:

1. CONTAS. Tabela com: item | valor declarado | conta refeita (mostre a conta) | bate? (sim/não). Refaça só as contas que dá para refazer com os números do documento: benefícios, totais, ROI e payback.

2. PREMISSAS FRÁGEIS. Tabela com: premissa | o que no próprio documento contradiz ou não sustenta | risco (alto, médio, baixo). Procure, entre outras coisas: benefício contado duas vezes, hora liberada tratada como caixa, benefício sem linha de base, premissa diferente do piloto, prazo de implantação ignorado e volume que muda o custo.

3. CUSTOS QUE FALTAM. Liste os custos que um projeto assim costuma ter e que não aparecem no documento. Não estime valor: escreva "a levantar".

4. BOTÃO DE DESLIGAR. Proponha 3 critérios de parada ou revisão, cada um com: métrica | limite | data de checagem | quem decide. Use números do próprio documento quando der. Se precisar de um limite que o documento não dá, escreva "a definir com o dono do projeto".

5. VEREDITO. Escolha uma: aprovar, aprovar com condições ou devolver para refazer. Explique em até 3 linhas e liste no máximo 5 perguntas para o dono do projeto.

Regras:
- Use só o que está no documento. Não cite benchmark de mercado, pesquisa, fornecedor ou preço de ferramenta.
- Mostre toda conta que fizer. Se não der para calcular, diga o que falta.
- Não invente linhas, valores nem premissas.
- Seja direto. Nada de elogio ao projeto antes dos problemas.

Business case (fictício):

Projeto: Agente de IA no contas a pagar (triagem de notas e pré-lançamento no ERP)
Empresa: Torrefação Exemplo Ltda. Dono do projeto: gerente de contas a pagar.
Cronograma: aprovação em jan/2027; implantação de 4 meses; go-live em maio/2027.

CUSTOS (ano 1)
C1. Implantação (consultoria): R$ 180.000, pagamento único
C2. Licença da plataforma: US$ 1.600/mês x câmbio de orçamento R$ 5,00 = R$ 8.000/mês = R$ 96.000/ano
Total de custos no ano 1: R$ 276.000

BENEFÍCIOS (ano 1)
B1. Horas liberadas: 4 analistas x 160 h/mês x 60% de automação = 384 h/mês x R$ 85/h = R$ 32.640/mês = R$ 431.680/ano
B2. Eliminação de 2 vagas de analista: R$ 288.000/ano
B3. Fim de multas e juros por pagamento atrasado: R$ 60.000/ano
Total de benefícios no ano 1: R$ 779.680

RESULTADO
ROI no ano 1: 290%
Payback: 3 meses

PREMISSAS
P1. Taxa de automação de 60% desde o primeiro mês. (Piloto de set/2026: 35% das notas passaram sem ajuste, numa amostra de 200 notas.)
P2. Custo-hora do analista: R$ 85, com encargos.
P3. Volume de notas cresce 20% em 2027. Volume atual: 2.900 notas/mês. A licença inclui até 3.000 notas/mês; acima disso, cobra por nota.
P4. Ninguém será desligado. O time será realocado para análise.
P5. Revisão humana: não necessária depois do go-live.
P6. Contingência: 0%.
P7. Critério de parada: não se aplica, projeto estratégico.
P8. Dono da métrica de resultado: a definir.
P9. Histórico de multas e juros por atraso: não levantado.
```

**O que um bom resultado deve apontar no exemplo** (para você saber se a IA leu direito):
- B1 com conta errada: R$ 32.640 x 12 dá R$ 391.680, não R$ 431.680;
- o ROI de 290% não fecha nem com os números do próprio documento (dá 182,5%; com B1 corrigido, 168%);
- B2 conta de novo as horas que já estão em B1, e ainda contradiz P4 (ninguém será desligado);
- hora liberada com o time realocado é capacidade, não caixa;
- B3 sem linha de base (P9: histórico de multas não levantado);
- P1 promete 60% de automação desde o mês 1, mas o piloto deu 35%;
- payback de 3 meses ignora os 4 meses de implantação;
- com 20% a mais de volume, as notas passam de 3.000/mês e a licença fica mais cara (custo fora do business case);
- câmbio fixo, sem sensibilidade;
- sem revisão humana, sem contingência, sem critério de parada e sem dono da métrica.

Se a IA aprovar o projeto sem condições, ou corrigir B1 e recalcular o ROI mantendo B2, ela não leu direito.

**Cuidados:** o veredito é ponto de partida para a conversa com o dono do projeto, não decisão de comitê. Confira as contas na planilha. Antes de colar, troque nome de fornecedor, de pessoas e valores sensíveis por marcadores; salário por pessoa é dado pessoal, e preço negociado com fornecedor costuma ser segredo do negócio.
