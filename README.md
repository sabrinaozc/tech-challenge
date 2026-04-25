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
O Random Forest obteve 91% de acurácia na classificação da SOP, com Recall de 0.78 e F1-score de 0.85 para a classe positiva. A Árvore de Decisão obteve Recall de 0.81 — superior ao Random Forest neste aspecto crítico. Em contexto médico, o Recall é a métrica mais importante. Com Recall de 0.78, o Random Forest deixa de identificar aproximadamente 22% dos casos reais de SOP — o que em escala hospitalar representa um número significativo de pacientes sem diagnóstico, com risco de complicações como infertilidade e diabetes tipo 2. Portanto, o modelo não é adequado para diagnóstico clínico direto. No entanto, o modelo tem valor real como ferramenta de triagem em regiões com acesso limitado a especialistas, priorizando quais pacientes devem ser encaminhadas com urgência ao ginecologista. As variáveis mais importantes — número de folículos ovarianos, ganho de peso e crescimento de pelos — são consistentes com os Critérios Clínicos de Rotterdam, validando que o modelo aprendeu padrões coerentes com a medicina. Para uso clínico real, seriam necessários: balanceamento de classes com SMOTE, ajuste de hiperparâmetros, validação cruzada e validação clínica por especialistas. Importante citar que o médico sempre tem a palavra final no diagnóstico.
