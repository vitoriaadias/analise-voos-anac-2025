# Análise de voos: atrasos e cancelamentos em 2025

Análise descritiva dos dados da ANAC para comparar o desempenho de Gol, Azul e Latam Brasil em operações domésticas e internacionais.

## Objetivo

Identificar qual companhia apresentou as menores taxas de atrasos e cancelamentos em 2025, oferecendo informações para apoiar a escolha de uma companhia aérea.

## Dados utilizados

- Fonte: Voo Regular Ativo (VRA), da ANAC.
- Período: janeiro a dezembro de 2025.
- Recorte: 828.882 trechos de voo, entre realizados e cancelados.
- Companhias: Gol, Azul e Latam Brasil.
- Operações: domésticas e internacionais.

Os arquivos mensais são importados diretamente da ANAC pelo notebook.

[Fonte dos dados](https://siros.anac.gov.br/siros/registros/diversos/vra/2025/)

## Ferramentas

- Python
- pandas
- Matplotlib
- Jupyter Notebook

## Etapas da análise

1. Importação e seleção dos registros.
2. Conferência de duplicatas, informações ausentes, datas e horários.
3. Definição do período de análise.
4. Cálculo das diferenças entre horários reais e previstos.
5. Classificação dos atrasos e análise dos casos extremos.
6. Cálculo dos indicadores mensais e anuais.
7. Visualização dos resultados e apresentação das conclusões.

## Definição dos indicadores

- Cancelamentos: registros cancelados com partida prevista, divididos pelo total de registros com partida prevista.
- Atrasos: diferenças superiores a 15 minutos, avaliadas separadamente na partida e na chegada.
- As taxas de atraso consideram apenas voos realizados com os horários necessários para avaliar cada etapa.
- As taxas anuais são calculadas a partir dos totais do ano, e não pela média simples das taxas mensais.

As taxas são calculadas sobre os registros elegíveis de cada companhia e tipo de operação.

Voos sem horários suficientes permanecem no volume total, mas ficam fora da respectiva taxa de atraso.

## Qualidade dos dados

Foram conferidos registros duplicados, informações ausentes e a consistência das datas e dos horários.

Também foram identificados 65 registros com diferenças extremas entre horários previstos e reais. A comparação com e sem esses casos alterou as taxas anuais de atraso em até aproximadamente 0,013 ponto percentual, sem mudar a ordem das companhias. Os registros foram preservados conforme a fonte.

## Principais resultados

A Gol apresentou as menores taxas anuais nos três indicadores, tanto nas operações domésticas quanto nas internacionais.

### Operações domésticas

| Companhia | Cancelamentos | Atrasos na partida | Atrasos na chegada |
|---|---:|---:|---:|
| Gol | 1,07% | 12,89% | 11,49% |
| Azul | 1,45% | 13,80% | 13,98% |
| Latam Brasil | 1,70% | 17,40% | 16,22% |

### Operações internacionais

| Companhia | Cancelamentos | Atrasos na partida | Atrasos na chegada |
|---|---:|---:|---:|
| Gol | 0,73% | 12,33% | 12,20% |
| Azul | 1,65% | 21,09% | 26,55% |
| Latam Brasil | 0,80% | 22,77% | 21,63% |

### Variação mensal

- A Gol apresentou a menor taxa de cancelamento em oito meses de cada tipo de operação.
- Dezembro registrou as maiores taxas domésticas de atraso na chegada nas três companhias.
- Nas operações internacionais, a Gol apresentou a menor taxa de atraso na chegada em todos os meses.

## Conclusão e limitações

No recorte analisado de 2025, a Gol apresentou os menores percentuais anuais de cancelamento e atraso. Esse histórico pode ser considerado como um dos critérios na escolha de uma companhia aérea.

A interpretação dos resultados deve considerar que:

- A comparação não controla diferenças de rotas, aeroportos, horários ou condições operacionais.
- Os percentuais representam trechos de voo, não passageiros ou viagens completas com conexões.
- A ausência de horários limita a cobertura dos indicadores de atraso.
- A análise descreve os resultados observados, sem determinar suas causas.
- O desempenho de 2025 não garante resultados futuros.

## Arquivos do projeto

- [Notebook da análise](analise_voos_anac_2025.ipynb)
- [Apresentação em PDF](apresentacao.pdf)

## Como executar

Abra o arquivo `analise_voos_anac_2025.ipynb` no Jupyter Notebook e execute as células em sequência.
