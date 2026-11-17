# 🫀 Detecção de Doença Arterial Coronariana via Machine Learning

> **Projeto Integrador** — Faculdade de Computação e Informática (FCI)  
> **Universidade Presbiteriana Mackenzie** — São Paulo, SP  

---

## 📌 Sobre o Projeto

As doenças cardiovasculares constituem uma das principais causas de mortalidade no mundo, sendo a **Doença Arterial Coronariana (DAC / CAD)** uma de suas manifestações de maior relevância clínica[cite: 2]. 

Este projeto tem como objetivo desenvolver, otimizar e avaliar modelos supervisionados de **Machine Learning** para detectar a presença de DAC a partir de dados clínicos do conjunto **Z-Alizadeh Sani** (disponibilizado pelo *UCI Machine Learning Repository*)[cite: 1, 2, 3]. O pipeline abrange desde a **Análise Exploratória de Dados (EDA)** até o treinamento de algoritmos, ajuste de hiperparâmetros com `GridSearchCV` e análise minuciosa dos erros de classificação[cite: 1].

---

## 🛠️ Opção Framework & Tecnologias

O projeto se enquadra na **Opção Framework**, conforme proposta da disciplina, utilizando técnicas de aprendizado supervisionado para um problema de classificação binária na área da saúde[cite: 3].

O desenvolvimento é realizado em **Python**, utilizando principalmente o framework **`scikit-learn`** para as etapas de preparação dos dados, divisão entre treino e teste, validação cruzada, otimização de hiperparâmetros e implementação dos modelos Regressão Logística, Support Vector Machine (SVM) e Random Forest[cite: 3]. Para o modelo XGBoost, é utilizada a biblioteca específica **`XGBoost`**, integrada ao mesmo fluxo de treinamento e avaliação[cite: 3].

---

## 👨‍💻 Integrantes do Grupo

```text
👤 Ana Clara Gierse Raymundo 
├─ TIA:    10428453
└─ E-mail: 10428453@mackenzista.com.br

👤 Erica Gonçalves de Oliveira
├─ TIA:    10428459
└─ E-mail: 10428459@mackenzista.com.br

👤 Luana Domingos Branco
├─ TIA:    10428547
└─ E-mail: 10428547@mackenzista.com.br

👤 Victor Luiz de Sá Alves
├─ TIA:    10426310
└─ E-mail: 10426310@mackenzista.com.br
```

---

## 📊 Estrutura do Dataset

O dataset **Z-Alizadeh Sani** é composto por **303 pacientes** e **54 características clínicas**[cite: 1]:

* **Demográficos & Fatores de Risco:** Idade, Sexo, IMC, Hipertensão (HTN), Diabetes (DM), Tabagismo, Obesidade[cite: 5, 6].
* **Sintomas & Exame Físico:** Tipo de Dor Torácica, Pulso Periférico, Sopros, Dispneia.
* **Exames Laboratoriais & Ecocardiograma:** Glicemia em Jejum (FBS), Colesterol (Triglicerídeos, LDL, HDL), Fração de Ejeção (`EF-TTE`)[cite: 5, 6].

### Variável Alvo (`Cath`)[cite: 5]
* **`Cad` (216 casos - 71,3%):** Estreitamento ≥ 50% em pelo menos uma das artérias coronárias[cite: 3, 5].
* **`Normal` (87 casos - 28,7%):** Pacientes sem lesão coronariana significativa[cite: 3, 5].

---

## ⚙️ Metodologia & Pipeline Experimental

1. **Análise Exploratória de Dados (EDA):** Verificação de integridade, ausência de nulos e distribuições da amostra[cite: 5, 6].
2. **Pré-Processamento:** Imputação de valores ausentes (mediana para numéricos, moda para categóricos), padronização com `StandardScaler` e codificação com `OneHotEncoder`[cite: 6].
3. **Modelagem Supervisionada:** Regressão Logística, Support Vector Machine (SVM), Random Forest e XGBoost[cite: 1].
4. **Otimização:** Uso de `GridSearchCV` com validação cruzada estratificada (5 folds) utilizando o **Recall** como critério de seleção para mitigar falsos negativos[cite: 6].
5. **Métricas de Avaliação:** Acurácia, Precisão, Recall, Especificidade, F1-score e ROC-AUC[cite: 1].

---

## 📈 Resultados e Desempenho dos Modelos

Após a otimização de hiperparâmetros, os modelos obtiveram os seguintes resultados no conjunto de teste[cite: 6, 7]:

| Modelo | Acurácia | Precisão | Recall | Especificidade | F1-score | ROC-AUC |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **Regressão Logística** | **90,2%** | **89,4%** | **97,7%** | **72,2%** | **93,3%** | **91,0%** |
| **SVM** | 70,5% | 70,5% | 100,0% | 0,0% | 82,7% | 89,7% |
| **Random Forest** | 85,2% | 84,0% | 97,7% | 55,6% | 90,3% | 88,6% |
| **XGBoost** | 82,0% | 84,8% | 90,7% | 61,1% | 87,6% | 83,7% |

### 🔍 Análise de Erros de Classificação (Falsos Positivos vs. Falsos Negativos)

Na área da saúde, minimizar **falsos negativos** (pacientes doentes diagnosticados como saudáveis) é crítico[cite: 3, 7]:

| Modelo | Falsos Positivos (FP) | Falsos Negativos (FN) |
| :--- | :---: | :---: |
| **Regressão Logística** | **5** | **1** |
| **SVM** | 18 | 0 |
| **Random Forest** | 8 | 1 |
| **XGBoost** | 7 | 4 |

> **Conclusão dos Resultados:** A **Regressão Logística** apresentou o melhor equilíbrio geral do projeto (90,2% de acurácia, 91,0% de ROC-AUC e apenas 1 falso negativo), demonstrando superioridade na robustez e interpretabilidade para este cenário clínico[cite: 1, 7].

---

## 📅 Histórico de Atualizações do Repositório

```text
Data        Autor               Descrição da atualização
12/09/2026  Victor Alves        Criação do repositório e adição da base de dados
13/09/2026  Victor Alves        Adição do Relatório e Notebook python
14/09/2026  Victor Alves        Adição do readme ao repositório
08/11/2026  Ana Clara           Adição do Notebook python completo
13/11/2026  Victor Alves        Adição do Relatório completo
14/11/2026  Victor Alves        Edição para completar informações do repositório
```

---

## 📁 Estrutura do Repositório

```text

├── Base de dados/
|      └── 📊 Z-Alizadeh sani dataset.xlsx    # Base de dados oficial utilizada no projeto
├──Notebooks/
       └──📓 Proejto_IA.pdf                   #Relatório acadêmico em formato PDF com os pedido da N1
|      └──📓 ProjetoIA.ipynb                  # Notebook Jupyter/Colab com o código-fonte da análise e modelos
├── N2/
|      └── 📕 Projeto_IA.pdf                  # Relatório acadêmico completo em formato PDF
       └── 📕 ProjetoIA_N2.jpynb              # Notebook Jupyter/Colab com o código-fonte da análise e modelos completo
├── 📄 README.md                        # Documentação e apresentação do repositório
```

---

## 📱 Redes Sociais e Contatos

[![LinkedIn](https://img.shields.io/badge/-LinkedIn_Ana_Gierse-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/ana-g-548419230)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn_Erica_Oliveira-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/erica-oliveira-7597b9291?utm_source=share_via&utm_content=profile&utm_medium=member_android)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn_Luana_Domingos-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/luana-domingos-branco-25a480256)
[![LinkedIn](https://img.shields.io/badge/-LinkedIn_Victor_Alves-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/victor-luiz-b39738222/)

