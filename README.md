# Projeto Antifraude - Financiamento Veicular

## Descrição
Este projeto tem como objetivo **identificar potenciais fraudes em propostas de financiamento veicular**. Foram utilizadas técnicas de machine learning, análise exploratória e engenharia de features para criar um modelo que auxilie o negócio na tomada de decisão, protegendo o valor financeiro e reduzindo o risco operacional.

---

## Estrutura do Projeto
- **Notebook:** Jupyter Notebook contendo análise exploratória, pré-processamento, modelagem, avaliação e visualização de métricas.  
- **Slides:** Breve apresentação executiva mostrando o impacto do modelo no negócio e resultados financeiros estimados.  
- **Dados:** Colunas incluem `id`,`documento`,`mes_ref`,`vlr_financiado`, `VAR1` a `VAR200` e `alvo` (fraude 0/1)`.  

---

## Ciclo de Vida do Projeto
1. **Entendimento do Negócio**
   - Objetivo: identificar clientes com maior risco de fraude.  
   - Indicadores analisados: fraudes capturadas, valor protegido, recall, precision.  

2. **Entendimento dos Dados**
   - Análise da distribuição de variáveis para fraudes vs não fraudes.  
   - Tratamento de outliers, NaN e dados inconsistentes/irrelevantes.  

3. **Preparação dos Dados**
   - Engenharia de features: criação de novas variáveis e relações entre colunas (ex: `VAR78xVAR124`).  
   - Pré-processamento: one-hot encoding, target encoding e tratamento de valores nulos.  

4. **Modelagem**
   - Modelos testados: LightGBM e Random Forest.  
   - Técnicas de balanceamento: SMOTE, ADASYN e Borderline-SMOTE.  
   - Ajuste de thresholds para otimização de recall e precision.  

5. **Avaliação**
   - Métricas clássicas: Precision, Recall, F1-score, Confusion Matrix.  
   - Métricas voltadas ao negócio:  
     - Precision @ Top 10% clientes mais arriscados 
     - Fraudes capturadas analisando Top 10%  
     - Valor estimado protegido 
   - Curvas Precision-Recall e análise de impacto financeiro por cliente.  

6. **Próximos Passos**
   - Refinamento de thresholds e mensagens de risco.  
   - Implementação e coleta de features em ambiente de produção (PRD) para melhorar a modelagem futura.  
   - Investigação de concept drift e data drift.  
   - Explorar outros modelos e técnicas de balanceamento para aumentar precision.  
   - Análise mais completa com SHAP para melhorar decisões do modelo.  

---

## Resultado de Negócio
O modelo permite:
- **Priorizar clientes com maior risco de fraude**, permitindo revisões manuais mais eficientes.  
- **Estimativa de valor protegido**, ajudando a mensurar impacto financeiro potencial.  
- **Raciocínio transparente**: cada cliente recebe uma probabilidade de fraude e o valor do risco associado à operação.  

---

## Tecnologias e Bibliotecas Utilizadas
- Python 3.x  
- Pandas, NumPy, Matplotlib, Seaborn  
- Scikit-learn, LightGBM, Imbalanced-learn  
- SHAP para interpretação do modelo  
- Jupyter Notebook
