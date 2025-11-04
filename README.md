# E-commerce Strategic Analysis

## Visão Geral

Este projeto implementa uma análise estratégica abrangente para e-commerce, dividida em dois módulos principais que fornecem insights valiosos para tomada de decisões de negócio:

1. **Clusterização Hierárquica de Clientes** - Segmentação RFM com Ward Linkage
2. **Market Basket Analysis** - Análise de associação usando algoritmo Apriori

## Estrutura do Projeto

```
ecommerce-strategic-analysis/
├── modulo1_clusterizacao/
│   ├── 1_clustering_analysis.ipynb      # Notebook de segmentação RFM
│   └── customer_segments.parquet       # Resultados em Parquet (otimizado)
├── modulo2_market_basket/
│   ├── 2_market_basket_analysis.ipynb  # Notebook de análise de cesta
│   ├── association_rules.parquet       # Regras de associação
│   └── frequent_itemsets.parquet       # Itemsets frequentes
├── data/
│   └── walmart.csv                      # Dataset Walmart (550K+ transações)
├── relatorios/
│   ├── relatorio_clusterizacao.html    # Relatório HTML Dark Mode - RFM
│   └── relatorio_market_basket.html    # Relatório HTML Dark Mode - MBA
├── .gitignore                           # Exclusões do Git
├── requirements.txt                     # Dependências Python
└── README.md                           # Documentação completa
```

## Módulo 1: Clusterização Hierárquica de Clientes

### Objetivo
Segmentar **5.891 clientes** com base em métricas RFM para identificar perfis comportamentais e criar estratégias personalizadas.

### Metodologia Técnica
- **Algoritmo**: Clusterização Hierárquica com Ward Linkage
- **Features**: RFM (Recência, Frequência, Monetário) + Ticket Médio
- **Normalização**: StandardScaler para equalização de escalas
- **Validação**: Silhouette Score (0.481 - Alta Qualidade)
- **Dataset**: 550.068 transações do Walmart

### Resultados Validados
- **4 Clusters identificados** com perfis distintos e acionáveis:
  - **VIP Premium (13%)**: Clientes de altíssimo valor (R$ 2.8M médio)
  - **Em Risco (17%)**: Inativos com alto valor histórico  
  - **Ativos Econômicos (20%)**: Frequentes e sensíveis a preço
  - **Regulares (50%)**: Base estável da empresa

### Estratégias Implementáveis
- **Programa VIP**: Atendimento premium e ofertas exclusivas
- **Reativação**: Campanhas urgentes para clientes em risco
- **Promoções**: Descontos por volume para econômicos
- **Cross-selling**: Expansão de categorias para regulares
- Personalização de ofertas baseada no perfil

## Módulo 2: Market Basket Analysis (Análise de Cesta)

### Objetivo  
Descobrir **1.093 regras de associação** entre produtos para otimizar cross-selling e layout de loja.

### Metodologia Técnica
- **Algoritmo**: Apriori otimizado para grandes datasets
- **Métricas**: Suporte, Confiança e Lift para validação
- **Filtros**: Confiança mínima 30% + Lift > 1.0
- **Otimização**: Top 50 produtos para performance
- **Encoding**: TransactionEncoder + Matriz binária

### Resultados Quantificados
- **1.093 regras** descobertas com alta qualidade
- **99.9% das regras** têm Lift > 1 (significativas)
- **Lift médio: 1.44** (excelente força associativa)
- **Top regra**: Lift 2.41 com 50.1% de confiança
- **147 regras premium** para implementação imediata

### Estratégias de Implementação
- **Sistema de Recomendação**: Automático baseado em regras
- **Bundling Inteligente**: Produtos com Lift > 2.0
- **Layout Otimizado**: Posicionamento por associações
- **Campanhas Dirigidas**: Email marketing personalizado

## Instalação e Execução

### Pré-requisitos
- **Python 3.8+** (recomendado: 3.9 ou superior)
- **8GB RAM** mínimo (dataset com 550K+ linhas)
- **Jupyter Lab** ou **VS Code** com extensão Python

### 1. Clone do Repositório
```bash
git clone https://github.com/caiothomasbandeira/ecommerce-strategic-analysis.git
cd ecommerce-strategic-analysis
```

### 2. Ambiente Virtual (Recomendado)
```bash
# Windows (PowerShell)
python -m venv .venv
.venv\Scripts\Activate.ps1

# macOS/Linux
python -m venv .venv
source .venv/bin/activate
```

### 3. Instalação das Dependências
```bash
pip install -r requirements.txt
```

### 4. Execução dos Notebooks

#### Opção A: Jupyter Lab (Recomendado para análise completa)
```bash
# Ativar ambiente virtual primeiro
jupyter lab

# Navegar até:
# - modulo1_clusterizacao/1_clustering_analysis.ipynb
# - modulo2_market_basket/2_market_basket_analysis.ipynb
```

**Vantagens do Jupyter Lab:**
- Interface web otimizada para data science
- Execução célula por célula com output inline
- Visualizações interativas integradas
- Ideal para exploração e análise de dados
- Suporte nativo a gráficos matplotlib/seaborn

#### Opção B: VS Code (Recomendado para desenvolvimento)
```bash
# Abrir no VS Code
code .

# Instalar extensões (se ainda não tiver):
# - Python (Microsoft)
# - Jupyter (Microsoft)
```

**Vantagens do VS Code:**
- Ambiente de desenvolvimento integrado completo
- IntelliSense e autocomplete avançado
- Debug integrado para notebooks
- Git integration nativo
- Extensões para produtividade
- Suporte a múltiplos kernels Python

### 5. Ordem de Execução
1. **Primeiro**: `modulo1_clusterizacao/1_clustering_analysis.ipynb`
2. **Segundo**: `modulo2_market_basket/2_market_basket_analysis.ipynb`

**Nota**: Cada notebook pode ser executado independentemente, mas recomenda-se seguir a ordem para melhor compreensão do fluxo analítico.

## Especificações Técnicas

### Stack Tecnológico
- **Python 3.8+** - Linguagem principal
- **pandas 1.5+** - Manipulação de dados
- **scikit-learn 1.2+** - Machine Learning
- **matplotlib/seaborn** - Visualização
- **mlxtend** - Algoritmos de associação
- **scipy** - Clustering hierárquico
- **pyarrow** - Formato Parquet

### Formato de Dados
- **Entrada**: CSV (550MB dataset Walmart)
- **Saída**: Parquet (formato otimizado, 50% menor)
- **Relatórios**: HTML com tema dark mode responsivo

### Performance
- **Tempo médio de execução**: 10-15 minutos por notebook
- **Memória utilizada**: 4-6GB durante processamento
- **Otimizações**: Sampling inteligente para Market Basket

## Resultados Esperados

### Arquivos Gerados
```
modulo1_clusterizacao/
└── customer_segments.parquet        # 5.891 clientes segmentados

modulo2_market_basket/
├── association_rules.parquet        # 1.093 regras de associação
└── frequent_itemsets.parquet        # Itemsets frequentes

relatorios/
├── relatorio_clusterizacao.html     # Relatório interativo RFM
└── relatorio_market_basket.html     # Relatório interativo MBA
```

### Métricas de Qualidade
- **Clustering**: Silhouette Score > 0.48 (Muito Bom)
- **Market Basket**: Lift médio 1.44 (Excelente)
- **Cobertura**: 99.9% das regras são significativas

## Aplicações de Negócio

### Segmentação RFM (Módulo 1)
- **CRM**: Personalização de campanhas
- **Pricing**: Estratégias diferenciadas por cluster
- **Atendimento**: Priorização por valor do cliente
- **Retenção**: Identificação de clientes em risco

### Market Basket (Módulo 2)  
- **E-commerce**: Sistema de recomendação
- **Varejo**: Otimização de layout físico
- **Marketing**: Campanhas de cross-selling
- **Estoque**: Planejamento de compras casadas

## Configuração de Desenvolvimento

### Jupyter Lab Setup
```bash
# Configurações recomendadas
jupyter lab --ip=0.0.0.0 --port=8888 --no-browser --allow-root
```

### VS Code Setup
```json
// .vscode/settings.json
{
    "python.defaultInterpreterPath": "./.venv/Scripts/python.exe",
    "jupyter.jupyterServerType": "local",
    "python.terminal.activateEnvironment": true
}
```

## Suporte e Contribuição

### Troubleshooting
- **Erro de memória**: Reduzir sample_size nos notebooks
- **Bibliotecas missing**: Verificar requirements.txt
- **Kernel crash**: Reduzir parâmetros min_support no Apriori

### Contribuições
1. Fork o repositório
2. Crie uma feature branch
3. Commit suas mudanças
4. Push para a branch
5. Abra um Pull Request

## Contato
- **Autor**: Caio Thomas Bandeira
- **LinkedIn**: [linkedin.com/in/caiothomasbandeira](https://linkedin.com/in/caiothomasbandeira)
- **GitHub**: [github.com/caiothomasbandeira](https://github.com/caiothomasbandeira)

---

**Nota**: Este projeto utiliza dados reais do Walmart para demonstração. Os insights gerados são baseados em análises estatísticas rigorosas e podem ser aplicados diretamente em ambientes de produção.
