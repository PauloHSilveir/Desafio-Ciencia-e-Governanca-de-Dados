# Desafio – Ciência e Governança de Dados

### Universidade Federal de Lavras (UFLA)

**Autor:** Paulo Henrique dos Anjos Silveira – 202310533
**Ano:** 2025
**Tema:** Avaliar e prever os agentes e fenômenos que mais causam impactos socioeconômicos nos municípios da Região Sudeste, aplicando modelos interpretáveis para formular recomendações de políticas públicas.

---

## Descrição

Este repositório tem como objetivos:
(1) identificar os fatores socioeconômicos mais associados ao desenvolvimento humano municipal;
(2) construir modelos preditivos interpretáveis;
(3) gerar recomendações estratégicas para políticas públicas com base nos resultados obtidos.

Foram utilizados dados públicos e oficiais de fontes nacionais, como IBGE, PNUD/Atlas, ANATEL e DATASUS, integrando indicadores de educação, renda, conectividade, violência e saúde.

---

## Indicadores utilizados e observações sobre os dados

Os dados centrais abrangem principalmente o período de 2021–2022, visando manter consistência temporal entre as fontes.
No **Desafio 2**, foram realizados os seguintes ajustes:

* Inclusão de variáveis derivadas para aprimorar a interpretação dos resultados.

---

## Escolhas metodológicas

1. Preparação e transformação de variáveis
2. Divisão dos dados em conjuntos de treino e teste, com padronização
3. Modelagem e interpretação

   * Modelos utilizados: Random Forest, XGBoost e Ridge Regression (α = 0.5)
4. Validação dos modelos e análise de robustez

---

## Conclusão

A escolha do `IDHM` como variável-alvo é justificada por sua natureza multidimensional — renda, educação e longevidade — e por sua ampla relevância no apoio à formulação e avaliação de políticas públicas.

---

## Reprodutibilidade

1. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

2. Execute os notebooks:
      Abra o notebook no Google Colab e execute:
      Runtime → Run all

---

## Referências

* Instituto Brasileiro de Geografia e Estatística (IBGE)
* Programa das Nações Unidas para o Desenvolvimento (PNUD)
* Atlas do Desenvolvimento Humano (IPEA/PNUD/FJP)
* Agência Nacional de Telecomunicações (ANATEL)
* DATASUS – Ministério da Saúde
* **Zetta Lab 2025 – UFLA**: *Desafio 1 e 2 – Ciência e Governança de Dados*
