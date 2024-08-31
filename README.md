# Seleção de Atributos em Algoritmos de Aprendizado de Máquina

A seleção de atributos é uma etapa fundamental em aprendizado de máquina AM. Ela visa identificar e manter apenas as variáveis mais relevantes, melhorando a eficiência e a performance dos modelos. Neste repositório, aplicamos dois métodos de seleção de atributos: o **Low Variance** e o **Extra Tree Classifier**.

### 1. **Low Variance**
O método *Low Variance* elimina atributos cuja variância está abaixo de um determinado limiar. A premissa por trás dessa técnica é que variáveis com pouca variabilidade fornecem pouca ou nenhuma informação útil para a previsão, podendo ser descartadas sem impactar negativamente a acurácia do modelo.
Nesse teste o limiar atribuido foi de 0.05, alcancando os seguintes efeitos:

#### Resultados:
- **Acurácia**: 81.51%
- **Tempo de treinamento**: 2.00 segundos
- **Número de atributos finais**: 5

#### Vantagens:
- **Redução de dimensionalidade**: Retirar atributos irrelevantes resulta em modelos mais simples e rápidos de treinar.
- **Menor tempo de processamento**: Menos dados resultam em menos carga computacional.
  
#### Desvantagens:
- **Risco de perda de informação**: A eliminação de variáveis com baixa variância pode ocasionalmente remover informações sutis, mas importantes, para o modelo.

### 2. **Extra Tree Classifier**
O **Extra Tree Classifier** é uma variante do algoritmo *Random Forest* que classifica a importância de cada atributo durante a construção das árvores. Os atributos mais relevantes são mantidos, enquanto aqueles com pouca importância são descartados.
Nesse exemplo, foi utilizado o parametro de corte para seleção dos atributos foi de 0.07.

#### Resultados:
- **Acurácia**: 84.36%
- **Tempo de treinamento**: 3.72 segundos
- **Número de atributos finais**: 8

#### Vantagens:
- **Acurácia**: Seleção baseada na capacidade preditiva das variáveis, o que tende a manter a performance do modelo.
- **Interpretação**: Facilita a análise ao destacar os atributos que mais influenciam a previsão.

#### Desvantagens:
- **Complexidade**: Comparado a métodos simples como *Low Variance*, o *Extra Tree Classifier* é mais complexo e pode demandar mais tempo de processamento.

### 3. **Todos os Atributos**
Quando todos os atributos são utilizados no treinamento do modelo, sem nenhuma técnica de seleção aplicada:

#### Resultados:
- **Acurácia**: 85.40%
- **Tempo de treinamento**: 4.30 segundos
- **Número de atributos**: 14

## Comparação dos Resultados

- **Low Variance** apresentou a menor acurácia (81.51%), mas também teve o menor tempo de processamento (2.00 segundos), usando apenas 5 atributos.
- **Extra Tree Classifier** alcançou uma acurácia intermediária (84.36%) com um tempo de processamento moderado (3.72 segundos) e 8 atributos finais.
- **Todos os Atributos** forneceram a melhor acurácia (85.40%), mas com o maior tempo de processamento (4.30 segundos) e a maior quantidade de atributos (14).

## Conclusão
A seleção de atributos é uma técnica poderosa que pode melhorar tanto a acurácia quanto a eficiência de um modelo de aprendizado de máquina. O método *Low Variance* foi o mais rápido, mas com uma ligeira perda de precisão, enquanto o *Extra Tree Classifier* apresentou um bom equilíbrio entre acurácia e eficiência. O uso de todos os atributos resultou na melhor acurácia, mas com o maior tempo de processamento.

Escolher o método adequado depende do contexto do problema e das restrições de tempo e desempenho.
