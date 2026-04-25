# Tech Challenge Fase 1 — Pós Tech/FIAP
## Classificação de Síndrome dos Ovários Policísticos (SOP) com Machine Learning

## Objetivo do Projeto
Construir uma solução inicial de Inteligência Artificial focada em Machine Learning para processamento de dados médicos relacionados à saúde da mulher, aplicando fundamentos essenciais de IA e aprendizado de máquina.
Especificamente, desenvolvemos um sistema de classificação automática da Síndrome dos Ovários Policísticos (SOP), capaz de analisar dados clínicos de pacientes e identificar padrões de risco, apoiando profissionais de saúde na identificação precoce da condição.
O modelo desenvolvido atua como ferramenta de apoio ao diagnóstico, sendo o médico sempre responsável pela decisão final.
Projeto desenvolvido como parte do Tech Challenge Fase 1 da Pós Tech/FIAP.

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
pip install pandas numpy matplotlib seaborn scikit-learn shap joblib openpyxl

## Estrutura do Projeto
```
tech-challenge/
├── pcos_sop_final.ipynb                # Notebook principal
├── PCOS_data_without_infertility.xlsx  # Dataset
├── modelo_pcos_random_forest.pkl       # Modelo Random Forest salvo
├── modelo_pcos_arvore_decisao.pkl      # Modelo Árvore de Decisão salvo
└── README.md                           # Documentação
```
## Explicabilidade e Transparência
Para garantir que o modelo seja confiável para uso médico, utilizamos a biblioteca SHAP (SHapley Additive exPlanations). Isso nos permite entender não apenas o que o modelo previu, mas quais variáveis (como níveis hormonais ou sinais físicos) foram determinantes para cada diagnóstico individual.

## Tratamento de Dados
O projeto inclui um pipeline de limpeza que trata: Imputação de valores ausentes por média e moda; Ajuste de cabeçalhos e seleção de abas específicas de arquivos .xlsx complexos; Conversão de tipos de dados para processamento numérico de alta precisão.

## Tecnologias Utilizadas
Python 3.13.5, pandas, numpy, matplotlib, seaborn, scikit-learn, shap, joblib

## Resultado Principal
O Random Forest obteve 91% de acurácia na classificação de SOP. As variáveis mais importantes foram o número de folículos ovarianos, ganho de peso e crescimento de pelos — consistentes com os Critérios Clínicos de Rotterdam, que constituem o padrão ouro internacional para o diagnóstico da Síndrome dos Ovários Policísticos (SOP).
