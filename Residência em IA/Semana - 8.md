# Resumo

Durante a primeira semana fiz a leitura dos temas de publicação dentro das conferências passadas, procurando por temas importantes, relevantes e interessantes, diante disso, percebi que grande parte da minha curiosidade vem do entendimento sobre como redes neurais funcionam. Chegando o tema de **Explicabilidade de Redes Neurais**. Porque, eu gostaria de entender quando uma rede neural está aprendendo em cima dos dados de treinamento e o que faz ela tomar certas decisões de escolha, que culminam na sua resposta, e com isso, conseguir identificar e corrigir as partes da arquitetura que fazem com que a rede tenha uma performance ruim. 

Depois de definido o tema, comecei o estudo pelos fundamentos, de Aprendizado por Reforço, lendo sobre artigos fundacionais e passando por **algotimos** e **técnicas** de RL. Que permitem realizar tarefas e resolver problemas atuais.

Depois de realizar esse estudo, eu fiz um outro estudo, agora sobre Redes Neurais, em que pesquisei duas coisas principais, **Fundamentos** e **Arquiteturas**, em que entendi sobre como se deu a ideia das MLPs, assim como algumas arquiteturas que evoluíram em cima das redes que existiam antigamente.

Explorei um pouco sobre o tema de **Generalização** em modelos treinados com **RL**, no entanto, percebi que somente medindo a capacidade do meu modelo de generalizar para dados que não foram vistos não me dá o poder para conseguir identificar porque esse modelo está falhando.

Por isso, parti para **Explicabilidade** de Redes Neurais (ainda tenho que verificar exatamente como justificar a inclusão do RL), mas gostaria de melhorar a análise do modelo para a escolha das suas ações, permitindo que um engenheiro de IA por meio dessa explicabilidade consiga melhorar o modelo desenvolvido. 

Durante essa semana eu percebi que Explicabilidade tem algumas diferenças com relação a Interpretabilidade e que meu tema se encaixa um pouco melhor na **Explicabilidade de modelos**, porque, o primeiro se refere a explicação de resultados de um modelo local ou globalmente, 
o segundo ser refere ao entendimento do funcionamento da arquitetura dos modelos, como o motivo da rede conseguir classificar um digito.
# Planejamento

Para essa semana eu planejo ler pelo menos 1 artigo mencionado para duas sub-áreas de explicabilidade em aprendizado por reforço e estudar sobre o uso de Aprendizado não Supervisionado para verificação de redes neurais com Autoencoders.

### Feature importance (O quanto cada feature contruíbui para o resultado final da rede), utilizada no **Actor** e no **Critic**:

**Integrated Gradientes, SHAP e Saliência por Perturbação** 

[2018] - Verifiable reinforcement learning via policy extraction.

[2017] - A Unified Approach to Interpreting Model Predictions

### *Knowledge Representaiton* - A rede neural consegue códificar as informações necessárias passadas como input: 

**Probing linear, TCAV, SAEs, CRP**

[2023] - Towards Monosemanticity: Decomposing Language Models With Dictionary Learning

[2025] - CAUSAL INTERPRETATION OF NEURAL NETWORK
COMPUTATIONS WITH CONTRIBUTION DECOMPOSITION

### *Decomposição de Recompensa* - A Recompensa guia o resultado esperado pelo modelo

**LPM, Reward Decomposition** 

[2019] - Explaining reinforcement learning to mere mortals: An empirical study 


# Leitura - Artigos


# [2018] - Verifiable reinforcement learning via policy extraction.

O artigo propõe o uso de um modelo chamada de **Viper** que funciona como um explainable model que utiliza **destilação** de conhecimento por meio de **imitational learning** para copiar o conhecimento de um modelo treinado com RL dentro de um modelo de árvore de decisão que é por natureza interpretável. 

#  [2017] - A Unified Approach to Interpreting Model Predictions

Utiliza como base uma ideia de teória dos jogos, chamada de SHAP (Shapley Aditive Explanation), que com base em um resultado permite calcular o quanto daquele resultado deve ser atribuído as features envolvidas, permitindo métrificar o quanto cada feature contribui para o resultado final.

Tendo diferentes tipos de conseguir estimar o quanto essa feature contribui com regressão linear, amostragem... Todas respeitando 3 propriedades "Local Accuracy", "Missingness" e "Consistency".

# [2019] - Explaining reinforcement learning to mere mortals: An empirical study 





# [2025] - Causal Interpretation Of Neural Network Computations With Contribution Decomposition





# Estudo do CODEC - Github

Ao estudar a estrutura e funcionamento do código do último artigo mencionado acima, elenquei uma estrutura 