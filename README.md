# Tech Challenge Fase 1 — PosTech/FIAP
## Classificação de Síndrome dos Ovários Policísticos (SOP) com Machine Learning

## Descrição
Solução de Machine Learning para classificação da Síndrome dos Ovários Policísticos (SOP), usando dados clínicos de 541 pacientes. Projeto desenvolvido como parte do Tech Challenge Fase 1 da PosTech/FIAP.

## Dataset
- **Nome:** PCOS_data_without_infertility.xlsx
- **Fonte:** Kaggle — prasoonkottarathil/polycystic-ovary-syndrome-pcos
- **Registros:** 541 pacientes, 45 variáveis clínicas

## Modelos Desenvolvidos
| Modelo | Acurácia | Precision | Recall | F1 |
|--------|----------|-----------|--------|----|
| Árvore de Decisão | 89% | 0.85 | 0.81 | 0.83 |
| Random Forest | 91% | 0.93 | 0.78 | 0.85 |

## Como Executar
1. Clone o repositório
2. Instale as dependências: pip install pandas numpy matplotlib seaborn scikit-learn shap joblib openpyxl
3. Abra o notebook: pcos_sop_final.ipynb
4. Execute todas as células: Run All

## Estrutura do Projeto
```
tech-challenge/
├── pcos_sop_final.ipynb                # Notebook principal
├── PCOS_data_without_infertility.xlsx  # Dataset
├── modelo_pcos_random_forest.pkl       # Modelo Random Forest salvo
├── modelo_pcos_arvore_decisao.pkl      # Modelo Árvore de Decisão salvo
└── README.md                           # Documentação
```

## Tecnologias
Python 3.13.5, pandas, numpy, matplotlib, seaborn, scikit-learn, shap, joblib

## Resultado Principal
O Random Forest obteve 91% de acurácia na classificação de SOP. As variáveis mais importantes foram o número de folículos ovarianos, ganho de peso e crescimento de pelos — consistentes com os critérios clínicos de Rotterdam.
