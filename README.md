# 🧠 Desafio 1 – Ciência e Governança de Dados  
### Universidade Federal de Lavras (UFLA)  
**Autor:** Paulo Henrique dos Anjos Silveira – 202310533  
**Ano:** 2025  
**Tema:** Avaliar e prever os agentes e fenômenos que mais causam impactos socioeconômicos no Brasil  
**Região estudada:** Sudeste  

---

## 🎯 Descrição

O presente trabalho tem como objetivo entender como fatores econômicos, sociais e estruturais se relacionam e impactam o desenvolvimento socioeconômico nos municípios da Região Sudeste do Brasil, em conformidade com o *Desafio I – Ciência e Governança de Dados* proposto pela Zetta Lab/UFLA.

Foram utilizados dados públicos e oficiais de diferentes fontes nacionais (IBGE, DATASUS, PNUD, Atlas Brasil e ANATEL), integrando indicadores relacionados a educação, renda, conectividade, violência e saúde.

---

## 📊 Indicadores Utilizados

Os dados utilizados neste trabalho foram selecionados dentro de um bienio (2021–2022), com o objetivo de garantir maior consistência temporal e comparabilidade entre os indicadores socioeconômicos.  
A escolha de um intervalo curto reduz distorções causadas por variações de metodologia e mudanças conjunturais.  

Entretanto, o indicador de Expectativa de Vida ao Nascer teve como referência o censo de 2010, pois é a última base oficial consolidada pelo IBGE com abrangência nacional e municipal.

| Indicador | Ano | Fonte | Descrição |
|------------|------|--------|------------|
| **População Residente** | 2022 | IBGE | Total de habitantes por município. |
| **Taxa de Analfabetismo (15+)** | 2022 | Atlas do Desenvolvimento Humano (PNUD/IPEA/FJP) | Percentual da população adulta que não sabe ler e escrever. |
| **Taxa de Desemprego Média** | 2022 | PNAD Contínua – IBGE | Média dos trimestres de 2022, representando o percentual de pessoas desocupadas. |
| **Índice Brasileiro de Conectividade (IBC)** | 2022 | ANATEL | Percentual de domicílios com acesso à Internet, refletindo a inclusão digital. |
| **Produto Interno Bruto (PIB)** | 2021 | IBGE | Valor total dos bens e serviços produzidos por município (preços de mercado). |
| **Índice de Desenvolvimento Humano Municipal (IDHM)** | 2021 | PNUD | Índice composto por renda, longevidade e educação. |
| **Expectativa de Vida ao Nascer** | 2010 | IBGE | Média de anos de vida esperados para um recém-nascido, segundo as condições de mortalidade observadas. |

💡 **Resumo:**  
> O uso de dados dentro de um mesmo período (bienio 2021–2022) assegura que as comparações entre indicadores reflitam condições socioeconômicas equivalentes, aumentando a confiabilidade das correlações.  
> A exceção da expectativa de vida (2010) não compromete o modelo, pois esse indicador evolui lentamente e mantém validade analítica como referência de longevidade.

---

## ⚙️ Metodologia

1. **Aquisição e limpeza dos dados:**  
   - Remoção de colunas vazias e duplicadas;  
   - Conversão de tipos numéricos;  
   - Preenchimento de valores ausentes com médias estaduais.  

2. **Integração das bases:**  
   - Junção (`merge`) das tabelas por município e estado, consolidando todos os indicadores em um único DataFrame.  

3. **Agregação e sumarização:**  
   - Cálculo de médias e somas por estado (`groupby`), representando a realidade da região Sudeste.  

4. **Análise exploratória:**  
   - Geração de gráficos interativos com `Plotly` (dispersão, barras, heatmap);  
   - Cálculo de correlações de Pearson entre variáveis;  
   - Aplicação de modelos de regressão linear (OLS) para estimar relações entre indicadores socioeconômicos.  

---

## 📈 Matriz de Correlação

A matriz de correlação apresenta a força e o sentido das relações entre os indicadores socioeconômicos analisados.  
O coeficiente de correlação de Pearson (ρ) varia entre **–1 e +1**, indicando:

- **+1:** correlação positiva perfeita (as variáveis crescem juntas);  
- **0:** ausência de correlação linear;  
- **–1:** correlação negativa perfeita (quando uma cresce, a outra diminui).

Neste estudo, a matriz permitiu identificar quais fatores estão mais associados ao desenvolvimento socioeconômico dos estados do Sudeste.  
Os resultados mostraram relações positivas fortes entre PIB, IDHM e expectativa de vida, o que confirma a ligação entre riqueza e qualidade de vida.  
Em contrapartida, observaram-se correlações negativas entre homicídios e expectativa de vida, reforçando o impacto da violência sobre o bem-estar populacional.

A análise da matriz serviu como base para selecionar as variáveis mais relevantes nas regressões e nos modelos preditivos aplicados posteriormente, garantindo uma interpretação mais consistente e alinhada com a realidade socioeconômica regional.

---

## 📊 Resultados das Regressões Lineares

| Relação | Interpretação |
|----------|----------------|
| **População × PIB** | Relação forte e direta: municípios mais populosos tendem a gerar maior PIB. Demonstra o peso econômico das grandes concentrações urbanas. |
| **PIB × Expectativa de Vida** | Associação moderada positiva: crescimento econômico está ligado à melhoria da qualidade de vida e longevidade. |
| **Internet × IDHM** | Relação muito fraca: o IDHM (de 2010) não reflete o avanço recente da conectividade; há defasagem temporal entre os indicadores. |
| **Homicídios × Expectativa de Vida** | Correlação negativa moderada: aumento da violência impacta diretamente a longevidade média da população. |
| **IDHM × Desemprego** | Relação fraca: embora esperada uma tendência inversa, a variação do IDHM é pequena entre estados, reduzindo a força da regressão. |
| **Analfabetismo × IDHM** | Associação negativa leve: o analfabetismo influencia o desenvolvimento humano, mas há outros fatores mais determinantes. |
| **Internet × Analfabetismo** | Relação forte e inversa: maior acesso à Internet está associado à redução do analfabetismo e ao avanço da inclusão digital. |

💡 **Interpretação geral:**  
Os resultados confirmam que população, PIB e conectividade digital têm papel central na dinâmica socioeconômica do Sudeste.

---

## 🧠 Conclusão

Os resultados apontam que, na Região Sudeste, o PIB, a expectativa de vida e o IDHM são os indicadores mais diretamente ligados ao desenvolvimento humano.  

Estados com economias mais fortes e maiores índices de conectividade tendem a apresentar melhores condições de vida e menor vulnerabilidade social.  
Em contrapartida, violência e desemprego mostram-se fortemente associados à redução da longevidade e à piora do bem-estar populacional.  

Além disso, a conectividade (IBC) surge como um novo determinante de desigualdade, um fator emergente que ainda não é plenamente captado pelos indicadores tradicionais de desenvolvimento humano.

---

## 💾 Reprodutibilidade

1. Instale as dependências:
   ```bash
   pip install pandas numpy plotly statsmodels scikit-learn
   ```

2. Execute o notebook:
   ```bash
   python meudesafio2.py
   ```

3. Estrutura esperada de diretórios:
   ```
   dados/
     populacao_total.csv
     pib_precos_de_mercado.csv
     taxa_de_desemprego.csv
     cobertura_internet.csv
     numero_homicidios.csv
     esperança_de_vida_ao_nascer.csv
     idhm_estados.csv
     taxa_de_analfabetismo.csv
   ```

---

## 📚 Referências

- Instituto Brasileiro de Geografia e Estatística (IBGE)  
- Programa das Nações Unidas para o Desenvolvimento (PNUD)  
- Atlas do Desenvolvimento Humano (IPEA/PNUD/FJP)  
- Agência Nacional de Telecomunicações (ANATEL)  
- DATASUS – Ministério da Saúde  
- **Zetta Lab 2025 – UFLA**: *Desafio 1: Ciência e Governança de Dados*
