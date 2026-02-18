# 📊 Telecom X – Previsão de Evasão de Clientes (Churn Prediction)

## 🎯 Objetivo do Projeto

O objetivo deste projeto é desenvolver modelos preditivos capazes de identificar clientes com maior probabilidade de evasão (churn), permitindo que a empresa Telecom X atue de forma preventiva por meio de estratégias de retenção baseadas em dados.

O estudo contempla desde a preparação dos dados até a interpretação dos modelos e proposição de ações estratégicas para o negócio.

---

## 🧠 Metodologia

O projeto foi estruturado seguindo boas práticas de Ciência de Dados e Machine Learning, passando pelas seguintes etapas:

### 🔹 1. Extração e Preparação dos Dados
- Leitura de dados em formato JSON via repositório GitHub
- Normalização de estruturas aninhadas
- Limpeza de inconsistências e tratamento de valores ausentes
- Engenharia de atributos (ex.: custo diário e quantidade de serviços)
- Padronização e tradução de colunas para facilitar interpretação

### 🔹 2. Análise Exploratória
- Análise da distribuição da variável alvo (evasão)
- Verificação de desequilíbrio de classes (~73% ativos e ~27% evadidos)
- Visualização da matriz de correlação entre variáveis numéricas
- Análise da relação entre evasão e variáveis como:
  - Tempo de contrato
  - Cobrança mensal
  - Total gasto

---

## ⚖️ Balanceamento de Classes

Foi identificado um **desequilíbrio moderado** entre as classes.  
Para aprofundar a análise, foi aplicada a técnica **SMOTE (Synthetic Minority Over-sampling Technique)** exclusivamente no conjunto de treino, permitindo avaliar o impacto do balanceamento no desempenho dos modelos.

---

## 🤖 Modelos Preditivos Utilizados

Foram treinados e avaliados diferentes modelos de classificação:

| Modelo | Normalização | Observações |
|------|-------------|-------------|
| Regressão Logística | ✅ Sim | Modelo interpretável (baseline) |
| Regressão Logística + SMOTE | ✅ Sim | Prioriza recall da evasão |
| Random Forest | ❌ Não | Melhor desempenho geral |
| KNN (K-Nearest Neighbors) | ✅ Sim | Baseado em distância |
| SVM Linear | ✅ Sim | Analisa fronteira de decisão |

A normalização foi aplicada apenas aos modelos sensíveis à escala, conforme boas práticas de Machine Learning.

---

## 📈 Avaliação dos Modelos

Os modelos foram avaliados utilizando as seguintes métricas:
- **Acurácia**
- **Precisão**
- **Recall**
- **F1-score**
- **Matriz de confusão**
- **ROC-AUC** (métrica adicional relevante para churn)

### 🔍 Principais Resultados
- **Random Forest** apresentou o melhor desempenho geral, com bom equilíbrio entre precisão e recall
- **Regressão Logística com SMOTE** aumentou significativamente o recall da classe evasão
- Não foram observados sinais relevantes de overfitting
- A Regressão Logística simples apresentou leve underfitting, esperado por se tratar de um modelo linear

---

## 🔍 Análise das Variáveis Mais Relevantes

A relevância das variáveis foi analisada conforme a natureza de cada modelo.

### 🔴 Fatores que Aumentam a Evasão
- Contrato mensal
- Cobrança mensal elevada
- Baixo tempo de contrato
- Método de pagamento via cheque eletrônico

### 🟢 Fatores que Reduzem a Evasão
- Maior tempo de contrato (tenure)
- Contratos de 1 ou 2 anos
- Maior quantidade de serviços contratados
- Serviços adicionais (suporte técnico, segurança, backup)

Esses fatores foram consistentes entre os diferentes modelos, reforçando a robustez dos resultados.

---

## 🎯 Estratégias de Retenção Propostas

Com base nos resultados obtidos, recomenda-se:

### 📌 Curto Prazo
- Ações de retenção nos primeiros 3 a 6 meses de contrato
- Monitoramento ativo de clientes com contrato mensal
- Ofertas direcionadas para clientes com alta mensalidade

### 📦 Médio Prazo
- Incentivo à migração para contratos anuais ou bienais
- Criação de bundles de serviços para aumentar fidelização
- Revisão de métodos de pagamento associados a maior churn

### 🧠 Longo Prazo
- Implementação do modelo preditivo em produção
- Uso de modelos com maior recall para alertas de churn
- Personalização de ofertas com base na explicabilidade dos modelos

---

## 🏁 Conclusão

A evasão de clientes na Telecom X está fortemente associada a fatores de **fidelização** e **percepção de custo**.  
Os modelos desenvolvidos demonstraram bom desempenho preditivo e forneceram insights claros para orientar decisões estratégicas.

O uso combinado de modelos interpretáveis e robustos permite tanto prever a evasão quanto compreender seus principais motivadores, apoiando ações eficazes de retenção.

---

## 🛠️ Tecnologias Utilizadas
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Imbalanced-learn (SMOTE)

---

📌 *Projeto desenvolvido para fins educacionais e analíticos no contexto do desafio Telecom X.*
