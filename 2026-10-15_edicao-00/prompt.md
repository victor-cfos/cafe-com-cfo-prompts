# Prompt da semana #0: o contrato de fornecedor na frente da reforma

- **Edição:** Café com CFO #0, enviada em 15/10/2026
- **Para que serve:** ler um contrato de fornecedor e mostrar onde ele protege, ou não, a sua empresa quando a CBS começar a ser cobrada, em 1º/01/2027.
- **Onde rodar:** ChatGPT, Claude, Copilot da Microsoft ou a ferramenta de IA aprovada pela sua empresa.
- **Testado:** no ChatGPT, versão gratuita, em 07/10/2026, com o contrato fictício do fim desta página. A resposta saiu em menos de 30 segundos e não inventou artigo de lei. A lista do que falta veio longa (17 itens), então comece pelas 3 ações prioritárias do final.

## Como funciona

1. **Mapeia as cláusulas que mexem com preço.** Monta uma tabela com cada cláusula de preço, reajuste, tributos, repasse, reequilíbrio, alteração de lei, nota fiscal, retenções, vigência, renovação e rescisão, com o trecho literal, o risco com a reforma e a pergunta para o jurídico ou o fornecedor.
2. **Aponta o que falta.** Confere se existe cláusula de alteração tributária com gatilho objetivo, método de cálculo do impacto, prazo para pedir revisão, forma de ajuste, tratamento dos créditos de CBS e IBS e o que acontece sem acordo.
3. **Prioriza.** Fecha com as três ações mais urgentes, em ordem.

## Antes de colar

Troque razão social, CNPJ, nomes, conta bancária e valores por marcadores (`[FORNECEDOR]`, `[CNPJ]`, `[VALOR]`) e use a versão da ferramenta aprovada pela empresa. Nome de signatário é dado pessoal pela LGPD, e preço é segredo do negócio. Na dúvida, não cole.

## O prompt

```text
Você é analista sênior de controladoria e tributos indiretos no Brasil.
Contexto: Reforma Tributária do Consumo (EC 132/2023 e LC 214/2025). Em 2027
a CBS substitui PIS e Cofins; de 2029 a 2033 o IBS substitui ICMS e ISS.
Abaixo está um contrato de fornecimento anonimizado. Somos a CONTRATANTE.

1. Monte uma tabela com cada cláusula sobre preço, reajuste, tributos,
   repasse, reequilíbrio, alteração de lei, nota fiscal, retenções,
   vigência, renovação ou rescisão. Colunas: nº da cláusula | trecho literal
   (até 40 palavras) | o que diz, em uma frase | risco com a reforma
   (Alto/Médio/Baixo) | por quê | pergunta para o jurídico ou o fornecedor.
2. Diga o que FALTA, checando: cláusula de alteração tributária com gatilho
   objetivo; método de cálculo do impacto (carga efetiva e créditos); prazo
   para pedir e responder revisão; forma de ajuste; tratamento dos créditos
   de CBS/IBS; o que acontece sem acordo.
3. Termine com as 3 ações prioritárias, em ordem.

Regras: use só o texto do contrato e escreva "não consta" quando faltar.
Não invente número de cláusula, alíquota ou artigo de lei. Não diga que
algo é ilegal; aponte o risco e recomende revisão jurídica. Avise se algum
trecho estiver cortado.

Contrato:
"""
[COLE AQUI O CONTRATO ANONIMIZADO]
"""
```

## Quer testar antes? Use este contrato fictício

Totalmente inventado, sem dados reais. Cole no lugar de `[COLE AQUI O CONTRATO ANONIMIZADO]`.

```text
CONTRATO DE FORNECIMENTO DE EMBALAGENS Nº [000]/2025
CONTRATANTE: [EMPRESA A], CNPJ [CNPJ A]. CONTRATADA: [FORNECEDOR], CNPJ [CNPJ B].

Cláusula 1 - Objeto. Fornecimento mensal de caixas de papelão conforme Anexo I.
Cláusula 4 - Preço. O preço unitário é de [VALOR] por caixa, já incluídos todos
os tributos incidentes, em especial ICMS, PIS e Cofins, não cabendo qualquer
acréscimo a esse título.
Cláusula 5 - Reajuste. O preço será reajustado a cada 12 meses pela variação
do IPCA, sem prejuízo da cláusula 4.
Cláusula 6 - Faturamento. A CONTRATADA emitirá nota fiscal até o 5º dia útil
do mês seguinte à entrega. Pagamento em 45 dias.
Cláusula 9 - Vigência. 36 meses a partir de 01/03/2025, renovável
automaticamente por igual período, salvo aviso com 90 dias de antecedência.
Cláusula 11 - Rescisão. Qualquer parte pode rescindir com aviso prévio de
60 dias, sem multa.
Cláusula 14 - Foro. Fica eleito o foro da comarca de [CIDADE].
```

**O que observar:** se a IA marca as cláusulas 4, 5 e 9 como risco alto, se aponta a falta de cláusula de alteração tributária e de tratamento dos créditos de CBS/IBS, e se inventa alguma cláusula ou artigo de lei que não está no texto.

Mesmo com um bom resultado, confira cada trecho literal no contrato original. O relatório não substitui revisão jurídica.

**Escala:** se você tem centenas de contratos em vez de um, a CFOs.AI tem o Analisador Inteligente de Contratos, que lê a pasta inteira.
