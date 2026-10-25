# Resumo

Durante a primeira semana fiz a leitura dos temas de publicação dentro das conferências passadas, procurando por temas importantes, relevantes e interessantes, diante disso, percebi que grande parte da minha curiosidade vem do entendimento sobre como redes neurais funcionam. Chegando o tema de **Explicabilidade de Redes Neurais, treinadas com Aprendizado por Reforço**. Porque, eu gostaria de entender quando uma rede neural está aprendendo em cima dos dados de treinamento e o que faz ela tomar certas decisões de escolha, que culminam na sua resposta, e com isso, conseguir identificar e corrigir as partes da arquitetura que fazem com que a rede tenha uma performance ruim. 

Depois de definido o tema, comecei o estudo pelos fundamentos, de Aprendizado por Reforço, lendo sobre artigos fundacionais e passando por **algotimos** e **técnicas** de RL. Que permitem realizar tarefas e resolver problemas atuais.

Depois de realizar esse estudo, eu fiz um outro estudo, agora sobre Redes Neurais, em que pesquisei duas coisas principais, **Fundamentos** e **Arquiteturas**, em que entendi sobre como se deu a ideia das MLPs, assim como algumas arquiteturas que evoluíram em cima das redes que existiam antigamente.

Explorei um pouco sobre o tema de **Generalização** em modelos treinados com **RL**, no entanto, percebi que somente medindo a capacidade do meu modelo de generalizar para dados que não foram vistos não me dá o poder para conseguir identificar porque esse modelo está falhando.

Por isso, parti para **Explicabilidade** de Redes Neurais (ainda tenho que verificar exatamente como justificar a inclusão do RL), mas gostaria de melhorar a análise do modelo para a escolha das suas ações, permitindo que um engenheiro de IA por meio dessa explicabilidade consiga melhorar o modelo desenvolvido. 

# Planejamento

Para essa semana eu planejo ler pelo menos 1 artigo mencionado para duas sub-áreas de explicabilidade em aprendizado por reforço e estudar sobre o uso de Aprendizado não Supervisionado para verificação de redes neurais com Autoencoders.

### Feature importance (O quanto cada feature contruíbui para o resultado final da rede), utilizada no **Actor** e no **Critic**:

**Integrated Gradientes, SHAP e Saliência por Perturbação** 

[2018] - Verifiable reinforcement learning via policy extraction.

[2017] - A Unified Approach to Interpreting Model Predictions

### *Representação da Informação* - A rede neural consegue códificar as informações necessárias passadas como input: 

**Probing linear, TCAV, SAEs, CRP**

[2018] - Summarizing agent behavior to people - RL

[2023] - Sparse Autoencoders Find Highly Interpretable Features in Language Models

[2023] - Towards Monosemanticity: Decomposing Language Models With Dictionary Learning

[2024] - A Multimodal Automated Interpretability Agent

### *Decomposição de Recompensa* - A Recompensa guia o resultado esperado pelo modelo

**LPM, Reward Decomposition** 

[2019] - Explaining reinforcement learning to mere mortals: An empirical study - RL

[2022] - From Attribution Maps to Human-Understandable Explanations through Concept Relevance Propagation

### *Confirmação de Hipótese* - 
