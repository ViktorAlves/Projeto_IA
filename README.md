# 🫀 Detecção de Doença Arterial Coronariana via Machine Learning

> **Projeto Integrador** — Faculdade de Computação e Informática (FCI)  
> **Universidade Presbiteriana Mackenzie** — São Paulo, SP  

---

## 📌 Sobre o Projeto

As doenças cardiovasculares constituem uma das principais causas de mortalidade no mundo, sendo a **Doença Arterial Coronariana (DAC / CAD)** uma de suas manifestações de maior relevância clínica. 

Este projeto tem como objetivo desenvolver, otimizar e avaliar modelos supervisionados de **Machine Learning** para detectar a presença de DAC a partir de dados clínicos do conjunto **Z-Alizadeh Sani** (disponibilizado pelo *UCI Machine Learning Repository*). O pipeline abrange desde a **Análise Exploratória de Dados (EDA)** até o treinamento de algoritmos, análise de erros de classificação, identificação de importância das características e explicabilidade (XAI).

---

## 👨‍💻 Integrantes do Grupo

```text
👤 Ana Clara Gierse Raymundo [![LinkedIn](https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](())
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

**Orientador / Professor:** Prof. Dr. Luiz Carlos Machi Lozano  
*Faculdade de Computação e Informática (FCI)*

---

## 📊 Estrutura do Dataset

O dataset **Z-Alizadeh Sani** é composto por **303 pacientes** e **54 características clínicas** divididas em 4 categorias principais:

- **Demográficos & Fatores de Risco:** Idade, Sexo, IMC, Hipertensão (HTN), Diabetes (DM), Tabagismo, Histórico Familiar (FH), Obesidade.
- **Sintomas & Exame Físico:** Tipo de Dor Torácica (Típica, Atípica, Não Anginosa), Pulso Periférico, Sopros, Dispneia.
- **Eletrocardiograma (ECG):** Onda Q, Elevação/Depressão do Segmento ST, Inversão da Onda T, Sobrecarga Ventricular Esquerda (LVH), Bloqueios de Ramo (BBB).
- **Exames Laboratoriais & Ecocardiograma:** Glicemia em Jejum (FBS), Colesterol (TG, LDL, HDL), Creatinina, Hemoglobina, Fração de Ejeção (`EF-TTE`), RWMA Regional.

### Variável Alvo (`Cath`)
- **`Cad` (216 casos):** Estreitamento ≥ 50% em pelo menos uma das artérias coronárias.
- **`Normal` (87 casos):** Pacientes sem lesão coronariana significativa.

---

## ⚙️ Metodologia & Modelos Avaliados

O pipeline experimental é composto pelas seguintes etapas:

1. **Análise Exploratória de Dados (EDA):** Verificação de integridade, ausência de nulos, distribuições e estatísticas descritivas.
2. **Pré-Processamento:** Codificação de variáveis categóricas (*One-Hot Encoding* / *Label Encoding*) e padronização das numéricas.
3. **Modelagem Supervisionada:**
   - 🔹 Regressão Logística (*Logistic Regression*)
   - 🔹 Máquinas de Vetores de Suporte (*Support Vector Machine - SVM*)
   - 🔹 Florestas Aleatórias (*Random Forest*)
   - 🔹 Gradiente Boosting Extremo (*XGBoost*)
4. **Otimização:** Otimização de hiperparâmetros com `GridSearchCV` e Validação Cruzada Estratificada.
5. **Métricas de Avaliação:** Acurácia, Precisão, **Recall** (foco em minoração de Falsos Negativos), Especificidade, F1-score e ROC-AUC.
6. **Explicabilidade:** Importância dos atributos e análise local/global com `SHAP`.

---

## 📅 Alterações do Repositório
```text
Data	Autor	Descrição da atualização
12/09/2026	Victor Alves	Criação do repositório e adição da base de dados
13/09/2026	Victor Alves	Adição do Relatório e Notebook python
```

---

## 📁 Estrutura do Repositório

```text

├── Base de dados/
|      └── 📊 Z-Alizadeh sani dataset.xlsx    # Base de dados oficial utilizada no projeto
├──Notebooks/
|      └──📓 Projeto_IA_EDA_Modelos.ipynb    # Notebook Jupyter/Colab com o código-fonte da análise e modelos
├── Relatório/
|      └── 📕 Projeto_IA.pdf                  # Relatório acadêmico completo em formato PDF
├── 📄 README.md                        # Documentação e apresentação do repositório
```

