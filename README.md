# E-commerce Strategic Analysis

## Visão Geral

Este projeto implementa uma análise estratégica abrangente para e-commerce, dividida em dois módulos principais que fornecem insights valiosos para tomada de decisões de negócio:

1. **Clusterização Hierárquica de Clientes** - Segmentação baseada em métricas RFM
2. **Market Basket Analysis** - Análise de associação de produtos usando algoritmo Apriori

## Estrutura do Projeto

```
ecommerce-strategic-analysis/
├── modulo1_clusterizacao/
│   └── 1_clustering_analysis.ipynb    # Análise de segmentação de clientes
├── modulo2_market_basket/
│   └── 2_market_basket_analysis.ipynb # Análise de associação de produtos  
├── data/
│   ├── walmart.csv                    # Dataset principal (gerado automaticamente)
│   └── association_rules.csv          # Regras de associação descobertas
├── relatorios/
│   ├── relatorio_clusterizacao.html   # Relatório HTML - Clusterização
│   ├── relatorio_market_basket.html   # Relatório HTML - Market Basket
│   ├── dados_clusterizacao.json       # Dados estruturados - Clusterização
│   └── dados_market_basket.json       # Dados estruturados - Market Basket
├── requirements.txt                   # Dependências do projeto
└── README.md                         # Documentação principal
```

## Módulo 1: Clusterização de Clientes

### Objetivo
Segmentar clientes com base nas métricas RFM (Recency, Frequency, Monetary) para identificar diferentes perfis de comportamento de compra.

### Metodologia
- **Algoritmo**: Clusterização Hierárquica com linkage Ward
- **Métricas**: RFM (Recência, Frequência, Valor Monetário)
- **Validação**: Análise de Silhouette e método do cotovelo
- **Normalização**: StandardScaler para padronização dos dados

### Resultados
- **4 Clusters identificados** com perfis distintos:
  - **Cluster 1**: Clientes VIP (alta frequência, alto valor)
  - **Cluster 2**: Clientes em Risco (baixa recência)
  - **Cluster 3**: Clientes Ocasionais (média frequência)
  - **Cluster 4**: Clientes Regulares (comportamento estável)

### Estratégias Recomendadas
- Programas VIP para clientes de alto valor
- Campanhas de reativação para clientes em risco
- Promoções direcionadas por segmento
- Personalização de ofertas baseada no perfil

## Módulo 2: Market Basket Analysis

### Objetivo
Descobrir padrões de associação entre produtos para identificar oportunidades de cross-selling e otimização de layout.

### Metodologia
- **Algoritmo**: Apriori para mineração de regras de associação
- **Métricas**: Suporte, Confiança e Lift
- **Filtros**: Suporte mínimo 0.01, Confiança mínima 0.5
- **Encoding**: TransactionEncoder para preparação dos dados

### Resultados
- **Regras de associação descobertas** com alto poder preditivo
- **Top produtos** mais frequentemente comprados juntos
- **Oportunidades de bundling** identificadas
- **Padrões de compra** por categoria de produto

### Estratégias Recomendadas
- Sistema de recomendações automático
- Posicionamento estratégico de produtos
- Promoções casadas baseadas em associações
- Otimização de estoque correlacionado

## Instalação e Configuração

### 1. Clone o Repositório
```bash
git clone <url-do-repositorio>
cd ecommerce-strategic-analysis
```

### 2. Crie e Ative o Ambiente Virtual
```bash
# Criar ambiente virtual
python -m venv venv

# Ativar no Windows
venv\Scripts\activate

# Ativar no Linux/Mac
source venv/bin/activate
```

### 3. Instale as Dependências
```bash
pip install -r requirements.txt
```

### 4. Inicie o Jupyter Lab
```bash
jupyter lab
```

### 5. Execute os Notebooks
1. **Primeiro**: `modulo1_clusterizacao/1_clustering_analysis.ipynb`
2. **Segundo**: `modulo2_market_basket/2_market_basket_analysis.ipynb`

## Dependências Principais

- **pandas** (>=1.5.0) - Manipulação de dados
- **numpy** (>=1.24.0) - Computação numérica  
- **scikit-learn** (>=1.3.0) - Algoritmos de machine learning
- **mlxtend** (>=0.22.0) - Algoritmo Apriori
- **matplotlib** (>=3.6.0) - Visualizações básicas
- **seaborn** (>=0.12.0) - Visualizações estatísticas
- **scipy** (>=1.10.0) - Funções científicas
- **jupyterlab** (>=4.0.0) - Ambiente de desenvolvimento
- **plotly** (>=5.15.0) - Visualizações interativas

## Relatórios Gerados

### Relatórios HTML Interativos
Ambos os notebooks geram relatórios HTML completos e profissionais:
- **Métricas principais** em cards visuais
- **Tabelas detalhadas** com resultados
- **Análise interpretativa** de cada insight
- **Recomendações estratégicas** práticas
- **Design responsivo** para visualização em qualquer dispositivo

### Dados Estruturados JSON
Para integração com outros sistemas:
- Métricas quantitativas
- Resultados de clusters/regras
- Timestamps de execução
- Metadados da análise

## Dataset

O projeto utiliza um dataset simulado do Walmart com:
- **550.000+ transações** e-commerce
- **5.891 clientes únicos**  
- **3.631 produtos únicos**
- Período: Janeiro 2023 a Dezembro 2023
- Dados gerados automaticamente nos notebooks

## Resultados Esperados

### Métricas de Negócio
- **Segmentação precisa** de clientes
- **ROI melhorado** em campanhas de marketing
- **Aumento nas vendas cruzadas** 
- **Otimização de estoque** baseada em associações
- **Personalização de experiência** do cliente

### KPIs Mensuráveis
- Taxa de conversão por segmento
- Valor médio do carrinho
- Frequência de compra
- Lifetime Value (LTV) por cluster
- Efetividade das recomendações

## Contribuição

Este projeto foi desenvolvido seguindo as melhores práticas de:
- **Código limpo** e bem documentado
- **Análise estatística rigorosa**
- **Visualizações profissionais**
- **Relatórios executivos automáticos**
- **Estrutura modular** e reutilizável

## Licença

Projeto desenvolvido para fins acadêmicos e profissionais.
