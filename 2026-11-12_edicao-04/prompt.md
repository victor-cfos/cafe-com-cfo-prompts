# Prompt da semana #4: o raio-x do cadastro antes da CBS

**Café com CFO #4 · 12/11/2026 · por Victor Prada (CFOs.AI)**

Para que serve: antes de a nota sair com IBS e CBS (e, lá na frente, antes de o pagamento precisar apontar para a nota certa), a IA passa um pente-fino numa amostra do seu cadastro de itens e serviços. Ela não diz qual é o NCM certo. Ela mostra onde o cadastro está vazio, torto ou duplicado, e transforma isso numa lista de perguntas para o fiscal e para o fornecedor do ERP.

Como usar:
1. Exporte do ERP uma amostra de 20 a 50 linhas do cadastro com: código interno, descrição, tipo (produto ou serviço), NCM, código de serviço (para serviços) e cClassTrib. Se o seu ERP ainda não tem o campo cClassTrib, deixe a coluna vazia: isso já é um achado.
2. Copie o prompt abaixo no ChatGPT, no Claude ou no Copilot da Microsoft e troque a tabela de exemplo pela sua amostra.
3. Leve a tabela de achados e as perguntas para 30 minutos com o fiscal e com quem cuida de dados mestres.

A amostra do exemplo é fictícia, inclusive os códigos.

```text
Você é um analista sênior de dados mestres fiscais em uma empresa brasileira. Vou colar uma amostra do cadastro de itens e serviços do nosso ERP. Faça uma triagem de qualidade do cadastro antes da emissão de notas com IBS e CBS.

Responda em 4 partes:

1. ACHADOS POR LINHA. Tabela com: código | problema encontrado | por que pode atrapalhar a emissão ou a apuração (uma frase) | risco (alto, médio ou baixo). Verifique só o que está na tabela:
   - NCM vazio, com menos ou mais de 8 dígitos, ou com cara de ter perdido o zero à esquerda;
   - cClassTrib vazio ou com quantidade de dígitos diferente de 6;
   - serviço cadastrado com NCM e sem código de serviço, ou produto com código de serviço;
   - descrição genérica demais para alguém classificar (ex.: "diversos", "material", "outros");
   - itens com descrição igual ou quase igual e códigos fiscais diferentes;
   - descrição que parece não combinar com o NCM informado (marque como "possível incompatibilidade: validar com o fiscal").

2. RESUMO. Quantas linhas foram analisadas, quantas têm pelo menos um problema e quais são os 3 problemas mais frequentes.

3. PERGUNTAS. No máximo 5 perguntas para o fiscal e 3 para o fornecedor do ERP, nascidas dos achados.

4. PRIMEIROS PASSOS. 3 ações para a próxima semana, em ordem.

Regras:
- Use só o que está na tabela. Não diga qual é o NCM, o cClassTrib ou o código de serviço correto, nem cite alíquota, artigo de lei ou multa. Quando suspeitar de erro, escreva "validar com o fiscal".
- Não invente linhas nem colunas. Se uma coluna não existir, diga que ela falta.
- Não recomende ferramenta, fornecedor nem preço.
- Não diga que o cadastro está "pronto" ou "correto". O seu papel é mostrar o que falta conferir.

Amostra do cadastro (fictícia):
código | descrição | tipo | NCM | código de serviço | cClassTrib
P001 | Café torrado em grãos 1 kg | produto | 9012100 | | 000001
P002 | Café torrado em grãos 1kg | produto | 09012100 | | 000001
P003 | Café torrado e moído 500 g | produto | 09012100 | | 000001
P004 | Material diverso | produto | 39269090 | | 000001
P005 | Cadeira de escritório giratória | produto | 09012100 | | 000001
P006 | Filtro de papel para café nº 103 | produto | 48239099 | | 
P007 | Cafeteira elétrica 1,2 L | produto | | | 000001
P008 | Xícara de porcelana 90 ml | produto | 69111010 | | 00001
P009 | Serviço de instalação de máquina de café | serviço | 84198100 | | 000001
P010 | Serviço de manutenção preventiva mensal | serviço | | 14.01 | 000001
P011 | Açúcar refinado sachê 5 g | produto | 17019900 | | 000001
P012 | Outros | produto | | | 
```

**O que um bom resultado deve apontar no exemplo** (para você saber se a IA leu direito):
- P001 com NCM de 7 dígitos (o Excel comeu o zero à esquerda);
- P001 e P002 com a mesma descrição e NCM diferente;
- P004 e P012 com descrição genérica, e P012 sem nenhum código;
- P005, uma cadeira com o mesmo NCM do café (possível incompatibilidade);
- P006 e P012 sem cClassTrib, e P008 com cClassTrib de 5 dígitos;
- P007 sem NCM;
- P009, serviço com NCM e sem código de serviço.

**Resultado do teste (ChatGPT gratuito, sem login, 10 a 20 s):** achou todos os erros plantados por linha sem inventar NCM nem alíquota. A armadilha apareceu na parte 2 (resumo numérico), onde ele se enrolou para contar: disse 8 linhas de risco alto quando a própria tabela tinha 9, e listou 3 códigos na categoria de cClassTrib dizendo que eram 2. Use a tabela linha a linha e as perguntas para o fiscal, e faça a contagem no Excel.

**Cuidados:** a triagem é ponto de partida para a conversa com o fiscal, não parecer. Se a IA disser qual é o NCM "correto", citar alíquota ou declarar o cadastro "pronto", desconfie e confira. Antes de colar, troque nome de cliente, fornecedor e preço por marcador; cadastro de item costuma não ter dado pessoal, mas preço é segredo do negócio.
