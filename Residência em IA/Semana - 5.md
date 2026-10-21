Resumindo que já foi feito nas semanas anteriores culminando nas atividades relacionados a essa semana, primeiramente escolhi o meu tema com base no que foi pesquisado sobre temas relevantes e interessantes dentro de conferências, com isso, escolhi **Análise de Generalização e Explicabilidade em Aprendizado por Reforço**, porque entender sobre como redes neurais aprendem é extremamente relevante e promisso, mas é um pouco amplo demais, com isso, foquei em **Aprendizado Por Reforço**, porque é um tema que eu gosto e amplamente explorado para diversas áreas atualmente.

Em seguida mapiei e li artigos fundacionais sobre a área de RL, de 1964 - 2018. 

Depois disso decidi fazer um mapeamento parecido para a área de Redes Neurais, em que vou estudar sobre os fundamentos de uma MLP e em seguida partir para arquiteturas importantes, como CNNs, Autoencoders, LSTM e Transformers, todas essas utilizam RL de alguma maneira em aplicações.

Na semana passada fiz a leitura de artigos fundacionais sobre a área de redes neurais, voltado para os temas "neurônio", "perceptron", "limitações das perceptrons", "adaline", "backpropagation", "multi-layer-perceptron" e um artigo sobre otimizadores, como o "adam" que era algo que senti que faltava no meu conhecimento.

Seguindo para essa semana vou realizar a leitura sobre artigos de arquiteturas fundamentais, como **CNNs**, **Resnet**, **LSTM**, **Autoencoders**, **Transformers** 

# Artigos


### **[ImageNet Classification with Deep Convolutional Neural Networks (AlexNet)](https://drive.google.com/file/d/1wtin8YH0LCuDeP64yd05Lj0Kn8JnhjLY/view?usp=sharing)** — (Alex Krizhevsky, Ilya Sutskever & Geoffrey Hinton, 2012)

No artigo acima foi feito um estudo sobre como poderia utilizar redes neurais para conseguir vencer uma competição utilizando o dataset do **ImageNet**, a arquitetura utilizada foi de Redes Convolutionais. 

A rede foi treinada com um dataset de 1.2 milhões de imagens de treino, em que foram utilizadas 2 GPUs com 2 GB de Vram para conseguir guardar todos os parâmetros do modelo que foi treinado de forma distribuida com 5 canamadas convolucionais e 3 fully conected, com uma softmax para conseguir atribuir as 1000 classes contidas dentro do dataset.

Dentro do treinamento foi utilizado o **ReLU** como função de ativação, além de **Local norm Normalization** e para impedir o overfitting das últimas camâdas foi utilizado **Data Augmentation** e **Dropout**, que permitiu com que essas câmadas não tenham tanto overfitting.


### **[Deep Residual Learning for Image Recognition (ResNet)](https://drive.google.com/file/d/1Gb2RBsMMGVlUpY2NYpgejTCwMP21_6UR/view?usp=sharing)** — (Kaiming He 2015/2016)

Foi proposta uma melhoria para a arquitetura de CNNs classicas aplicadas dentro da competição do ImageNet, na qual, foi adicionada uma operação **Residual** que ajuda a mitigar o desaparecimento do gradiente, devido a grande quantidade de câmadas dentro de uma rede Neural, esse desaparece quando nós temos uma grande quantidade de ruído na rede e muitas camadas, tornando dificil a propagação de erro para as primeiras camâdas dentro da rede, porque a derivada de x faz com que fique "1" residual no gradiente e com isso as multiplicações são de números "> 1", portanto, não diminuem gradativamente, como eram se "< 1". E facilita o aprendizado dos neurônios, que somente precisam aprender a representar a diferença entre a entrada e a saída, não exatamente uma função ótima de saída (F(x) = H(x) + x).

A conexão residual somente soma o valor do input ao output de um neurônio em cada um deles dentro da rede. Dentro do artigo é apresentado essa nova mudança e além disso é provado que com um aumento de muitas câmadas ainda é possível


### [**Long Short-Term Memory**](https://drive.google.com/file/d/1wMJieeCzT8HIv5tMvRkzozd48HT6UQbe/view?usp=sharing) — (Sepp Hochreiter & Jürgen Schmidhuber, 1997)

O artigo tenta melhorar o gap da literatura sobre **vanishing gradients** e **exploding_gradients** dentro da literatura de redes neurais, na qual, devido ao backpropagation e o aumento do tamanho das redes, temos momentos em que o aprendizado não é propagado corretamente para as células dentro de uma rede neural. 

Para corrigir esse problema o artigo utiliza redes Recorrentes (RNNs) que processam somente um input x por vez e com base nesse input, armazenam dentro de uma memôria local o quanto desse input deve ser guardado nessa memôria, o quanto deve ser esquecido (adicionado depois de 1997) e o quanto deve ser utilizado como output para uma nova iteração dentro da memôria da rede h(t) 

Isso é chamada de Celula de Memôria e é acoplada junto com camâdas de neurônios FF para formar uma rede LSTM.


### **[Reducing the Dimensionality of Data with Neural Networks (autoencoders)](https://drive.google.com/file/d/11cjXodqAmZCB2lz2KUZEM3NTm1LPMBai/view?usp=sharing)** — (Geoffrey Hinton & Ruslan Salakhutdinov, 2006)

Pulei por enquanto devido a falta de tempo, além de que isso serviria mais como curiosidade do que utiliza de real para Generalização em RL. 

### **Attention Is All You Need (Transformer)** — (Ashish Vaswani, 2017)


O artigo propõe uma nova arquitetura batizada de **Transformers** que promete conseguir identificar e entender sequências longas para realizar tarefas de modelagem de linguagem e de tradução, utilizando somente uma MLP simples e atenção para que a MLP tenha conhecimento das relações entre as palavras, dentro disso, é utilizada uma arquitetura **Encoder->Decoder**, em que a primeira representa a linguagem com embeddings e a outra busca utilizar essa representação para conseguir gerar resultados.

Encode - Utilizamos Positional encoding, um sinal adicionado ao embedding para que ele tenha noção de posição dentro da frase, em seguida é calculada uma **Scaled Dot Product Attention**, em que o embedding tem uma noção de correlação entre as palavras dentro de uma frase. Utilizamos uma LayerNorm com soma Residual depois de cada camâda para melhorar o aprendizado e diminuir problemas dos gradientes. Além disso, utilizamos uma FF para conseguir extrair correlações não lineares.

Decoder - Arquitetura utilizada para a previsão do próximo token dentro de uma frase, em que usamos PE, MHMA (incluimos uma máscara por ser decoder) e em seguida calculamos **Cross Attention** utilizando K e V do Encoder para entender a relação entre as palavras, depois passamos por uma **Feed Foward** novamente, realizamos a projeção linear final para transformar os embeddings em **logits** e depois utilizamos uma softmax para achar a palavra mais próvavel e utilizar ela para escolher o próximo token, comparando com o resultado do tokenizador.



# Pesquisa e Mapeamento de Frameworks 

Realizarei uma pesquisa sobre frameworks que serão úteis dentro da área e que já foram mencionados em artigos anteriormente. Nisso irei incluir também frameworks relacionados com a generalização e explicabilidade de modelos de Machine Learning.

# Modelagem de ambientes para treinamento de política

**Gymnasium** - 

**Mujoco** - 

**PyTorch** - 

**Reprodutibilidade do ambiente** - 

**Comparação com algoritmos simples** -

**Atari Learning Environment** - 

**Modelagem com Recompensas Esparsas** - 

**CleanRL** - 

**Stable-Baselines3** -

**Weights E Bias** -

**Hydra** - 

# Análise de Generalização 

**ProcGen** - 

**CARL** -


# Análise de Explicabilidade

**Captum** - 

**TransformerLens** - 



# Próximas Semanas

Para a próxima semana, gostaria de estudar cada um dos frameworks marcados como interessantes de modo que eu entenda (Para que servem? Até onde vão? Como utilizar?).

Além de testar dentro de uma aplicação simples como eu poderia realizar uma análise de generalização e explicabilidade em Redes Neurais.