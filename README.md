# 🧪 A/B Testing — Teste de Hipóteses para Validação de Sistema de Recomendação

Análise de teste A/B para avaliar se um novo sistema de recomendação melhora a taxa de conversão de um e-commerce, utilizando teste de hipóteses bicaudal com dados reais do Kaggle.

> **Parte do desafio [#7DaysOfCode](https://7daysofcode.io/) de Data Science — Dia 6/7**

---

## 📋 Sobre o Projeto

Simulando um cenário real de e-commerce, este projeto analisa os resultados de um teste A/B onde usuários foram distribuídos aleatoriamente entre duas versões de uma landing page: a versão atual (controle) e uma nova versão com sistema de recomendação (tratamento). O objetivo é validar estatisticamente se a nova versão gera mais conversões.

### Pipeline da análise

1. **Carregamento e exploração** — 294.478 registros com 5 colunas
2. **Limpeza de dados** — Identificação e remoção de 3.893 registros inconsistentes (1,32%)
3. **Análise exploratória** — Distribuição dos grupos, taxas de conversão, tendências ao longo do tempo
4. **Amostragem** — Seleção de 5.000 registros com `random_state=42`
5. **Teste estatístico** — Teste t bicaudal (`scipy.stats.ttest_ind`)

### Resultados

| Métrica | Valor |
|---------|-------|
| Registros originais | 294.478 |
| Registros após limpeza | 290.585 |
| Taxa de conversão (controle) | 12,04% |
| Taxa de conversão (tratamento) | 11,88% |
| Estatística t | -1,5837 |
| P-valor | 0,1133 |

### Conclusão

**Não há evidência estatística suficiente para rejeitar a hipótese nula.** A diferença entre as taxas de conversão dos dois grupos não é significativa (p-valor 0,1133 > 0,05), indicando que o sistema de recomendação não demonstrou impacto mensurável nas conversões. A recomendação seria **manter a página atual**.

---

## 🛠️ Tecnologias Utilizadas

- **Python 3.13**
- **Pandas** — Manipulação e limpeza de dados
- **Matplotlib** — Visualizações
- **Seaborn** — Gráficos estatísticos
- **SciPy** — Teste t bicaudal (`scipy.stats.ttest_ind`)

---

## 📁 Estrutura do Projeto

```
ab-testing-hypothesis/
├── analise_ab_testing.ipynb   # Notebook com análise completa
├── data/
│   └── archive.zip            # Dataset do Kaggle (compactado)
├── LICENSE                     # Arquivo de Licença
├── README.md                   # Este arquivo
├── requirements.txt            # Dependências do projeto
└── .gitignore                  # Arquivos ignorados pelo Git
```

---

## 🚀 Como Executar

### 1. Clone o repositório
```bash
git clone https://github.com/Bernardinense/ab-testing-hypothesis.git
cd ab-testing-hypothesis
```

### 2. Instale as dependências
```bash
pip install -r requirements.txt
```

### 3. Extraia o dataset

O dataset está incluído no repositório em `data/archive.zip`. Extraia o arquivo `ab_data.csv` para a raiz do projeto:

```
ab-testing-hypothesis/
├── ab_data.csv   ← extrair aqui
├── analise_ab_testing.ipynb
└── ...
```

**Fonte original:** [A/B Testing — Kaggle](https://www.kaggle.com/datasets/zhangluyuan/ab-testing)

### 4. Execute o notebook
```bash
jupyter notebook analise_ab_testing.ipynb
```

---

## 🔗 Parte do Desafio #7DaysOfCode

Este projeto é o **Dia 6** de um desafio de 7 dias cobrindo o pipeline completo de Data Science:

| Dia | Projeto | Tema |
|-----|---------|------|
| 1 | [ceaps-data-wrangling](https://github.com/Bernardinense/ceaps-data-wrangling) | Limpeza e Tratamento de Dados |
| 2 | [ceaps-storytelling](https://github.com/Bernardinense/ceaps-storytelling) | Visualização e Storytelling |
| 3 | [ceaps-forecasting](https://github.com/Bernardinense/ceaps-forecasting) | Previsão com Prophet e Sklearn |
| 4 | [movie-recommendation-system](https://github.com/Bernardinense/movie-recommendation-system) | Sistema de Recomendação |
| 5 | [movie-recommendation-api](https://github.com/Bernardinense/movie-recommendation-api) | API REST com FastAPI |
| **6** | **ab-testing-hypothesis** | **Teste A/B e Validação de Hipóteses** |

📌 Veja a jornada completa: [7DaysOfCode-DataScience](https://github.com/Bernardinense/7DaysOfCode-DataScience)

---

## 👤 Autor

**Bruno Corrêa** —  Engenheiro | Especialista em Ciência de Dados

[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/bfpc7/)
[![GitHub](https://img.shields.io/badge/GitHub-black?style=flat&logo=github)](https://github.com/Bernardinense)

---

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.