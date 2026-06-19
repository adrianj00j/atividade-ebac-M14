# 📊 Previsão de Churn em Telecomunicações: Pré-Processamento Avançado

Este projeto foca na primeira e mais crucial etapa de qualquer modelo de Machine Learning: a **Limpeza e Preparação de Dados**. Utilizamos uma base de dados de clientes de uma empresa de telecomunicações para aplicar técnicas avançadas de tratamento e otimização utilizando a biblioteca Pandas em Python.

## 🚀 Principais Etapas Realizadas

1. **Tratamento Estratégico de Dados Faltantes (Missing Values)**
   - **Prevenção de Viés:** Exclusão técnica de linhas onde a *Variável Alvo* (`Churn`) estava nula, pois imputar a variável resposta "inventa" dados para o modelo aprender.
   - **Análise de Viabilidade:** Remoção de colunas criticamente comprometidas (como `PhoneService` com quase 60% de nulos), evitando picos artificiais que destruiriam a distribuição original.
   - **Imputação Robusta:** Uso da **Mediana** em vez da Média para variáveis financeiras (`Pagamento_Mensal`), garantindo que a imputação não seja distorcida por *outliers* (valores discrepantes).

2. **Padronização e Data Cleaning**
   - Correção de erros de digitação em categorias (ex: unificando 'F' e 'f' para 'Female', e 'dsl' para 'DSL').
   - Tradução integral do Dataset (nomes das colunas e valores internos) para o Português (PT-BR), padronizando a visualização e facilitando a extração de *insights*.

3. **Otimização Extrema de Memória (Downcasting & Categorização) 🧠**
   - *Este é o grande diferencial técnico deste projeto.* Ao trabalhar com Big Data, a gestão da memória RAM do servidor é fundamental. Neste projeto, demonstramos a redução massiva do peso do DataFrame através de:
   - **Categorização (`astype('category')`):** Variáveis em texto (`object`) consomem muita memória. Ao convertê-las para categorias, o Pandas armazena as strings uma única vez em um dicionário interno e usa inteiros minúsculos para representar as categorias nas linhas. Isso não só salva memória, mas também acelera cálculos computacionais no Pandas.
   - **Downcasting de Numéricos:** Colunas inteiras como `Idoso` (que armazenam apenas `0` e `1`) foram rebaixadas da precisão padrão `int64` (64 bits) para `int8` (8 bits), cortando o peso dessas colunas pela oitava parte sem perda de informação. 

## 🛠️ Tecnologias Utilizadas
- **Linguagem:** Python
- **Manipulação de Dados:** Pandas
- **Visualização:** Seaborn, Matplotlib
- **Ambiente:** Jupyter Notebook

## 💡 Como Executar
1. Clone este repositório.
2. Certifique-se de ter o arquivo `CHURN_TELECON_MOD08_TAREFA.csv` no mesmo diretório.
3. Execute o notebook `Profissao Cientista de Dados M14 Pratique (2).ipynb` para acompanhar passo a passo o processo de limpeza.
