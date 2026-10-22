# Prompt da semana #2: o comentário de variação que se confere em 5 minutos

**Café com CFO #2 · 29/10/2026 · por Victor Prada (CFOs.AI)**

Para que serve: a IA escreve o comentário de orçado x realizado para o CFO, mas cada número aponta para a linha da DRE e cada causa aponta para a nota da área. Assim você confere a tabela, não o texto inteiro.

Como usar:
1. Copie o prompt abaixo no ChatGPT, no Claude ou no Copilot da Microsoft.
2. Troque a DRE e as notas de exemplo pelas suas (anonimize: nada de nome de cliente, fornecedor ou CNPJ).
3. Confira a tabela de conferência e a lista do que a IA não conseguiu checar antes de mandar para o CFO.

Os números do exemplo são fictícios.

```text
Você é analista sênior de FP&A numa empresa brasileira. Abaixo estão a DRE gerencial do mês (orçado x realizado, em R$ mil) e as notas que as áreas mandaram. Escreva o comentário de variação para o CFO de um jeito que eu consiga conferir em 5 minutos.

1. Recalcule você mesmo a variação de cada linha (Var R$ = realizado − orçado; Var % = Var R$ ÷ |orçado|). Se a coluna "Var R$" que eu mandei estiver diferente do seu cálculo, aponte a linha e os dois valores.
2. Considerando só as linhas de receita, custo e despesa (sem subtotais), escolha as 3 maiores variações em valor absoluto. Para cada uma, escreva no máximo 3 frases.
3. Toda frase com número termina com [linha X]. Toda frase com causa termina com [nota N]. Se nenhuma nota explica a variação, escreva "causa não informada: perguntar para a área responsável". Não deduza causa. Se a nota explica só parte da variação, diga quanto fica sem explicação.
4. Feche com uma frase sobre o EBITDA [linha X].
5. Depois, uma tabela de conferência com as colunas: linha | orçado | realizado | Var R$ (seu cálculo) | Var % | fonte da causa | o que o revisor precisa checar.
6. Por último, liste o que você NÃO conseguiu conferir com os dados recebidos.

Regras: use só os números e as notas abaixo. Não invente meta, histórico, benchmark, preço de mercado nem causa. Se faltar dado, escreva "não consta".

DRE gerencial, setembro (R$ mil):
"""
Linha | Conta | Orçado | Realizado | Var R$
1 | Receita bruta | 12.400 | 11.650 | -750
2 | Deduções (tributos sobre vendas) | -1.860 | -1.748 | 112
3 | Receita líquida | 10.540 | 9.902 | -638
4 | CMV | -6.320 | -6.050 | 270
5 | Lucro bruto | 4.220 | 3.852 | -368
6 | Despesas com pessoal | -1.650 | -1.810 | -160
7 | Marketing | -420 | -610 | -190
8 | Fretes | -380 | -455 | -75
9 | Tecnologia e software | -210 | -228 | -18
10 | Outras despesas administrativas | -300 | -262 | 48
11 | EBITDA | 1.260 | 487 | -773
"""

Notas das áreas:
"""
Nota 1 (Comercial): dois contratos de um cliente grande foram adiados para novembro, cerca de R$ 600 mil de receita bruta.
Nota 2 (RH): o dissídio foi aplicado em setembro; o orçamento previa novembro.
Nota 3 (Marketing): o evento de lançamento foi antecipado de dezembro para setembro.
"""
```

**Cuidados:** a conta oficial continua na planilha. Use o recálculo da IA só para achar diferença, nunca como número final. Se a IA escrever uma causa sem [nota N] do lado, apague a frase.
