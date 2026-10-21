
A fim de continuar o mapeamento de artigos essenciais para o entendimento da área de aprendizado por reforço. Ainda tenho que ler os seguintes artigos mapeados. Imagino que só será possível ler 3 artigos ou 2 essa semana, além de assistir ao vídeo do 3blue1brown sobre redes neurais.

## [Mastering Chess and Shogi by Self-Play with a General Reinforcement Learning Algorithm](https://drive.google.com/file/d/1hiUESPAbWneh_sF_-R59944RlQDtpC-d/view?usp=drive_link) (2018)

Determinei que não irei ler esse artigo, porque ele não tráz nenhuma inovação algoritmica para a área, mais uma inovação de aplicação dos algoritmos pre-existentes


## [Asynchronous Methods for Deep Reinforcement Learning](https://drive.google.com/file/d/15y51BvQFB0vC7uG9y4AdqAXPKyh3mezR/view?usp=drive_link)(A3C - 2016)

Paper muito bem escrito, ele tráz uma melhoria muito simples no conceito.

Retirar a necessidade de ter um replay buffer dentro de algoritmos como **DQN**. Isso seria feito utilizando paralelismo para poder instânciar *n* ambientes de maneira simultânea, essa situação resolver o principal problema resolvido pelo **replay buffer** que era o fato das ações serem muito semelhantes de um episódio para o outro e por conta disso a rede neural não aprendia muito, porque ela foi contruída para receber a cada epoch dados de diferentes domínios e sem correlação entre si. Devido ao paralelismo resolvemos o problema de relação temporal entre os episódios, além de trazer uma serie de benéficios, porque como é asynchronous permite a execução mais rápida dos algoritmos, além de viabilizar o uso de algoritmos **on-policy** em redes neurais.

Essa virada de chave é feita dividindo o ambiente em n threads e dentro de cada thread temos uma copia dos pesos da rede neural e a cada step, ou n-steps atualizamos o gradiente com base na recompensa acumulada, mas somente atualizamos o gradiente de maneira simultânea dentro da rede global depois de x gradientes, para que tenha maior eficiência de dados e não tenha concorrência entre diferentes ambientes. 

Considerando isso também tem um melhor desempenho utilizar diferentes estrátegias de exploração para garantir gradientes diferentes. Dentro dessa ideia no paper foi reformulado os 3 algoritmos principais de RL **Sarsa** **Q-learning** e **Actor-critic** que foi batizado de **A3C**. 


## [Proximal Policy Optimization Algorithms](https://drive.google.com/file/d/1ZrWzWU51SU6PtMddXSZ3bhwWhHADZ8oK/view?usp=drive_link) (PPO - 2017)

Muito bom e resumido o artigo sobre PPO

O algoritmo herda da ideia de utilizar **Gradientes de política** para conseguir otimizar o valor da recompensa recebida por um agente dentro de um determinado momento. No entanto, o algoritmo mais recente e avançado dentro dessa área, chamado de **TRPO** sofre de um problema, porque ele precisa manter uma restrição e por isso não é possível otimizar diretamente a sua loss, mais é necessário amostrar utilizando **Monte Carlo** para conseguir simular as distribuíções de experança.

Por isso o algoritmo do PPO foi melhorando ao adicionar uma forma de otimizar essa restrição dentro da política. Porque a restrição existe, já que a formula foi encontrada devido a uma aproximação do valor entre o ganho de uma política antiga para a nova política, mas essa aproximação somente é verdadeira quando a proporção entre o valor estimado pelas políticas tá dentro de um intervalo. Para isso foram pensadas em duas formas de conseguir adicionar esse valor dentro do calculo da loss.

**Clipped Surrogate Objective** - É adicionado um clip dentro do calculo da loss, de modo que se a divergência entre a proporção de valores estimados pelas políticas é muito grande ou muito pequena ele é passado para um valor fixo determinado por 1 - e. L clip

**Adaptive KL Penalty Coefficient** - É adicionado um coeficiente de penalidade no calculo que representa a divergência entre as distribuições de cada política multiplicada por uma parâmetro B. Que é atualizado ao longo do treinamento, mas parece que essa política teve um resultado insatisfatório em relação a outra forma anterior.

Com isso utilizando essa nova loss ela é subtraída da loss de vantagem e somada a um valor de entropia para promover a exploração do agente dentro do ambiente.

Depois disso somente são provados os resultados e explicado o contexto utilizado.




## Estudei também sobre um vídeo explicativo de gradiente descendente.

[Gradient descent](https://www.youtube.com/watch?v=IHZwWFHWa-w&list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi&index=2)

Foi entendido que o gradiente descendente é calculado durante a parte do backpropagation, com relação a cada um dos neurônios da minha rede, atualizando os pesos desses neurônios, ao propagar o erro a função de custo que é representado no calculo de uma loss entre o valor esperado da resposta **Label** e o valor real da resposta, no caso de **RL** esse erro da loss é calculado e alterado de diferentes maneiras dependendo do algoritmo utilizado. 

Para conseguir propagar o erro da loss para cada um dos neurônios da rede é necessário calcular o backpropagation com a regra da cadeia para conseguir propagar retroativamente esse erro. Preciso entender melhor o backprop para saber a intuição exata.

O gradient então indica um valor que é calculado que se ele foi positivo a rede está subindo para a direita, se for negativo a rede está descendo na direita, portanto esse valor é subtraído durante a atualização dos pesos, porque se ele estiver positivo, subtraíndo isso vc garante que vai descer, e se está negativo subtraíndo vc garante que vai subir.


# Próximas semanas 

Watikins 1989, - Reinforce 1992, - Actor Critic sutton e Baro 1998, Barto, A. G., Sutton, R. S., & Anderson, C. W. (1983) — "Neuronlike Adaptive Elements That Can Solve Difficult Learning Control Problems

# [Soft Actor-Critic:  Off-Policy Maximum Entropy Deep Reinforcement  Learning with a Stochastic Actor](https://drive.google.com/file/d/1kaPzb0mcTQdu5Fcrvsr6NLHFEBWgZeWl/view?usp=drive_link) (2018)



# [Deep Reinforcement Learning from Human Preferences](https://drive.google.com/file/d/1n3Qvne6u_SLEhkyqoxNLXQ_L5-IceXbr/view?usp=drive_link) (2017)



# [Training Language Models to Follow Instructions with Human Feedback](https://drive.google.com/file/d/1wzoJ8amD2YOMyNZ1v0e4rzS8sMfE58oB/view?usp=drive_link) (2022)



**[https://youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi&si=te7UnvqUH6Mo1wF0](https://youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi&si=te7UnvqUH6Mo1wF0)**


É realizar um mapeamento prévio sobre a área de redes neurais para que eu siga na leitura dos artigos nas semanas seguintes.