
Durante a primeira semana fiz a leitura dos temas de publicação dentro das conferências passadas, procurando por temas importantes, relevantes e interessantes, diante disso, percebi que grande parte da minha curiosidade vem do entendimento sobre como redes neurais funcionam. Chegando o tema de **Explicabilidade de Redes Neurais, treinadas com Aprendizado por Reforço**. Porque, eu gostaria de entender quando uma rede neural está aprendendo em cima dos dados de treinamento e o que faz ela tomar certas decisões de escolha, que culminam na sua resposta, e com isso, conseguir identificar e corrigir as partes da arquitetura que fazem com que a rede tenha uma performance ruim. 

Depois de definido o tema, comecei o estudo pelos fundamentos, de Aprendizado por Reforço, lendo sobre artigos fundacionais e passando por **algotimos** e **técnicas** de RL. Que permitem realizar tarefas e resolver problemas atuais.

Depois de realizar esse estudo, eu fiz um outro estudo, agora sobre Redes Neurais, em que pesquisei duas coisas principais, **Fundamentos** e **Arquiteturas**, em que entendi sobre como se deu a ideia das MLPs, assim como algumas arquiteturas que evoluíram em cima das redes que existiam antigamente.

Explorei um pouco sobre o tema de **Generalização** em modelos treinados com **RL**, no entanto, percebi que somente medindo a capacidade do meu modelo de generalizar para dados que não foram vistos não me dá o poder para conseguir identificar porque esse modelo está falhando

# Processo de como treinar uma Rede com Aprendizado por Reforço 

Com base em um problema sequencial (em que estados futuros são atingidos somente por ações realizadas nos estados atuais, que contém toda a informação do ambiente), mapeado como um processo de decisão de markov - (s,a,r), em que o modelo (Pode ser qualquer tipo de rede neural adaptada com uma técnica de reforço para o meu problema EX: PPO + CNN, PPO + Transformers, A2c + CNN...) recebe como input a **obs** que representa o estado, retorna uma ação, depois disso o critico confere um Valor para essa ação. Atualmente esse ciclo se repete por uma quantidade grande de vezes, até que a rede seja atualizada no rollout que infere novamente os valores de **Probabilidade dada a ação escolhida estado pelo ator** e com base nessa probabilidade calcula o quanto uma política antiga != política nova. Para calcular a **Clipped Surrogate Loss** e somar isso pela **Entropia**. O mesmo calculo acontece com o **Critico** em que comparamos o Valor dado a um estado V(s^t+1) - V(s). 

E esse ciclo se repete por uma quantidade gigante de episódios em que cada x Episódios representa um step da função e depois de uma grande quantidade de episódios minha rede neural foi treinada. No entanto, para validar o treinamento e conseguir diagnosticar as suas capacidades, penso em observar as suas métricas de treinamento (mean/return, loss, entropy...), mas isso só informa o engenheiro de machine learning (Temos um problema), não informa o que é o problema, de onde ele veio. Com isso, o papel do engenheiro é investigar esse problema e conseguir diagnósticar alterando o ambiente para verificar como melhorar a capacidade da rede.

Dentro desses gap de diagnóstico é onde entra a pesquisa que eu gostaria de fazer, pensei primeiramente em análisar as capacidades de generalização de uma rede que foi bem sucedida e verificar os seus artefatos que colaboraram para que essa rede tivesse um bom resultado, mas essa abordagem de pesquisa torna o problema muito especifíco e corresponde a boas práticas utilizadas durante o treinamento (dentro de um problema específico) que fazem com que ele tenha bons resultados.

No entanto, eu quero conseguir ampliar essa análise para diferentes tipos de problema e por isso comecei a seguir dentro da área de Explicabilidade, onde na teória eu conseguiria ter um verbose maior da parte "Estado entra na rede -> Rede -> Rede retorna ação", porque dada uma ação o motivo da sua recompensa é observável e é possível análisar como a política foi atualizada com base na recompensa. Com base nisso, precisamos de técnicas de Explicabilidade para conseguir indentificar o motivo de uma rede escolher determinada ação com base no seu estado, que tipo de informação a rede está utilizando para conseguir escolher as ações.
# Comentários sobre o tema

Pelo que eu entendi, o meu objetivo de conseguir melhorar o entedimento do problema e conseguir diagnosticar melhor uma solução para o problema, sem ter que realizar inúmeros testes de ablação que podem demorar muito tempo 

# Artigos sobre Explicabilidade

## [2024] - Explainable Reinforcement Learning A Survey and Comparative Review.pdf

Tem como objetivo de pesquisa ajudar pesquisadores a tomarem decisões de melhora do modelo em cima de erros, além de permitir uma verificação se o agente irá atuar em produção de maneira segura e razoável.

Dentro do artigo ele apresenta métricas que uma análise de explicabilidade precisa verificar para diferentes tipos de análise.

**Fidelidade** - Se o modelo utilizado como **Post-hoc** tem escolhas de ações parecidas com o do modelo original.

**Performance** - Se o modelo utilizado como **Post-hoc** tem capacidade semelhante as capacidades de uma rede original.

**Comprensibilidade** - Dificuldade de compressão da análise se Explicabilidade feita, pelos usuários.

**Preferência** - Como as pessoas que irão utilizar essa análise preferem que essa métricas fiquem mostradas.

**Acionabilidade** - O quanto essa métrica contribui para a mudança de comportamento da rede.

**Capacidade Cognitiva** - Quanto tempo demora para uma pessoa realizar o diagnostíco com base na métrica passada de explicabilidade.

**Visualização** - Sem tem alguma maneira de visualizar as métricas utilizadas 

O artigo propõe certas categorias de análise também, sendo elas:

**Feature Importance** - O quanto cada feature está sendo utilizada e impacta no resultado (escolha de ações dentro de uma rede neural).

**Learning Process and MDP** - Considerando um processo de decisão de Markov entender como a política muda durante o treinamento com base em exemplos, decompor funções de recompensa .

**Policy level** - Verificar como podemos identificar um padrão das transições de estados realizada pela política. 

# Frameworks de Aprendizado por Reforço
## Frameworks de Explicabilidade

### [2021] - CleanRL High quality Single file Implementations of Deep Reinforcement Learning Algorithms (Huang et al. 2021)

Framework que realiza a implementação de diversos algoritmos de **RL** em ambientes diferentes trazendo implementações minimalistas.

**PPO** - 

**DQN** - 

### [2024] - Gymnasium A Standardized Interface for Reinforcement Learning Environments (Towers et al. 2024)

Um Framework que padroniza os mods de implementação de Aprendizado por Reforço, utilizando ambiente já comumente utilizadas e metódos de paralelizaçao de ambientes, registro de alterações e Wrappers para conseguir desenvolver em cima desses ambientes. 

Temos 2 tipos de paralelização **SyncVectorEnvs** e **AsyncVectorEnvs** em que o sincrono faz com que todos os ambientes em paralelo atualizem o gradiente de maneira syncrona, e o async não. O async normalmente garante mais performance mais no custo de memória. 


# Resumo com base na taxônomia do que deve ser estudado

### Feature importance (O quanto cada feature contruíbui para o resultado final da rede), utilizada no **Actor** e no **Critic**:

**Integrated Gradientes, SHAP e Saliência por Perturbação** 

[2018] - Verifiable reinforcement learning via policy extraction.

[2021] - Iterative bounding MDPs: Learning inter-pretable policies via non-interpretable method

[2017] - A Unified Approach to Interpreting Model Predictions

### *Representação da Informação* - A rede neural consegue códificar as informações necessárias passadas como input: 

**Probing linear, TCAV, SAEs, CRP**

### *Decomposição de Recompensa* - A Recompensa guia o resultado esperado pelo modelo

**LPM, Reward Decomposition** 

### *Confirmação de Hipótese* - Alterar o ambiente com base no diagnóstico feito pelas técnicas de explicabilidade de uma rede e verificar como isso alterou o resultado do ambiente. 

**Activation steering, pathing, mudança de ambiente** 





### Verificar o que o claude cuspiu e retirar o ruído.


SHAP
- A Unified Approach to Interpreting Model Predictions — Lundberg & Lee (NeurIPS 2017)
- A Value for n-Person Games — Shapley (1953)
- "Why Should I Trust You?": Explaining the Predictions of Any Classifier — Ribeiro, Singh & Guestrin (KDD 2016) [LIME]
- Learning Important Features Through Propagating Activation Differences — Shrikumar, Greenside & Kundaje (ICML 2017) [DeepLIFT]

INTEGRATED GRADIENTS
- Axiomatic Attribution for Deep Networks — Sundararajan, Taly & Yan (ICML 2017)

CRP
- From Attribution Maps to Human-Understandable Explanations through Concept Relevance Propagation — Achtibat et al. (Nature Machine Intelligence 2023)
- On Pixel-Wise Explanations for Non-Linear Classifier Decisions by Layer-Wise Relevance Propagation — Bach et al. (PLoS ONE 2015) [LRP]

TCAV
- Interpretability Beyond Feature Attribution: Quantitative Testing with Concept Activation Vectors (TCAV) — Kim et al. (ICML 2018)

SPARSE AUTOENCODERS
- Towards Monosemanticity: Decomposing Language Models With Dictionary Learning — Bricken et al. (Anthropic, Transformer Circuits Thread, 2023)
- Sparse Autoencoders Find Highly Interpretable Features in Language Models — Cunningham et al. (ICLR 2024)
- Toy Models of Superposition — Elhage et al. (Anthropic, 2022)
- Emergence of Simple-Cell Receptive Field Properties by Learning a Sparse Code for Natural Images — Olshausen & Field (Nature 1996)
- Interpretable and Testable Vision Features via Sparse Autoencoders — Stevens et al. (arXiv 2025; título da v1: Sparse Autoencoders for Scientifically Rigorous Interpretation of Vision Models)

MAIA
- A Multimodal Automated Interpretability Agent — Shaham et al. (ICML 2024)
- FIND: A Function Description Benchmark for Evaluating Interpretability Methods — Schwettmann et al. (NeurIPS 2023) [paradigma de agentes de interpretabilidade]