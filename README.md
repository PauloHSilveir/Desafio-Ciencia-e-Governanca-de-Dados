# Desafio – Ciência e Governança de Dados

### Universidade Federal de Lavras (UFLA)

**Autor:** Paulo Henrique dos Anjos Silveira – 202310533
**Ano:** 2025

**Tema:** Avaliar e prever os principais agentes e fenômenos associados aos impactos socioeconômicos nos municípios da Região Sudeste, utilizando modelos interpretáveis para subsidiar recomendações de políticas públicas.

---

## Os objetivos principais são:

1. Identificar fatores socioeconômicos associados ao desenvolvimento humano municipal;
2. Construir e comparar modelos preditivos interpretáveis;
3. Formular recomendações estratégicas para políticas públicas a partir dos resultados obtidos.

---

## Dados e Indicadores

Foram utilizados dados públicos e oficiais provenientes de fontes nacionais, incluindo:

* IBGE
* PNUD / Atlas do Desenvolvimento Humano
* ANATEL
* DATASUS

### Observações sobre os dados

No Desafio 2, foram realizadas adaptações e transformações adicionais, incluindo:

* Criação de variáveis derivadas para melhorar a capacidade explicativa e interpretabilidade dos modelos.

---

## Metodologia

As principais etapas metodológicas incluem:

1. Preparação, limpeza e transformação das variáveis
2. Divisão dos dados em conjuntos de treino e teste, com padronização quando aplicável
3. Modelagem preditiva e interpretação dos resultados

   * Modelos utilizados: **Random Forest**, **XGBoost** e **Ridge Regression**
4. Validação cruzada e análise de robustez dos modelos

---

## Conclusão

A escolha do IDHM como variável-alvo é justificada por sua natureza multidimensional — renda, educação e longevidade — e por sua ampla relevância no apoio à formulação e avaliação de políticas públicas.

---

## Reprodutibilidade

Para reproduzir os resultados:

1. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

2. Execute os notebooks:

   * Abra os arquivos no **Google Colab**
   * Selecione **Runtime → Run all**

---

## Agradecimentos
* **Zetta Lab 2025 – UFLA**
  *Desafio 1 e 2 – Ciência e Governança de Dados*