# DATA HARVESTING / Projeto da Disciplina

## Universidade de Fortaleza - UNIFOR  
**Prof.:** Ms. Alex Lima  
**Curso:** MBA em Ciência de Dados  
**Aluna:** Gabriela Ferreira Coutinho - 2418581

# 📊 Champions League Analysis - Data Harvesting

## 🔗 Link do Repositório

Acesse o repositório no **[GitHub](https://github.com/gabrierys/Data-Harvesting-Sofascore/)**.

## 📌 Descrição do Projeto
Este projeto tem como objetivo coletar dados da UEFA Champions League a partir do site **Sofascore** e realizar uma análise das últimas 10 temporadas (entre 2014 até 2014). A coleta de dados é feita através de **Web Scraping**, utilizando as bibliotecas **Requests, BeautifulSoup e Selenium**.

## 🎯 Objetivos
- Realizar a coleta automatizada de estatísticas dos jogadores em cada temporada.
- Armazenar os dados em formato CSV de maneira organizada.
- Analisar e recuperar informações relevantes a partir dos dados coletados.

## 🛠 Ferramentas Utilizadas
- **Python 3.x**
- **Requests** (para coleta de páginas estáticas)
- **BeautifulSoup** (para extração de dados da página)
- **Selenium** (para interação com elementos dinâmicos)
- **Pandas** (para manipulação e armazenamento de dados)
- **Requests** (requisições HTTP)
- **Jupyter Notebook** (para execução e organização do código)

## 📂 Estrutura do Projeto
```
Champions-League-Analysis/
│── data/                           # Diretório onde serão salvos os dados coletados
│   ├── temporadas/                 # Dados organizados por temporada (ex: 22-23, 21-22)
│   │   ├── Ataque/                 # Estatísticas de ataque por temporada
│   │   ├── Defesa/                 # Estatísticas defensivas por temporada
│   │   ├── Passe/                  # Estatísticas de passes por temporada
│   │   ├── Goleiro/                # Estatísticas de goleiros por temporada
│   ├── temporadas_urls.csv         # Arquivo com URLs das temporadas para scraping
│── data_unificada/                 #Contém os arquivos CSV que foram limpos, organizados e unificados por categoria
│── champions_league_analysis.ipynb # Notebook principal
│── requirements.txt                # Lista de dependências do projeto
│── readme.md                       # Este arquivo README
```

## 📥 Instalação e Configuração
1. **Clone o repositório**
2. **Crie um ambiente virtual e instale as dependências:**
```bash
python -m venv venv
source venv/bin/activate  # Mac/Linux
venv\Scripts\activate     # Windows
pip install -r requirements.txt
```

3. **Abra o Jupyter Notebook:**
```bash
jupyter notebook
```

4. **Execute o notebook `champions_league_analysis.ipynb`** para iniciar a coleta de dados.

## 🏆 Funcionalidades
- **Captura Dinâmica de URLs das Temporadas:** Utiliza **Selenium** para navegar até a lista de temporadas e coletar os IDs automaticamente.
- **Web Scraping Híbrido:** Usa **Requests + BeautifulSoup** para obter a primeira página e **Selenium** para navegar nas páginas seguintes.
- **Extração Completa das Estatísticas dos Jogadores:** Gols, assistências, passes certos, entre outras métricas.
- **Salvamento Estruturado:** Os dados são armazenados na pasta `data/` em arquivos `.csv`, separados por temporada.

## 🔍 Recuperação e Análise de Dados

A segunda parte do projeto se concentra em extrair informações úteis a partir dos dados coletados. Algumas análises realizadas incluem:

### 📈 Análise de Tendências por Temporada
- Avaliação do desempenho médio de jogadores e equipes ao longo das últimas 10 temporadas.
- Identificação de padrões e evolução das estatísticas por posição (Ataque, Defesa, Passe e Goleiro).
- Uso da **mediana** em vez da média para garantir robustez nos dados.

### ⚖️ Comparação de Desempenho por Clube
- Criação de rankings de clubes usando duas abordagens:
  1. **Mediana da Nota Sofascore** - Reflete a avaliação geral da performance dos jogadores no time.
  2. **Mediana das Estatísticas (sem métricas percentuais e qualitativas)** - Considera apenas estatísticas objetivas como gols, passes e desarmes.
- Comparação visual entre os rankings baseados em nota e métricas objetivas.

### ⭐ Identificação de Jogadores-Chave
- Classificação dos jogadores com maior impacto em cada categoria (Ataque, Defesa, Passe e Goleiro).
- Excluindo métricas qualitativas para um ranking mais justo, focado apenas em estatísticas numéricas.
- Comparação entre os melhores jogadores por temporada.

### 🏆 Melhor Jogador e Melhor Time das Últimas 10 Temporadas
- Identificação do jogador mais impactante baseado na **mediana das métricas objetivas**.
- Ranking dos melhores times baseados em desempenho agregado das estatísticas (gols, passes, assistências, desarmes, etc.).

## ⚠️ Possíveis Erros e Soluções
1. **Problemas com Selenium?** Certifique-se de que o WebDriver está instalado corretamente:
   ```bash
   pip install --upgrade selenium webdriver-manager
   ```
2. **Bloqueio pelo Sofascore?** Tente alterar o `User-Agent` no código.
3. **Erro ao salvar os arquivos?** Verifique se a pasta `data/` existe antes de executar o scraping.
   ```python
   import os
   os.makedirs("data", exist_ok=True)
   ```
4. **Erro no WebDriver Manager?** Exclua a pasta do ChromeDriver e tente novamente.
   ```bash
   rm -rf ~/.wdm/drivers/chromedriver
   ```

## 📄 Licença
Este projeto é de uso educacional e não deve ser utilizado para fins comerciais. Todos os dados pertencem ao **[Sofascore](https://www.sofascore.com/)**.

---
