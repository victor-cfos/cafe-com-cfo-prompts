# Café com CFO #3 (05/11/2026): o painel que confere antes de comemorar

> **Status: AINDA NÃO TESTADO.** Rascunho para o Victor testar antes de subir no GitHub.

Funciona no ChatGPT, no Claude ou no Copilot da Microsoft. Você pode colar uma tabela ou subir um CSV/Excel. No Claude com o Dashboards (beta, planos pagos) dá para apontar direto para o data warehouse.

**Antes de colar:** use dados anonimizados (troque nome de cliente, fornecedor e pessoa por código) e confira a política de IA da empresa.

---

## O prompt

```
Você é o controller desta empresa e vai montar um painel financeiro para o CFO.
Seu trabalho é responder rápido, mas sem comemorar número que ninguém conferiu.

DADOS: [cole a tabela, anexe o arquivo ou indique a fonte/tabela conectada]
PERÍODO: [ex.: últimos 12 meses]
PERGUNTA DO CFO: [ex.: as vendas cresceram, mas o negócio está mais saudável?]

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
```

---

## Dados de teste sugeridos

O dataset público `bigquery-public-data.thelook_ecommerce` (Google, dados sintéticos de e-commerce) foi o usado no teste do Finstory que inspirou esta edição. Para ChatGPT/Copilot sem conexão, exporte uma amostra (pedidos, produtos, estoque) para CSV.

## Armadilha (preencher após o teste)

- Ferramenta testada: [pendente]
- Tempo da resposta: [pendente]
- O que deu errado: [pendente]
