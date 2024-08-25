## Treinamento de Rede Neural para Resolução de EDOs - Problema 1 de Lagaris

Este código demonstra o treinamento de uma rede neural para resolver o Problema 1 de Lagaris, uma equação diferencial ordinária (EDO) de primeira ordem com condições de contorno de Dirichlet. A rede neural é treinada usando a descida de gradiente em mini-lotes e o código inclui:

* **Definição do Problema:** Define a EDO e a solução analítica para comparação.
* **Rede Neural:** Cria a rede neural com uma camada oculta com 'numHiddenNodes' nós.
* **Função de Perda:** Define a função de perda para medir a diferença entre a saída da rede e a solução da EDO.
* **Treinamento:** Implementa o treinamento da rede usando a descida de gradiente em mini-lotes, iterando sobre os dados de treinamento em lotes.
* **Plotagem:** Plota a saída da rede neural treinada em comparação com a solução analítica da EDO.
* **Cálculo do Custo:** Calcula e plota o custo da rede durante o treinamento.

### Código:

O código é dividido em várias classes e funções:

* **`DataSet`:**  Classe que gera dados de treinamento igualmente espaçados para a entrada da rede neural (`x`).
* **`Fitter`:** Classe que define a rede neural com duas camadas totalmente conectadas (`fc1` e `fc2`).
* **`plotNetwork`:** Função que plota a saída da rede neural em comparação com a solução analítica.
* **`trialFunc`:** Função que representa a solução de teste para a EDO.
* **`dTrialFunc`:** Função que calcula a derivada da solução de teste.
* **`diffEq`:** Função que calcula o valor da EDO para um dado ponto `x`.
* **`solution`:** Função que retorna a solução analítica da EDO.
* **`train`:** Função que treina a rede neural usando a descida de gradiente em mini-lotes.

### Uso:

1. **Configurar os parâmetros:**
    * `xRange`: Define o intervalo de entrada `x`.
    * `numSamples`: Define o número de amostras de treinamento.
    * `batchSize`: Define o tamanho do lote para o treinamento.
    * `paramUpdates`: Define o número de iterações de treinamento.
    * `numHiddenNodes`: Define o número de nós na camada oculta da rede neural.
    * `numEpochs`: Define o número de épocas para cada iteração de treinamento.
    * `totalEpochs`: Define o número total de épocas para o treinamento.

2. **Criar a rede neural (`network`) e o conjunto de dados de treinamento (`train_set`)**.

3. **Treinar a rede neural usando a função `train`.**

4. **Plotar a saída da rede neural treinada usando a função `plotNetwork`.**

5. **Observar o custo da rede neural durante o treinamento.**

## Referências

Código: https://github.com/Isaac-Somerville/Neural-Networks-for-Solving-Differential-Equations/tree/main?tab=readme-ov-file
* **BAELDUNG.** _Differences Between Gradient, Stochastic and Mini Batch Gradient Descent_. 2023. &lt;https://www.baeldung.com/cs/gradient-stochastic-and-mini-batch&gt;. Acessado em: 13 ago. 2024.
* **HAYKIN, S.** _Redes Neurais - Princípios e práticas_. [S.l.]: Bookman, 2007.
* **LAGARIS, I. E.; LIKAS, A.; FOTIADIS, D. I.** _Artificial neural networks for solving ordinary and partial differential equations_. IEEE Transactions on Neural Networks, 1998.
  

### Observações:

* O código pode ser modificado para resolver outras EDOs alterando as funções `trialFunc`, `dTrialFunc` e `diffEq`.
* Os parâmetros de treinamento podem ser ajustados para otimizar o desempenho da rede.
* O código usa a biblioteca `torch.autograd` para calcular os gradientes da saída da rede em relação aos valores de entrada.
* A biblioteca `torch.nn` é usada para definir a rede neural, a função de perda e o otimizador.
* A biblioteca `matplotlib` é usada para plotar os resultados.

### Potenciais Melhorias:

* Implementar outras técnicas de otimização, como Adam ou RMSprop.
* Investigar o impacto do tamanho do lote, da taxa de aprendizado e do número de épocas no desempenho da rede.
* Avaliar o desempenho da rede em conjuntos de dados de teste separados.
