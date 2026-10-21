Resumindo que já foi feito nas semanas anteriores culminando nas atividades relacionados a essa semana, primeiramente escolhi o meu tema com base no que foi pesquisado sobre temas relevantes e interessantes dentro de conferências, com isso, escolhi **Análise de Generalização em Aprendizado por Reforço**, porque entender sobre como redes neurais aprendem é extremamente relevante e promisso, mas é um pouco amplo demais, com isso, foquei em **Aprendizado Por Reforço**, porque é um tema que eu gosto e amplamente explorado para diversas áreas atualmente.

Em seguida mapiei e li artigos fundacionais sobre a área. De 1964 - 2018. Depois disso decidi fazer um mapeamento parecido para a área de Redes Neurais, em que vou estudar sobre os fundamentos de uma MLP e em seguida partir para arquiteturas importantes, como CNNs, Autoencoders, LSTM e Transformers, todas essas utilizam RL de alguma maneira em aplicações.

Com isso essa semana decidi ler 7 artigos fundacionais sobre a área de RL durante essa semana.

# Artigos Fundacionais/Livros da área de Redes Neurais 

# Fundamentos da MLP

### [A Logical Calculus of the Ideas Immanent in Nervous Activity](https://drive.google.com/file/d/1zF_G3tolWDgE1S_hW8ch-5pHqk1mg1lW/view?usp=sharing) - (Warren McCulloch & Walter Pitts, 1943)

O artigo se propõe a modelar por meio de **lógica proposicional** o comportamento de um neurônio, ou seja, validando as suas ativações, inativações, excitações que conseguem ativar neurônios subsequentes, além de uma ideia de que com a ativação de um neurônio conseguimos alterar ativações futuras e com isso armazenar o conhecimento adiquirido por meio daquela ativação. Modelando por meio de proposições lógicas um neurônio.

Esse neurônio abstrato teria entradas bool e essa entradas poderiam ser somadas impedindo a ativação ou causando a ativação de um neurônio, se elas ultrapassasem um certo threshold.

Diante disso, foram definidos 10 teoremas que seriam utilizados para conseguir provar essa ideia, além disso, isso foi modelado no formato de **circuitos lógicos**, e foi mencionado no artigo que podemos reunir os conceitos de um fluxo completo de uma sinapse dentro de um conceito de esfera, que contém ativações e inibições.


### **[The Perceptron: A Probabilistic Model for Information Storage and Organization in the Brain](https://drive.google.com/file/d/1cJrUuWOyhnbs_RAq2gU9jqN6mOP1LlTi/view?usp=sharing)** — (Frank Rosenblatt, 1958)

Esse artigo é simplesmente genial porque o autor previu o que a IA iria conseguir fazer e suas limitações, por meio de uma modelagem simples utilizando somente circuitos lógicos e operações com binários 0 e 1. Utilizando por meio disso a lógica de um neurônio definida no artigo acima. Em que pega 3 sistemas, **S-Sistems**, **A-Sistems** e **R-Sistems** e utilizando esses três sistemas bem definidos contruí o fluxo de uma perceptron.

Em que define o S como o input de binários que será feito dentro da **Perceptron** uma unidade probabilistica que é capaz de conseguir generalizar sobre dados sem que precise armazenar todos eles, esses sistemas s se conectam com sistemas A, que representam o neurônio de McCulloch, em que recebe entradas e verifica se ela passa de um threashold, definindo se o neurônio deve ser ativo ou não deve ser ativo, além de ter 2 portais lógicos dentro dos sistemas A, um deles representa ativação por estimulos e outro representa a inibição por estimulos. A soma desses resultados que são passados é passado para os sistemas R que em seguida irão decodificar o resultado dos A e verificar se devem estimular ou inibir comportamentes, ou seja, se o resultado deve ser 0 ou 1, o maior resultado na soma dita isso, e depois disso irão "propagar os erros".

Seguindo essa ideia o resultado da perceptron então é guiado por quais camadas foram atividadas em determinado momento. Com isso o artigo estabelece um calculo de probabilidade de ativação de camadas com base em certos critérios.

### **[Perceptrons](https://archive.org/details/perceptronsintro00mins/page/n3/mode/2up)** — (Marvin Minsky & Seymour Papert, 1969)

Dentro desse livro é provado matemáticamente muitas formulações em cima das **Perceptrons** de Roseblatt, em que primeiro é provado matemáticamente a convergência das redes, em seguida é provado geometricamente, explorado mais a fundo com base em no erro descrito e como ele afeta a rede.

Dois problemas fundamentais observados dentro das Perceptrons foram de que elas não conseguiam ver a correlação entre os dados de entrada, sendo impossível computar imagens por exemplo. Além disso somente tem uma única camada, com isso conseguem computar somente variáveis de primeira ordem.
### **[Adaptive Switching Circuits](https://drive.google.com/file/d/10rB9g6pCiaqgn4RErGzG5pKss9Qej8Kw/view?usp=sharing)** — (Bernard Widrow & Marcian Hoff, 1960)

Define uma arquitetura para a resolução do problema de aprendizado generalizado, onde um máquina poderia aprender com base em exemplos a como resolver determinado problema, sem ser treinada diretamente para ele, esse formato é modelado em cima de circuitos parecidos com if e else gerados por multiplas variáveis em tabelas verdade.

Com isso foi criado um computador chamado de ADALINE, que seria possível atualizar uma quantidade fixa de pesos e conseguir prever um valor positivo ou negativo, com base na somatória desses pesos. Em que tinhamos as entradas 1 e -1, que eram multiplicadas pelos pesos, esses pesos eram então somados e geravam um valor e, que era verificado se era maior ou menor do que 0. Com base nisso tinhamos um resultado 1 ou -1. 

em seguida era calculado o erro com base nesse valor "e" junto com um label passado, dividindo ele pelos pesos e atualizando a.


### **[Learning Representations by Back-propagating Errors](https://drive.google.com/file/d/1-QPGh3tRryxGfxZd6LtvbFWkTXB4yi-5/view?usp=sharing)** — (David Rumelhart, Geoffrey Hinton & Ronald Williams, 1986) 

Dentro dessa dissertation sobre backpropagation é definido com mais clareza os avanços feitos até esse momento, em que o neurônio e a perceptron são bem mais definidos.

O neurônio possui como entrada as entradas anteriores multiplicadas pelo seu peso e somadas, depois disso são passadas por uma função de ativação, sigmoid para conseguir deixar os dados não lineares é definido juntamente com isso um valor de Erro que é calculado como uma **MSE**, que retropropaga esse erro por meio da regra da cadeia para conseguir otimizar o gradiente em relaçao aos pesos de cada neurônio, decompondo a cadeia de operações até chegar aos pesos de um neurônio.


### **[Multilayer Feedforward Networks are Universal Approximators](https://drive.google.com/file/d/1Rvv7DrRMHg_FjFs48uyTDghPlp39jCBY/view?usp=sharing)** — (Kurt Hornik, Maxwell Stinchcombe & Halbert White, 1989)

Esse artigo foi escrito com o crescimento das MLPs, que começaram a mostrar bastante sucesso na resolução de diversos problemas de aproximação de funções, com isso, o artigo busca definir matemáticamente com diversas definições e teoremas como nos podemos definir que redes neurais são sim aproximadores universais de funções e que podemos utilizar essas redes para tarefas das mais diversas funções. Dentro do artigo foi concluído que é possível. 

E o fato de ela não convergir vem da falta de modelagem do problema, devido a pouca quantidade de dados ou algum outro problema de modelagem.



### **[Adam: A Method for Stochastic Optimization](https://drive.google.com/file/d/1mJIU4MHahP6uFrvyn0dpKzmu2lxshkjK/view?usp=sharing)** — (Diederik Kingma & Jimmy Ba, 2014)

Nesse paper foi definido um algoritmo de otimização chamado de **Adam**, que é utilizado dentro de redes neurais para conseguir melhorar a atualização de pesos rumo ao gradiente, adicionando o fator de momentum, que faz com que os pesos converter mais rapidamente para um otimo, visto que valorizam o sinal e a magnitude do gradiente. Porque são criados dois vetores m e v que codificam isso.

No caso do m ele codifica uma média do caminho que o gradiente está seguindo enquanto o v códifica a magnitude do valor do gradiente sem levar em conta o sinal dele.


# Proximos passos

## Leitura de artigos sobre arquiteturas fundamentais de Redes Neurais. Todas essas são treinadas com reforço.

## [ImageNet Classification with Deep Convolutional Neural Networks (AlexNet)](https://drive.google.com/file/d/1wtin8YH0LCuDeP64yd05Lj0Kn8JnhjLY/view?usp=sharing)** (Alex Krizhevsky, Ilya Sutskever & Geoffrey Hinton, 2012)

### **[Deep Residual Learning for Image Recognition (ResNet)](https://drive.google.com/file/d/1Gb2RBsMMGVlUpY2NYpgejTCwMP21_6UR/view?usp=sharing)** (Kaiming He 2015/2016)

### **[Reducing the Dimensionality of Data with Neural Networks (autoencoders)](https://drive.google.com/file/d/11cjXodqAmZCB2lz2KUZEM3NTm1LPMBai/view?usp=sharing)** (Geoffrey Hinton & Ruslan Salakhutdinov, 2006)

### [**Long Short-Term Memory**](https://drive.google.com/file/d/1wMJieeCzT8HIv5tMvRkzozd48HT6UQbe/view?usp=sharing)  (Sepp Hochreiter & Jürgen Schmidhuber, 1997)

### [**Attention Is All You Need](https://drive.google.com/file/d/1EETeYWKsI3Rbs6FhLmo1YLu_RnQVIEGg/view?usp=sharing) 
(Transformer)** — (Ashish Vaswani, 2017)


## Mapeamento de frameworks de aprendizado por reforço encontrados nos artigos.

### Aprendizado por reforço.

### Generalização.