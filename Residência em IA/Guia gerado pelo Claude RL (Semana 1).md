# Guia de Estudo: Fundamentos e Papers Essenciais de Reinforcement Learning

## Como usar este guia

A ordem abaixo é pensada para construir intuição progressivamente: primeiro a base matemática (Programação Dinâmica e MDPs), depois os algoritmos clássicos de RL tabular, depois a virada para Deep RL, e por fim os ramos modernos (policy gradient, model-based, RLHF). Não tente ler tudo de uma vez — o livro do Sutton & Barto deve ser sua espinha dorsal, e os papers servem para aprofundar pontos específicos conforme você avança nele.

---

## 0. O livro-base (leia em paralelo com tudo)

**Sutton, R. S. & Barto, A. G. — "Reinforcement Learning: An Introduction" (1998, 2ª edição 2018)**
É o texto fundador didático da área. Cobre desde a história intelectual do campo (conexões com psicologia comportamental, controle ótimo e aprendizado por diferença temporal) até os algoritmos modernos. Gratuito em PDF pelo site do autor: incompleteideas.net/book/the-book.html.
Vale notar: <cite index="1-1">Sutton e Barto receberam o Prêmio Turing de 2025</cite>, o que reforça o papel central desse livro e do trabalho dos dois na fundação do campo.

---

## 1. Fundamentos matemáticos (décadas de 1950-1960)

**Bellman, R. — "A Markovian Decision Process" (1957)**
Introduz a equação de Bellman e o conceito de Processos de Decisão de Markov (MDPs), a base matemática de todo RL. Sem entender essa equação, nada do resto faz sentido — é o "recorte recursivo" que permite decompor decisões sequenciais em subproblemas. [x]

**Bellman, R. — "Dynamic Programming" (livro, 1957)**
Formaliza a Programação Dinâmica, precursora direta dos algoritmos de RL baseados em valor (value iteration, policy iteration). [x]

**Howard, R. A. — "Dynamic Programming and Markov Processes" (1960)**
Desenvolve policy iteration e conecta MDPs a aplicações práticas de decisão.

---

## 2. As raízes psicológicas e o nascimento do RL moderno (1970s-1980s)

**Klopf, A. H. — "Brain Function and Adaptive Systems: A Heterostatic Theory" (1972)**
Trabalho que inspirou Sutton e Barto a distinguirem aprendizado por reforço de aprendizado supervisionado — a ideia de que sistemas adaptativos buscam maximizar algo, não apenas prever.

**Barto, A. G. & Sutton, R. S. — "Toward a Modern Theory of Adaptive Networks: Expectation and Prediction" (1981)**
Um dos primeiros trabalhos formalizando a distinção entre aprendizado supervisionado e por reforço, ligando isso a modelos de condicionamento clássico.

**Sutton, R. S. — "Learning to Predict by the Methods of Temporal Differences" (1988)** [x]
Paper fundamental: introduz formalmente o TD-learning (aprendizado por diferença temporal), a técnica central que une previsão e controle em RL. É leitura obrigatória — praticamente todo algoritmo moderno de RL usa alguma forma de TD.

**Watkins, C. J. C. H. — "Learning from Delayed Rewards" (tese de doutorado, 1989)**
Introduz o **Q-learning**, o algoritmo mais influente de RL tabular, permitindo aprendizado off-policy do valor ótimo de ações sem precisar de um modelo do ambiente.

**Watkins, C. J. C. H. & Dayan, P. — "Q-Learning" (Machine Learning, 1992)** [x]
A prova formal de convergência do Q-learning, publicada como nota técnica — consolidou matematicamente o método de 1989.

---

## 3. Policy Gradient e a formalização do controle (1990s)

**Williams, R. J. — "Simple Statistical Gradient-Following Algorithms for Connectionist Reinforcement Learning" (1992)**
Introduz o algoritmo REINFORCE, a base de todos os métodos de policy gradient modernos (incluindo PPO e TRPO décadas depois).

**Tsitsiklis, J. N. & Van Roy, B. — "An Analysis of Temporal-Difference Learning with Function Approximation" (1997)**
Formaliza os limites e garantias teóricas de combinar TD-learning com aproximadores de função (redes neurais), preparando terreno teórico para o Deep RL.

**Sutton, R. S., McAllester, D., Singh, S. & Mansour, Y. — "Policy Gradient Methods for Reinforcement Learning with Function Approximation" (NeurIPS, 1999)** [x]
Formaliza o teorema de policy gradient de forma geral, unificando REINFORCE com aproximação de função — base teórica de tudo que veio depois em policy gradient.

---

## 4. A virada para Deep RL (2013-2016)

**Mnih, V. et al. (DeepMind) — "Playing Atari with Deep Reinforcement Learning" (2013)**
O paper que provou que redes neurais profundas combinadas com Q-learning (DQN) conseguem aprender diretamente de pixels a jogar Atari em nível humano. Marco histórico que reacendeu o interesse global em RL.

**Mnih, V. et al. — "Human-level Control through Deep Reinforcement Learning" (Nature, 2015)**
Versão consolidada e publicada na Nature do DQN, com replay buffer e rede-alvo (target network) — as duas inovações que estabilizaram o treinamento.

**Silver, D. et al. — "Mastering the Game of Go with Deep Neural Networks and Tree Search" (Nature, 2016)** — AlphaGo
Combina redes neurais profundas, busca em árvore Monte Carlo (MCTS) e RL para derrotar campeões humanos de Go, um marco simbólico enorme para a área.

**Van Hasselt, H., Guez, A. & Silver, D. — "Deep Reinforcement Learning with Double Q-learning" (2016)**
Corrige o viés de superestimação do Q-learning clássico, gerando o Double DQN.

**Schaul, T. et al. — "Prioritized Experience Replay" (2016)**
Melhora a eficiência de amostragem do replay buffer, priorizando transições mais "surpreendentes" para o agente.

**Wang, Z. et al. — "Dueling Network Architectures for Deep Reinforcement Learning" (2016)**
Separa a estimativa de valor de estado e vantagem de ação na arquitetura da rede, melhorando a estabilidade do DQN.

---

## 5. Policy Gradient profundo e métodos atores-críticos (2015-2018)

**Lillicrap, T. et al. — "Continuous Control with Deep Reinforcement Learning" (2015)** — DDPG
Estende DQN para espaços de ação contínuos usando arquitetura ator-crítico.

**Schulman, J. et al. — "Trust Region Policy Optimization" (TRPO, 2015)**
Introduz otimização com restrição de região de confiança para tornar policy gradient mais estável.

**Mnih, V. et al. — "Asynchronous Methods for Deep Reinforcement Learning" (A3C, 2016)**
Treina múltiplos agentes em paralelo de forma assíncrona, tornando o treinamento mais rápido e estável sem replay buffer.

**Schulman, J. et al. — "Proximal Policy Optimization Algorithms" (PPO, 2017)**
Simplifica o TRPO mantendo boa parte da estabilidade — hoje é provavelmente o algoritmo de policy gradient mais usado na prática, inclusive em RLHF de LLMs.

**Haarnoja, T. et al. — "Soft Actor-Critic" (SAC, 2018)**
Introduz RL com maximização de entropia, tornando o treinamento mais robusto e eficiente em amostras para controle contínuo.

---

## 6. Model-based RL e planejamento (2017-2020)

**Silver, D. et al. — "A General Reinforcement Learning Algorithm that Masters Chess, Shogi and Go" (AlphaZero, 2018)**
Generaliza o AlphaGo para aprender do zero (self-play puro), sem conhecimento humano prévio, em múltiplos jogos.

**Schrittwieser, J. et al. — "Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model" (MuZero, 2020)**
Aprende um modelo do ambiente implicitamente, sem precisar conhecer as regras do jogo, unificando model-free e model-based RL.

---

## 7. RL aplicado a modelos de linguagem (2017-2022) — relevante hoje

**Christiano, P. et al. — "Deep Reinforcement Learning from Human Preferences" (2017)**
Base metodológica do RLHF (Reinforcement Learning from Human Feedback), usado depois para alinhar LLMs como o ChatGPT.

**Ouyang, L. et al. (OpenAI) — "Training Language Models to Follow Instructions with Human Feedback" (InstructGPT, 2022)**
Aplica RLHF (com PPO) para alinhar LLMs a seguir instruções — o paper que originou a linha de trabalho por trás dos assistentes conversacionais modernos.

---

## Roteiro sugerido de estudo

1. **Fundação teórica**: Bellman → capítulos 3-4 do Sutton & Barto (MDPs, Programação Dinâmica)
2. **RL tabular clássico**: TD-learning (Sutton 1988) → Q-learning (Watkins 1989) → capítulos 5-7 do livro
3. **Teoria de policy gradient**: REINFORCE (Williams 1992) → Policy Gradient Theorem (Sutton et al. 1999)
4. **Deep RL**: DQN (2013/2015) → Double/Dueling/Prioritized DQN → capítulos sobre aproximação de função
5. **Métodos modernos ator-crítico**: A3C → TRPO → PPO → SAC
6. **Model-based**: AlphaGo → AlphaZero → MuZero
7. **Fronteira atual**: RLHF e aplicação em LLMs

## Dica prática
Para cada paper, tente reimplementar a versão mais simples do algoritmo (ex.: Q-learning tabular no Frozen Lake/Gridworld, depois REINFORCE no CartPole, depois um DQN simples no Atari via Gymnasium). A combinação teoria + implementação é o que consolida a expertise nessa área — RL é uma área onde intuição sem prática raramente gera domínio real.
