# Café com CFO #3 (05/11/2026): o painel que confere antes de comemorar

Funciona no ChatGPT, no Claude ou no Copilot da Microsoft. Você pode colar a tabela de exemplo abaixo direto no chat ou trocar pela sua amostra (CSV/Excel). No Claude com o Dashboards (beta, planos pagos) dá para apontar direto para o data warehouse.

**Antes de colar:** use dados anonimizados (troque nome de cliente, fornecedor e pessoa por código) e confira a política de IA da empresa.

---

## O prompt (com amostra fictícia pronta para copiar e testar)

```text
Você é o controller desta empresa e vai montar um painel financeiro para o CFO.
Seu trabalho é responder rápido, mas sem comemorar número que ninguém conferiu.

DADOS: veja a amostra de pedidos, estoque e resumo abaixo (fictícia, inspirada em e-commerce).
PERÍODO: últimos 12 meses (2025-10-01 a 2026-09-30).
PERGUNTA DO CFO: as vendas cresceram 77%, mas o negócio está mais saudável?

Monte o painel em 4 blocos:

1. RESULTADO: receita, margem, volume e a variação contra o período anterior.
   Para cada número, mostre de onde ele veio (a consulta SQL, a fórmula ou as
   linhas da tabela) e a data do dado mais recente usado.

2. CAIXA E CAPITAL DE GIRO: estoque, giro, recebíveis e o que estiver parado.
   Diga quanto do resultado virou caixa e quanto ficou preso.

3. CONTROLES: rode pelo menos 8 checagens nos dados antes de concluir qualquer
   coisa (duplicidade, datas fora do período, valores negativos onde não deveria,
   totais que não fecham com a soma das partes, itens sem custo, saldo de estoque
   sem movimentação, etc.). Liste cada checagem como OK / FALHOU / NÃO DEU PRA
   CHECAR, com o número de linhas afetadas.

4. ACHADOS: no máximo 5. Classifique cada um com uma etiqueta:
   - "Impacto real": o dado está consistente e o efeito é no negócio.
   - "Conferir o dado primeiro": parece mais problema de cadastro ou registro do
     que de negócio. Diga o que verificar e com quem antes de lançar qualquer
     ajuste contábil.
   - "Sem base para concluir": falta dado.

Regras:
- Não invente número. Se não está nos dados, escreva "não informado".
- Não proponha baixa, provisão ou ajuste sem antes passar pela etiqueta
  "Conferir o dado primeiro".
- Feche com uma tabela de conferência: número | fonte | checagem que o sustenta.

Amostra de dados (fictícia):

TABELA 1 — PEDIDOS (amostra de 10 linhas do período)
linha | pedido_id | data | sku | categoria | qtd | venda_liquida_usd | cmv_usd | status_pagamento
L01 | ORD-1001 | 2025-11-10 | SKU-10 | Casacos | 2 | 240 | 110 | recebido
L02 | ORD-1002 | 2025-12-05 | SKU-20 | Jeans | 3 | 300 | 140 | recebido
L03 | ORD-1002 | 2025-12-05 | SKU-20 | Jeans | 3 | 300 | 140 | recebido
L04 | ORD-1003 | 2026-01-18 | SKU-30 | Tênis | 1 | 180 | 85 | recebido
L05 | ORD-1004 | 2026-03-22 | SKU-40 | Camisetas | 5 | 200 | | recebido
L06 | ORD-1005 | 2026-05-14 | SKU-10 | Casacos | 2 | -240 | 110 | recebido
L07 | ORD-1006 | 2026-07-09 | SKU-20 | Jeans | 4 | 400 | 185 | a_receber_vencido_95d
L08 | ORD-1007 | 2026-08-29 | SKU-30 | Tênis | 2 | 360 | 170 | recebido
L09 | ORD-1008 | 2026-09-28 | SKU-10 | Casacos | 1 | 120 | 55 | a_receber_30d
L10 | ORD-0890 | 2025-08-15 | SKU-20 | Jeans | 2 | 200 | 95 | recebido

TABELA 2 — POSIÇÃO DE ESTOQUE EM 2026-09-30 (5 linhas)
linha | sku | categoria | unidades_estoque | custo_unitario_usd | custo_total_estoque_usd | dias_sem_giro | observacao_sistema
E01 | SKU-10 | Casacos | 1.200 | 55 | 66.000 | 12 | giro normal
E02 | SKU-20 | Jeans | 1.500 | 47 | 70.500 | 8 | giro normal
E03 | SKU-30 | Tênis | 900 | 85 | 76.500 | 19 | giro normal
E04 | SKU-40 | Camisetas | 2.000 | 0 | 0 | 15 | custo unitário zerado no cadastro
E05 | SKU-99 | Inverno Legado | 172.400 | 50 | 8.620.000 | 410 | lote migrado do ERP antigo em 2025-07 sem baixa de saídas

TABELA 3 — RESUMO GERENCIAL DECLARADO NO PAINEL (últimos 12 meses vs. 12 meses anteriores)
metrica | 12m_anteriores | 12m_atuais_declarado | variacao_declarada
Vendas líquidas (USD) | 1.207.000 | 2.140.000 | +77,3%
CMV (USD) | 590.000 | 1.030.000 | +74,6%
Margem bruta (USD) | 617.000 | 1.110.000 | +79,9%
Pedidos (qtd) | 28.400 | 44.861 | +58,0%
Soma das categorias de vendas no detalhe (Casacos + Jeans + Tênis + Camisetas) | | 2.090.000 | (diferença de USD 50.000 para o total declarado de 2.140.000)
Contas a receber total em 2026-09-30 (USD) | 145.000 | 490.000 | sendo USD 210.000 vencidos há mais de 90 dias
Estoque total no balancete em 2026-09-30 (USD) | 910.000 | 8.833.000 | inclui E05 (SKU-99) de USD 8.620.000 sem giro há 410 dias
```

---

## O que um bom resultado deve apontar no exemplo (gabarito de checagem)

- **L02 e L03:** pedido `ORD-1002` duplicado.
- **L10:** pedido `ORD-0890` com data `2025-08-15`, fora da janela dos últimos 12 meses (`2025-10-01` a `2026-09-30`).
- **L06:** venda líquida negativa (`-240`) com quantidade positiva (`2`) e CMV positivo (`110`), sem indicação de devolução.
- **L05 e E04:** `SKU-40` vendido sem CMV informado em `L05` e com custo unitário zerado no cadastro de estoque (`E04`), inflando a margem.
- **Tabela 3 (soma das partes):** a soma das categorias no detalhe (`USD 2.090.000`) não fecha com o total declarado de vendas líquidas (`USD 2.140.000`, diferença de `USD 50.000`).
- **E05 (`SKU-99`, `USD 8,62 milhões` sem giro há 410 dias):** deve receber a etiqueta **"Conferir o dado primeiro"** (lote migrado do ERP antigo sem baixa de saídas), e **não** uma proposta direta de baixa contábil no DRE.
- **Recebíveis (Tabela 3 e L07):** contas a receber subiram de `USD 145.000` para `USD 490.000` (+237,9%, bem acima do crescimento de 77,3% nas vendas), com `USD 210.000` vencidos há mais de 90 dias.

## Resultado do teste (26/10/2026)

- **Ferramenta testada:** ChatGPT gratuito (sem login), no navegador, colando o prompt inteiro com as três tabelas da amostra fictícia.
- **Tempo de resposta:** ~88 segundos (cerca de 1 minuto e meio).
- **O que funcionou:** montou os 4 blocos pedidos, exibiu origem/fórmula/data de cada indicador, escreveu consultas SQL de validação, rodou 14 checagens (6 falhas, 3 aprovações e 5 sem base suficiente — pegando o pedido duplicado `ORD-1002` em `L02`/`L03`, a data fora do período em `L10`, a venda negativa em `L06`, o item sem CMV em `L05` e com custo unitário zerado em `E04`, e a diferença de `US$ 50.000` entre o total de vendas e a soma das categorias) e classificou os `US$ 8,62 milhões` do `SKU-99` (`E05`) como **"Conferir o dado primeiro"**, sem propor baixa contábil.
- **A armadilha:** contradisse a própria etiqueta nos recebíveis vencidos (`US$ 210.000` há mais de 90 dias). No bloco 4 (*Achados*), classificou o item 3 como **`[Impacto real]`**, mas logo abaixo da tabela final de conferência escreveu uma *Nota de classificação* dizendo que o achado 3 deveria ser tratado como **`Conferir o dado primeiro`** até que os títulos vencidos fossem conciliados.
