
Dado que não foi possível avançar tanto quanto o esperado na semana passada, essa semana foi atribuído uma quantidade maior de coisas a serem feitas ao longo da semana.

# Artigos - RL

# [Soft Actor-Critic:  Off-Policy Maximum Entropy Deep Reinforcement  Learning with a Stochastic Actor](https://drive.google.com/file/d/1kaPzb0mcTQdu5Fcrvsr6NLHFEBWgZeWl/view?usp=drive_link) (2018)

Dentro desse artigo foram encontrados outros artigos para seguir com o remapeamento da área.

Seguindo para a ideia do artigo em si, seria principalmente resolver os problemas do PPO, com relação a eficiência de amostras e a dependência de conseguir tunar os hyperparâmetros, sendo o algoritmo muito sensível para esse tuning. Com isso é proposto o SAC que tenta resolver os problemas com um algoritmo **actor-critic** off-policy que utiliza replay buffer para garantir a eficiência de dados, além de 3 redes, 1 para otimizar o valor de *V(st)* outra para *Q(at,st)* e uma última para a política dele. Com isso são adicionados dentro da loss de cada um deles um calculo envolvendo a entropia, para garantir maior exploração do ambiente e otimizamos o valor de cada um.

A rede da política tem uma diferença, porque a otimização é feita em cima da divergência entre a política atual e uma política ótima, assim como é feito durante o calculo da função de valor no Q-Learning, em que ele pega um valor ideal pela ação que maximiza esse valor. Nesse caso nós comparamos uma política teórica ótima que segue uma distribuição exponencial com a nossa política que necessariamente está dentro de um espaço Gaussiano, depois disso é utilizada uma técnica de **Reparâmetrização**, amostrando uma ação que possa ser usada para a otimização da política em função de um "e", que permite o calculo da loss para nossa rede de otimização de política.


# [Deep Reinforcement Learning from Human Preferences](https://drive.google.com/file/d/1n3Qvne6u_SLEhkyqoxNLXQ_L5-IceXbr/view?usp=drive_link) (2017)


O objeto de estudo do artigo é o Deep Reinforcement Learning, verificando se podemos utilizar a intenção do usuário para conseguir treinar um algoritmo utilizando aprendizado por reforço. Isso é feito ao construir a função de recompensa do modelo com base na intenção do usuário.

Para isso utilizamos uma rede treinada com aprendizado supervisionado, em que o alvo da rede seria a preferência humana de comportamento de certos agentes dentro do ambiente do **Atari** e do **Mujoco** com base em um vídeo de seu comportamento. Com base nesse vídeo a pessoa teria que escolher qual entre os dois vídeos qual o melhor resultado para o agente, dando um resultado de (1.0, 0.0) ou (0.5, 0.5) ou (0.0, 1.0) ou se não concluível (pula o episódio). 

Com base nesse resultado a rede Supervisionada usa isso como alvo a ser calculado no erro, ela atribuí um valor escalar de recompensa para o episódio 1 e o episódio 2, em seguida compara com uma softmax o quanto a recompensa 1 é melhor do que a 2. Depois faz o quanto a recompensa 2 é melhor do que a 1. 

Isso nós dá o valor predito pela rede em forma de probabilidade, que podemos utilizar para calcular o erro comparando o label atribuído pela intenção do usuário e essa probabilidade com a **Cross Entropy**. Somada do mesmo resultado para a possibilidade 2. Isso nos permite calcular o erro com relação entre a recompensa e as duas possíveis escolhas de melhora com base na escolha humana.


# [Training Language Models to Follow Instructions with Human Feedback](https://drive.google.com/file/d/1wzoJ8amD2YOMyNZ1v0e4rzS8sMfE58oB/view?usp=drive_link) (2022)


O Pessoa da Openai resolve inverstir na ideia do **RLHF** e utiliza ele para conseguir fazer um fine-tuning do seu modelo do GPT-3, criando o InstructGPT-3 que tem uma melhor capacidade de resposta que o modelo padrão, sem o Post-training.

1. Para isso é definida uma pipeline de treino, na qual, são primeiro amostrados prompts aleatórios e anotados respostas para esses prompts por pessoas e isso é utilizado para treinar o modelo novamente de maneira supervisionada.

2. Amostramos respostas a prompts aleatórios seguindo algumas categorias, como "QA", "Chat", "Review", "Sumarization"... e pedimos para uma pessoa escolher dentre duas respostas qual delas ela prefere, com isso podemos treinar um modelo de aprendizado supervisionado com feedback humano como foi feito no paper de **RLFH**. Esse modelo é chamado de Reward Model, pois seu papel é dar um valor escalar de recompensa dado uma resposta de um modelo. Para isso foi alterada a loss do modelo GPT-3 que foi usado para esse RM. Em que adicionamos no calculo da loss a perda com base na recompensa dada para ambas as respostas e o resultado humano, isso amostrado com relação a n respostas e combinando qualquer uma das respostas escolhidas.

3. Em seguida utilizamos o modelo treinado com aprendizado supervisionado na etapa 1 dentro da etapa 3 para aprender com base em prompts do usuário qual é a melhor forma de responder eles, enquanto a recompensa é dada pelo Reward Model treinado na etapa 2. Esse modelo STF é acolplado a arquitetura do PPO de actor critic. Onde o ator é o modelo STF com PPO, onde alteramos a loss do modelo adicionando a loss do PPO por KL Divergence somada de uma loss padrão utilizada para NLP que garante que o modelo mantenha os conhecimentos de LLM dele. Foi necessário utilizar KL Divergence em vez de Clipped Surrogate Objective porque ela observa toda a divergência da política atual com base na política do modelo SFT, não somente a imediatamente anterior. E o critic para calcular a função de valor foi utilizado como base o Reward Model, que já tinha como resultado um valor escalar como o V(s) faz.


Isso tudo foi acoplado dentro de uma pipeline que permitiu que modelos instruct superassem muito mais a performance do que aumentar o tamanho do modelo.

## Finalizado o estudo por hora de artigos sobre exclusivamente aprendizado por reforço.

# Redes Neurais


**[https://youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi&si=te7UnvqUH6Mo1wF0](https://youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi&si=te7UnvqUH6Mo1wF0)**

## Backpropagation

Vídeo sobre backpropagation, com o conjunto de vídeos foi possível aprender sobre a arquitetura de uma Multi-Layer Perceptron mais a fundo e conseguir verificar como funcionam todos os passos dentro de uma rede neural simples. Sem quaisquers outras melhorias arquiteturais desenvolvidas ao longo dos anos e foi possível identificar como funciona a regra da cadeia para o calculo dos gradientes utilizados para atualizar os pesos.



Mapeamento da área utilizando o livro [Learning Deep Learning](https://drive.google.com/file/d/1pNQlimPNz9ja-mLtwXeuqQjBTdApfm31/view?usp=sharing) 

# Marcos da área

Fundamentos do neurônio e MLP
	- Neurônio 
	- Perceptron
	- Multi Layer Perceptron (MLP)
	- Gradiente Descendente with Perceptrons
	- Backpropagation
	- Activation Functions
	- Training and Inference 
	- Loss Function
	- Mini-Batch Gradient Descent

Initialization:
	- Weight Initialization, Input Standartization, Batch Normalization

Inovações da MLP:
	- Cross Entropy
	- Logistic Softmax e Linear Unit
	- Improving Generalization with Regularization

Image Processing:
	- Convolutional Neural Networks (CNN)
	- Transfer Learning
	- Data Augmentation
	- Limitations of Feedfoward
	- Recurrent Neural Networks (RNN)
	- Long Short-Term Memory
	- Sequence-to-Sequence

Não Supervisionado:
	- GANs
	- Autoencoders


Aprendizado por reforço:
	- DQN
	- Double DQN
	- TRPO
	- PPO
	- SAC

Natural Language Processing
	- Transformers 
	- One-to-Many
	- Auto encoders 

Key Concepts:
	- Multimodal Learning
	- Process for Tuning a Network


# Papers Elencados Redes Neurais Fundamentos

# Fundamentos da MLP

### [A Logical Calculus of the Ideas Immanent in Nervous Activity](https://drive.google.com/file/d/1zF_G3tolWDgE1S_hW8ch-5pHqk1mg1lW/view?usp=sharing) - (Warren McCulloch & Walter Pitts, 1943)


### **[The Perceptron: A Probabilistic Model for Information Storage and Organization in the Brain](https://drive.google.com/file/d/1cJrUuWOyhnbs_RAq2gU9jqN6mOP1LlTi/view?usp=sharing)** — (Frank Rosenblatt, 1958)


### **[Perceptrons](https://archive.org/details/perceptronsintro00mins/page/n3/mode/2up)** — (Marvin Minsky & Seymour Papert, 1969)


### **[Adaptive Switching Circuits](https://drive.google.com/file/d/10rB9g6pCiaqgn4RErGzG5pKss9Qej8Kw/view?usp=sharing)** — (Bernard Widrow & Marcian Hoff, 1960)


### **[Learning Representations by Back-propagating Errors](https://drive.google.com/file/d/1-QPGh3tRryxGfxZd6LtvbFWkTXB4yi-5/view?usp=sharing)** — (David Rumelhart, Geoffrey Hinton & Ronald Williams, 1986) 


### **[Multilayer Feedforward Networks are Universal Approximators](https://drive.google.com/file/d/1Rvv7DrRMHg_FjFs48uyTDghPlp39jCBY/view?usp=sharing)** — (Kurt Hornik, Maxwell Stinchcombe & Halbert White, 1989)


### **[Adam: A Method for Stochastic Optimization](https://drive.google.com/file/d/1mJIU4MHahP6uFrvyn0dpKzmu2lxshkjK/view?usp=sharing)** — (Diederik Kingma & Jimmy Ba, 2014)


## Processamento de Imagens

### **[ImageNet Classification with Deep Convolutional Neural Networks (AlexNet)](https://drive.google.com/file/d/1wtin8YH0LCuDeP64yd05Lj0Kn8JnhjLY/view?usp=sharing)** — (Alex Krizhevsky, Ilya Sutskever & Geoffrey Hinton, 2012)


### **[Deep Residual Learning for Image Recognition (ResNet)](https://drive.google.com/file/d/1Gb2RBsMMGVlUpY2NYpgejTCwMP21_6UR/view?usp=sharing)** — (Kaiming He 2015/2016)


## Não Supervisionado
### **[Reducing the Dimensionality of Data with Neural Networks (autoencoders)](https://drive.google.com/file/d/11cjXodqAmZCB2lz2KUZEM3NTm1LPMBai/view?usp=sharing)** — (Geoffrey Hinton & Ruslan Salakhutdinov, 2006)


# NLP

### [**Long Short-Term Memory**](https://drive.google.com/file/d/1wMJieeCzT8HIv5tMvRkzozd48HT6UQbe/view?usp=sharing) — (Sepp Hochreiter & Jürgen Schmidhuber, 1997)

### **Attention Is All You Need (Transformer)** — (Ashish Vaswani, 2017)


### 12 Papers Essenciais


# Retirados da Trilha Essencial

### **Approximation by Superpositions of a Sigmoidal Function** — (George Cybenko, 1989)

### Probabilistic Interpretation of Feedforward Classification Network Outputs — (John Bridle, 1990)

### **Rectified Linear Units Improve Restricted Boltzmann Machines** — (Vinod Nair & Geoffrey Hinton, 2010)

### **Generative Adversarial Nets (GANs)** — (Ian Goodfellow, 2014)




# TODO

Mapear os artigos faltantes de RL no roteiro:

Watkins 1989, - Reinforce 1992, 

Actor Critic sutton e Barto 1998, 

Barto, A. G., Sutton, R. S., & Anderson, C. W. (1983) — "Neuronlike Adaptive Elements That Can 
Solve Difficult Learning Control Problems 

Reinforcement learning with deep energy-based policies. 

DPO - Phi 4?

GRPO - DeepkSeek