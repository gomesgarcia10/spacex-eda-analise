# 🚀 Análise Preditiva de Custos: O Caso de Reutilização do Falcon 9 (SpaceX)

## 🎯 O Problema de Negócio
A indústria aeroespacial tradicional operava com foguetes de uso único, tornando o custo de envio de cargas ao espaço proibitivo. A SpaceX mudou o paradigma ao tentar pousar e reutilizar o primeiro estágio do foguete Falcon 9, gerando uma economia estimada em US$ 50 milhões por voo. 

Este projeto analisa os dados históricos de lançamentos da SpaceX para identificar **quais fatores determinam o sucesso da recuperação do primeiro estágio**, uma informação vital para a precificação de seguros de cargas espaciais e previsão de custos operacionais.

## 💡 A Solução e Metodologia
Foi realizada uma Análise Exploratória de Dados (EDA) utilizando Python (Pandas, Matplotlib, Seaborn). O processo envolveu tratamento de valores nulos (Imputação de Dados) e o cruzamento multivariado de variáveis categóricas e temporais.

---

## 📈 Visualização dos Dados e Descobertas

### 1. A Curva de Aprendizado (Visão Temporal)
O primeiro passo foi analisar a taxa de sucesso ao longo dos anos. A análise revela que o sucesso inicial era nulo, mas a curva de aprendizado empírica gerou uma escalada rápida rumo à previsibilidade.

# Agrupando a taxa de sucesso por ano
sucesso_ano = df.groupby('Year')['Class'].mean() * 100
sns.lineplot(x=sucesso_ano.index, y=sucesso_ano.values, marker='o', color='#2980b9', linewidth=2.5)

*<img width="3000" height="1500" alt="grafico2_temporal" src="https://github.com/user-attachments/assets/d1749d6c-3705-46c2-becf-cde9b5778077" />*

### 2. O Risco Físico: Peso vs. Experiência
Ao cruzar a massa da carga (`PayloadMass`) com a experiência acumulada (`FlightNumber`), fica evidente que o peso deixou de ser um fator limitante. Com acúmulo de telemetria, a SpaceX passou a garantir o pouso até mesmo com cargas extremas.

*<img width="3000" height="1500" alt="grafico4_experiencia" src="https://github.com/user-attachments/assets/53be55b2-6193-4852-8722-6208b71b319c" />*

### 3. O Fator Órbita e Logística
Diferentes órbitas exigem perfis de queima de combustível distintos. A análise de sucesso por órbita e por base de lançamento (Launch Site) demonstra quais missões apresentam o menor risco atuarial para as seguradoras.

**Sucesso por Órbita:**
*<img width="3000" height="1500" alt="grafico1_orbita" src="https://github.com/user-attachments/assets/5a1cf26a-fb77-40b1-9008-e40b7455e97e" />*

**Sucesso por Base de Lançamento:**
*<img width="3000" height="1500" alt="grafico3_base" src="https://github.com/user-attachments/assets/76dd9015-6f2b-489a-91cd-059aa73b530c" />*

---

## 🚀 Reflexões Estratégicas e Desdobramentos

Os insights extraídos desta análise vão muito além da redução imediata de custos operacionais:

1. **O Fosso Tecnológico (Moat) Baseado em Dados:** A relação entre o aumento da taxa de sucesso e o número de voos prova que o maior ativo da SpaceX não é apenas o hardware, mas a **telemetria acumulada**. Concorrentes podem tentar aplicar engenharia reversa nos foguetes, mas não conseguem replicar instantaneamente o modelo preditivo construído com base em anos de falhas e acertos empíricos. 
2. **A Comoditização do Espaço e o Mercado Financeiro:** Ao provar que o pouso de um foguete pode se tornar previsível e seguro, o risco da operação deixa de ser uma "aposta científica" e passa a ser um cálculo atuarial. Essa previsibilidade rebaixa a barreira de risco para fundos de Venture Capital e Private Equity, transformando a exploração espacial em uma nova classe de investimentos.

## 🛠️ Tecnologias Utilizadas
* Python (Pandas, Seaborn, Matplotlib)
* Técnicas de Imputação de Dados e EDA (Google Colab)

---
**Autor:** Gabriel Gomes
