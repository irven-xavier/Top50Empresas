# Análise de Lucro e DFCs de empresas listadas na NYSE e NASDAQ

Este projeto realiza uma análise financeira de empresas listadas nas bolsas **NYSE** e **NASDAQ**, com foco no lucro líquido e nos fluxos de caixa reportados entre os anos de 2019 e 2024.

## Objetivos

1. Analisar o comportamento das 50 empresas mais lucrativas a cada ano no período observado.
2. Avaliar os lucros segmentando as empresas por setor.
3. Investigar os componentes da Demonstração de Fluxo de Caixa (DFC): atividades operacionais, de investimento, de financiamento e fluxo líquido.
4. Verificar se os lucros se converteram em Fluxo de Caixa Operacional.
5. Avaliar o comprometimento das empresas com capital de terceiros e o pagamento de dividendos.
6. Identificar empresas financeiramente estáveis.
7. Integrar dados externos via API (Marketstack), como: nome completo da empresa, setor, bolsa em que atua, preço de abertura e fechamento dos ativos.

## Análise Exploratória dos Dados

A EDA buscou entender como os dados estavam inseridos no Dataset. Foi verificado o tipo dos dados, elementos duplicados, a quantidade de linhas e colunas bem como a contagem única de empresas, entre outros componentes.

Ainda nesta parte, pequenas transformações ocorreram a fim de mudar o tipo de uma coluna e a adição de 3 novas colunas ao Dataset.

## Análise Diagnóstica

Ao selecionar as 50 empresas mais lucrativas das bolsas **NYSE** e **NASDAQ**, foi feita a investigação do Fluxo de Caixa dessas empresas, com o objetivo de entender como empresas que lucram perforam nas movimentações de operação, investimento e financiamento. 

Observou-se que nem sempre essas empresas apresentavam Fluxos de Caixa saudáveis, onde critérios como conversão de lucro em caixa operacional e necessidade de capital de terceiros foram determinantes para identificar empresas com boa situação financeira.

Após esta identificação, foi feita uma conexão à API da Marketstack para trazer mais informações sobre as empresas como por exemplo o nome completo, segmento do setor e os preços de abertura e fechamento entre os dias de 01/07/2024 e 05/07/2024 a fim de entender o comportamento desses preços. Para tal, foi utilizado um gráfico de linha para cada empresa para uma melhor visualização destas variações dia a dia.

A análise completa, códigos de conexão da API e gráficos estão no [Jupyter Notebook](https://github.com/irven-xavier/Top50Empresas/blob/main/Analise_Lucro_DFC_NYSE_NASDAQ.ipynb)

## Considerações e Limitações:

1. A data de publicação não faz referência a qual período está sendo considerado nas demonstrações financeiras, portanto assume-se que o ano/mês da data é o próprio ano (exercício) fiscal.

2. A análise das demonstrações é limitada pela falta dos balanços patrimoniais das empresas. Desta forma, fica inviável analisar índices cruciais como liquidez, endividamento e giro de estoque por exemplo.

3. O Lucro Líquido (Net Income) é apenas um pequeno extrato da DRE (P&L Report), portanto métricas como EBITDA e EBIT e contas como Receita Bruta, Impostos, CMV/CSP e Despesas Operacionais de um determindado exercício não foram considerados pela falta dos mesmos.

4. A análise de Fluxo de Caixa Investimento foi desconsiderada do produto final da análise, pois entende-se que tais movimentações compõe mudanças no Ativo da empresa, o qual não pode ser analisado pela falta do mesmo. O Dataset original não fornece detalhamento das aquisições e receitas financeiras, por exemplo.

5. A API da Marketstack tem um limite de 100 requests por mês no plano "Free". Portanto, não foi possível extrair dados históricos robustos sobre o comportamento dos preços de abertura e fechamento das empresas selecionadas entre os períodos analisados.

6. A análise, como um todo, desconsidera completamente fatores macroecônomicos e tendências de mercado.