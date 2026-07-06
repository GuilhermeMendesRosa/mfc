# Universidade do Estado de Santa Catarina — UDESC
## Centro de Ciências Tecnológicas — CCT
## Curso de Engenharia de Produção e Sistemas — EPS

---

**Aluno(a):** Ana Paula Schultze  
**Matrícula:** _______________  
**Disciplina:** MFC — Mercado Financeiro e de Capitais  
**Período letivo:** 2026 S1  
**Data:** 29/06/2026  
**Avaliação:** Prova 01  
**Professor:** Pedro Vitor de Barba  

---

# Relatório — Prova 01: Teoria de Markowitz e Otimização de Carteiras

## 1. Introdução

Este relatório apresenta a aplicação da Teoria de Markowitz (Teoria Moderna de Carteiras) à carteira de ações definida na Atividade 01 da disciplina. O objetivo é determinar a carteira de mínima variância, comparar seus resultados com os obtidos na atividade original, analisar a variabilidade dos pesos ao longo do tempo e propor uma metodologia para definir o intervalo ideal de rebalanceamento, tudo com base em dados reais obtidos via Yahoo Finance.

### 1.1 Ativos analisados

A carteira da Atividade 01 é composta por cinco ativos do mercado brasileiro, com os seguintes pesos originais:

| Ativo | Ticker | Peso original |
|-------|--------|:-------------:|
| Petrobras PN | PETR4 | 35% |
| Embraer ON | EMBJ3 | 20% |
| WEG ON | WEGE3 | 15% |
| Ambev ON | ABEV3 | 20% |
| BTG Pactual Units | BPAC11 | 10% |

O retorno médio ponderado obtido na Atividade 01 (período de 03/03/2026 a 23/03/2026) foi de **-0,4004%**. A taxa do ativo livre de risco adotada é de **2,90% ao ano**, conforme definido em aula.

### 1.2 Metodologia geral

Os preços de fechamento ajustados foram obtidos da base Yahoo Finance por meio da biblioteca `yfinance` em Python. Os retornos diários foram calculados como a variação percentual dos preços, e os retornos anualizados foram estimados multiplicando-se a média dos retornos diários por 252 (dias úteis no ano). A matriz de covariância anualizada foi obtida multiplicando-se a covariância dos retornos diários por 252. Para o cálculo da carteira de mínima variância, utilizou-se a fórmula fechada de Markowitz, e para a carteira ótima (máximo índice de Sharpe), utilizou-se otimização numérica via SLSQP com restrição de vendas a descoberto proibidas (pesos entre 0 e 1, soma igual a 1).

---

## 2. Questão 1 — Carteira de mínima variância no período da Atividade 01

### 2.1 Item (a): Cálculo da carteira de mínima variância

Utilizando o mesmo período da Atividade 01 (03/03/2026 a 23/03/2026), os retornos anualizados e a matriz de covariância foram estimados a partir dos retornos diários dos cinco ativos. A seguir, aplicou-se a fórmula de Markowitz para determinar os pesos da carteira de mínima variância.

**[INSERIR AQUI O GRÁFICO DE EVOLUÇÃO DOS PREÇOS — QUESTÃO 1]**

*Figura 1: Evolução dos preços ajustados dos cinco ativos no período da Atividade 01.*

A tabela abaixo resume o retorno anualizado e o risco (desvio padrão anualizado) de cada ativo individual no período:

**[INSERIR AQUI A TABELA DE RETORNO E RISCO POR ATIVO — QUESTÃO 1]**

*Tabela 1: Retorno e risco anualizados por ativo (período da Atividade 01).*

Aplicando a fórmula de mínima variância, obtiveram-se os seguintes pesos:

| Ativo | Peso na carteira de mínima variância |
|-------|:------------------------------------:|
| PETR4 | **[COLAR RESULTADO DO NOTEBOOK]** |
| EMBJ3 | **[COLAR RESULTADO DO NOTEBOOK]** |
| WEGE3 | **[COLAR RESULTADO DO NOTEBOOK]** |
| ABEV3 | **[COLAR RESULTADO DO NOTEBOOK]** |
| BPAC11 | **[COLAR RESULTADO DO NOTEBOOK]** |

*Tabela 2: Composição da carteira de mínima variância.*

**[INSERIR AQUI O GRÁFICO DA FRONTEIRA EFICIENTE — QUESTÃO 1]**

*Figura 2: Fronteira eficiente com destaque para a carteira de mínima variância (estrela vermelha) e carteira ótima (estrela verde).*

### 2.2 Item (b): Comparação com o retorno da Atividade 01

O retorno simples no período foi calculado com base nos preços inicial e final de cada ativo, replicando a metodologia da Atividade 01. Os resultados comparativos são:

| Carteira | Retorno simples no período |
|----------|:--------------------------:|
| Atividade 01 (original) | -0,4004% |
| Carteira de mínima variância | **[COLAR RESULTADO DO NOTEBOOK]** |

*Tabela 3: Comparação de retornos — carteira original vs. carteira de mínima variância.*

**[COMENTÁRIO AUTOMÁTICO DO NOTEBOOK SERÁ INSERIDO AQUI]**

**Comentário:** A carteira de mínima variância apresentou retorno **[maior/menor]** que a carteira original da Atividade 01 nesse intervalo. É importante destacar que a carteira de mínima variância é projetada para minimizar risco, e não necessariamente para maximizar retorno. A avaliação deve considerar o par risco-retorno, e não apenas o retorno de forma isolada. O desvio padrão anualizado da carteira de mínima variância foi de **[COLAR RISCO]**, inferior aos riscos individuais dos ativos que a compõem, demonstrando o benefício da diversificação preconizado por Markowitz.

---

## 3. Questão 2 — Análise dos últimos 36 meses

### 3.1 Item (a): Carteira de mínima variância do período completo e mês a mês

Para os últimos 36 meses (29/06/2023 a 29/06/2026), foram realizados dois cálculos distintos:

**Período completo:** a carteira de mínima variância foi calculada utilizando todos os retornos diários dos 36 meses, resultando nos seguintes pesos:

| Ativo | Peso (período completo) |
|-------|:-----------------------:|
| PETR4 | **[COLAR RESULTADO]** |
| EMBJ3 | **[COLAR RESULTADO]** |
| WEGE3 | **[COLAR RESULTADO]** |
| ABEV3 | **[COLAR RESULTADO]** |
| BPAC11 | **[COLAR RESULTADO]** |

*Tabela 4: Carteira de mínima variância — período completo de 36 meses.*

**Mês a mês:** a carteira de mínima variância foi recalculada para cada mês individualmente, utilizando apenas os retornos diários daquele mês específico. A tabela completa com os 36 meses está disponível no notebook; abaixo apresenta-se um extrato ilustrativo:

**[INSERIR AQUI A TABELA DE PESOS MENSAIS — QUESTÃO 2]**

*Tabela 5: Pesos da carteira de mínima variância mês a mês.*

A variação observada nos pesos mensais reflete a instabilidade das estimativas de retorno e covariância quando calculadas com janelas muito curtas (aproximadamente 21 dias úteis por mês). Isso evidencia a importância de utilizar janelas de estimação mais longas para decisões de alocação.

### 3.2 Item (b): Média e desvio padrão dos pesos mensais

A partir dos pesos mensais calculados no item anterior, foram computadas a média e o desvio padrão de cada ativo ao longo dos 36 meses:

**[INSERIR AQUI A TABELA DE MÉDIA E DESVIO PADRÃO — QUESTÃO 2]**

*Tabela 6: Média e desvio padrão dos pesos mensais por ativo.*

O desvio padrão elevado em alguns ativos indica que os pesos da carteira de mínima variância são sensíveis às flutuações de curto prazo nos retornos e na covariância. Ativos com maior desvio padrão nos pesos tendem a apresentar maior instabilidade nas estimativas de risco e correlação.

### 3.3 Item (c): Histogramas dos pesos mensais

Para visualizar a distribuição dos pesos de cada ativo ao longo dos meses, foram construídos histogramas (peso W vs. frequência):

**[INSERIR AQUI OS 5 HISTOGRAMAS — QUESTÃO 2]**

*Figura 3: Histogramas dos pesos mensais de cada ativo.*

Os histogramas permitem observar a concentração dos pesos em determinadas faixas. Por exemplo, ativos cujos pesos se concentram próximos a zero em vários meses indicam que, sob a ótica de mínima variância, a alocação nesses ativos não contribui significativamente para a redução do risco da carteira naquele mês específico.

---

## 4. Questão 3 — Intervalo ideal de rebalanceamento

### 4.1 Metodologia proposta

Para determinar o intervalo de tempo ideal para o rebalanceamento da carteira de mínima variância, propõe-se a seguinte metodologia:

1. **Base de dados:** utilizar os preços diários reais dos últimos 36 meses para os cinco ativos da carteira.

2. **Janela de estimação:** para cada decisão de rebalanceamento, estimar os retornos esperados e a matriz de covariância utilizando uma janela móvel de 12 meses anteriores à data de rebalanceamento.

3. **Frequências testadas:** simular o rebalanceamento em cinco frequências distintas:
   - Mensal (a cada 1 mês)
   - Bimestral (a cada 2 meses)
   - Trimestral (a cada 3 meses)
   - Semestral (a cada 6 meses)
   - Anual (a cada 12 meses)

4. **Métricas de avaliação:** para cada frequência, calcular fora da amostra:
   - Retorno anualizado
   - Volatilidade anualizada (desvio padrão)
   - Índice de Sharpe
   - Turnover médio (soma das mudanças absolutas nos pesos entre rebalanceamentos consecutivos)
   - Drawdown máximo

5. **Critério de escolha:** como o objetivo da estratégia é a **minimização de risco**, o critério principal é a **menor volatilidade anualizada** realizada fora da amostra. Em caso de resultados muito próximos, o desempate privilegia o **menor turnover médio** (menor custo operacional e menor necessidade de ajustes) e, em seguida, o **maior índice de Sharpe** (melhor relação retorno-risco).

### 4.2 Resultados das simulações

A tabela a seguir resume o desempenho de cada frequência de rebalanceamento:

**[INSERIR AQUI A TABELA COMPARATIVA DE REBALANCEAMENTO — QUESTÃO 3]**

*Tabela 7: Desempenho comparativo por frequência de rebalanceamento.*

### 4.3 Análise gráfica

O gráfico abaixo mostra a evolução do capital acumulado (riqueza) para cada frequência de rebalanceamento ao longo do período de teste:

**[INSERIR AQUI O GRÁFICO DE EVOLUÇÃO DO CAPITAL — QUESTÃO 3]**

*Figura 4: Evolução do capital acumulado por frequência de rebalanceamento.*

### 4.4 Conclusão e intervalo sugerido

Com base nos resultados das simulações e nos critérios estabelecidos, o intervalo de rebalanceamento sugerido é:

> **[COLAR O INTERVALO SUGERIDO PELO NOTEBOOK]**

**[COLAR A JUSTIFICATIVA AUTOMÁTICA DO NOTEBOOK]**

**Justificativa:** A frequência **[Mensal / Bimestral / Trimestral / Semestral / Anual]** apresentou a menor volatilidade anualizada realizada fora da amostra, que é o critério principal para uma estratégia de mínima variância. Esse intervalo representa um bom compromisso entre a estabilidade da carteira (evitando custos excessivos de transação com rebalanceamentos muito frequentes) e a capacidade de adaptação a mudanças nas condições de mercado (evitando que a carteira se distancie muito dos pesos ótimos).

Adicionalmente, o turnover médio observado nessa frequência foi de **[COLAR VALOR]**, indicando que as alterações nos pesos entre rebalanceamentos consecutivos são moderadas, o que é desejável do ponto de vista de custos operacionais.

---

## 5. Referências

- MARKOWITZ, Harry. Portfolio Selection. *The Journal of Finance*, v. 7, n. 1, p. 77-91, 1952.

- SHARPE, William F. Capital Asset Prices: A Theory of Market Equilibrium under Conditions of Risk. *The Journal of Finance*, v. 19, n. 3, p. 425-442, 1964.

- Material da disciplina MFC — Aula 13: Teoria de Markowitz. Prof. Pedro Vitor de Barba, UDESC/CCT, 2026.

- Yahoo Finance. Dados históricos de cotações. Disponível via biblioteca `yfinance` (Python).

---

## Anexo I — Código-fonte

O código-fonte completo utilizado nas análises está disponível no arquivo `exercicioPratico.ipynb`, entregue juntamente com este relatório.
