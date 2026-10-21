
Durante a primeira semana fiz a leitura dos temas de publicação dentro das conferências passadas, procurando por temas importantes, relevantes e interessantes, diante disso, percebi que grande parte da minha curiosidade vem do entendimento sobre como redes neurais funcionam. Chegando o tema de **Estudo sobre o fenômeno de Generalização e Explicabilidade de Redes Neurais, treinadas com Aprendizado por Reforço**. Porque, eu gostaria de entender quando uma rede neural está aprendendo em cima dos dados de treinamento e o que faz ela tomar certas decisões de escolha, que culminam na sua resposta. 

Depois de definido o tema, comecei o estudo pelos fundamentos, de Aprendizado por Reforço, lendo sobre artigos fundacionais e passando por **algotimos** e **técnicas** de RL. Que permitem realizar tarefas e resolver problemas atuais.

Depois de realizar esse estudo, eu fiz um outro estudo, agora sobre Redes Neurais, em que pesquisei duas coisas principais, **Fundamentos** e **Arquiteturas**, em que entendi sobre como se deu a ideia das MLPs, assim como algumas arquiteturas que evoluíram em cima das redes que existiam antigamente.

Para essa semana, eu gostaria de conseguir explorar melhor o tema de **Explicabilidade e Generalização**, agora que eu tenho conhecimento dos fundamentos que geram aquilo, e mapeei alguns frameworks que são úteis para o desenvolvimento de aplicações dentro da área.

# Porque estudar Generalização?

O estudo sobre generalização vem devido a curiosidade e a relevância do assunto quando tratamos de redes neurais. Com isso, irei formular certas perguntas, que busco responder com o meu estudo sobre o tema.

1. Porque e Quando a rede generalizou em cima dos dados?
2. Como eu posso avaliar se uma rede aprendeu os dados de treino de modo que consiga se adaptar a variações deles?. (OOD)
3. O que causa/gera fenômenos como o **Grokking**, de generalização tardia?
4. Como identificar por meio de métricas se uma rede neural aprendeu ou não? Quais são os viézes de realizar essa análise?
5. Porque o overfitting é menos comum em LLMs?

Percebi que o estudo de generalização irá tomar muito tempo e é algo extremamente complexo, com isso, resolvi limitar a parte de explicabilidade e focar na generalização. Principalmente estudando o que causou a generalização e verificação se o modelo é realmente generalista. 

## Medir a generalização

[[2023] - A Survey of Zero-shot Generalisation in Deep Reinforcement Learning](https://drive.google.com/file/d/1sKVrHBi3GfymNhYwM2naujjL3Se2DjyJ/view?usp=drive_link) (Robert Kirk)


# Porque estudar sobre Explicabilidade?

Estudar sobre explicabilidade, ajuda o engenheiro de IA a conseguir diagnosticar problemas com a rede neural sem precisar realizar múltiplos experimentos e utilizar de técnicas de avaliação e métrificação para conseguir resolver o problema, ao conseguir ter um conhecimento maior sobre o tema.

1. O quanto é possível explicar sobre a decisão de uma rede neural?
2. Há alguma maneira de visualizar essa decisão?
3. Quais neurônios ou partes da arquitetura colaboram diretamente para gerar esse resultado?



No final o meu trabalho busca conseguir entender, quando uma rede neural começou a generalizar em cima dos dados. Porque essa generalização ocorreu, se foi por grokking ou outro fenômeno. Depois disso, conseguir explicar as decisões tomadas pela rede, quais neurônios ajudaram  na decisão que essa rede tomou.


# Artigos - Frameworks de RL e Generalização


## Aprendizado por Reforço 


### [2021] - CleanRL High quality Single file Implementations of Deep Reinforcement Learning Algorithms (Huang et al. 2021)


### [2024] - Gymnasium A Standardized Interface for Reinforcement Learning Environments (Towers et al. 2024)



## Generalização

### [2023] - A Survey of Zero-shot Generalisation in Deep Reinforcement Learning (Kirk et al. 2023)


### [2018] - Quantifying Generalization in Reinforcement Learning (Cobbe et al. 2018)


### [2020] - Leveraging Procedural Generation to Benchmark Reinforcement Learning (Cobbe et al. 2020)


### [2022] - Towards Understanding Grokking An Effective Theory of Representation Learning (Liu et al. 2022)


### [2024] - Deep Networks Always Grok and Here is Why (Humanyun et al. 2024)


### [2026] - A Survey on Grokking (Bertolotti et al. 2026)


### [2026] - Spectral Entropy Collapse as a Phase Transition (Khanh et al. 2026)
