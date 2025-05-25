# **Projeto Didático de ETL com Pandas: Emissões de CO₂ por País**

## 🎯 Objetivo

Este projeto tem como finalidade praticar e documentar o processo ETL (**Extração, Transformação e Carga**) utilizando exclusivamente a biblioteca **pandas**, com foco em dados reais de emissões de CO₂. Trata-se de um estudo **didático**, realizado para fins de **aprendizado pessoal** e desenvolvimento de **portfólio** na área de Ciência de Dados.

---

## 📊 Fonte dos Dados

- **Dataset:** `GCB2024v17_MtCO2_flat.csv`
- **Plataforma:** [Zenodo](https://zenodo.org/record/13981696)
- **Dados:** Emissões históricas de CO₂ por país, desde **1750**

### 📚 Referência Bibliográfica

Ritchie, H., Roser, M., & Rosado, P. (2020). *CO₂ and Greenhouse Gas Emissions*. Our World in Data.
Disponível em: [https://ourworldindata.org/co2-and-greenhouse-gas-emissions](https://ourworldindata.org/co2-and-greenhouse-gas-emissions)

---

## 🔧 Etapas do Processo ETL

### 1. 📥 Extração

- Leitura dos dados diretamente da web via `pandas.read_csv()`.
- Dataset original extraído do Zenodo.
- Validação dos países com `pycountry`.
- Verificação da estrutura do DataFrame com `.info()` e `.head()`.

### 2. 🧹 Limpeza

- Remoção de colunas desnecessárias.
- Exclusão de registros não representativos (territórios e entidades agregadas).
- Filtragem por países válidos com código ISO-3166 alpha-3.
- Conversão do ano para tipo inteiro.
- Exclusão de registros com emissões totais nulas.

### 3. 🔄 Transformação

- Criação da coluna `'Total Emissions'` com a soma das principais fontes.
- Conversão de megatoneladas para toneladas (multiplicação por 1 milhão).
- Preenchimento de valores ausentes com `fillna(0)` e tipagem como `int`.

### 4. 💾 Carga

- Exportação dos dados tratados para um arquivo `.xlsx` com **múltiplas abas**:
    - Aba "Geral" com todos os dados consolidados.
    - Aba específica para país China.
- Geração e download do arquivo no ambiente Google Colab.

---

## 📈 Visualização e Análise com Looker Studio

Após o processo ETL, os dados foram carregados em um ambiente de visualização utilizando o **Looker Studio**. Essa etapa foi crucial para transformar os dados brutos em visuais gráficos.
![Sem título](https://github.com/user-attachments/assets/07187666-4ef5-43a3-86f1-e43a4d81c69c)

No Looker Studio, foram desenvolvidos painéis que permitiram:

- **Análise das Emissões Totais por País** e **Composição Anual das Emissões por Fonte**:
  ![Sem título](https://github.com/user-attachments/assets/61d03056-c3f6-4755-bc5d-0e7a0bade0e0)

- **Estudo Específico**: Uma análise da trajetória de emissões de dióxido de carbono da China, destacando a aceleração acentuada a partir das últimas décadas, reflexo da intensa industrialização e desenvolvimento econômico. ![Sem título](https://github.com/user-attachments/assets/771ebf8c-bc72-4399-8a89-6244934b03dd)

Esta fase com o Looker Studio demonstrou a capacidade de criar representações gráficas claras e objetivas a partir de dados complexos, facilitando a interpretação e a identificação de tendências importantes sobre as emissões de CO₂.

