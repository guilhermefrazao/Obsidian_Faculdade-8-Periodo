
Durante a primeira semana fiz a leitura dos temas de publicação dentro das conferências passadas, procurando por temas importantes, relevantes e interessantes, diante disso, percebi que grande parte da minha curiosidade vem do entendimento sobre como redes neurais funcionam. Chegando o tema de **Explicabilidade de Redes Neurais, treinadas com Aprendizado por Reforço**. Porque, eu gostaria de entender quando uma rede neural está aprendendo em cima dos dados de treinamento e o que faz ela tomar certas decisões de escolha, que culminam na sua resposta, e com isso, conseguir identificar e corrigir as partes da arquitetura que fazem com que a rede tenha uma performance ruim. 

Depois de definido o tema, comecei o estudo pelos fundamentos, de Aprendizado por Reforço, lendo sobre artigos fundacionais e passando por **algotimos** e **técnicas** de RL. Que permitem realizar tarefas e resolver problemas atuais.

Depois de realizar esse estudo, eu fiz um outro estudo, agora sobre Redes Neurais, em que pesquisei duas coisas principais, **Fundamentos** e **Arquiteturas**, em que entendi sobre como se deu a ideia das MLPs, assim como algumas arquiteturas que evoluíram em cima das redes que existiam antigamente.

Explorei um pouco sobre o tema de **Generalização** em modelos treinados com **RL**, no entanto, percebi que somente medindo a capacidade do meu modelo de generalizar para dados que não foram vistos não me dá o poder para conseguir identificar porque esse modelo está falhando

# Processo de como treinar uma Rede com Aprendizado por Reforço 


# Comentários sobre o tema

Pelo que eu entendi, o meu objetivo de conseguir melhorar o entedimento do problema e conseguir diagnosticar melhor uma solução para o problema, sem ter que realizar inúmeros testes de ablação que podem demorar muito tempo 

# Artigos sobre Explicabilidade

## [2024] - Explainable Reinforcement Learning A Survey and Comparative Review.pdf

Tem como objetivo de pesquisa ajudar pesquisadores a tomarem decisões de melhora do modelo em cima de erros, além de permitir uma verificação se o agente irá atuar em produção de maneira segura e razoável.






# Frameworks de Aprendizado por Reforço
## Frameworks de Explicabilidade

### [2021] - CleanRL High quality Single file Implementations of Deep Reinforcement Learning Algorithms (Huang et al. 2021)



### [2024] - Gymnasium A Standardized Interface for Reinforcement Learning Environments (Towers et al. 2024)




# Resumo com base na taxônomia do que deve ser estudado

### Feature importance (O quanto cada feature contruíbui para o resultado final da rede), utilizada no **Actor** e no **Critic**:

**Integrated Gradientes, SHAP e Saliência por Perturbação** 

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