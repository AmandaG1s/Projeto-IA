# Projeto-IA-PACMAN

Aprendizado por Reforço: Pac-Man como MDP

Repositório da dupla para as entregas da disciplina de Aprendizado por Reforço.

Integrantes
Eric Rhaysllier Silva,
Amanda Gomes

# O problema:

- Ensinar um agente a jogar Pac-Man em um labirinto pequeno. O agente deve comer todas as pastilhas no menor número de passos, sem ser pego por um fantasma que se move ao acaso. Como o agente não sabe de antemão qual é a melhor jogada, ele aprende uma política (qual ação tomar em cada estado) por tentativa e erro, maximizando a recompensa acumulada.

- O problema é modelado como um MDP (processo de decisão de Markov).

Modelagem (Desafio 1)
# Ambiente:

- Labirinto em grade 7×7 com paredes e pastilhas.
- 1 fantasma que se move ao acaso (ambiente estocástico).
- Fim do episódio: o Pac-Man é pego ou come todas as pastilhas.
  Estado

# Estado: 

- s = (posição do Pac-Man, posição do fantasma, pastilhas restantes).
- O estado é markoviano: contém tudo o que importa para decidir a próxima ação, então o histórico de jogadas é desnecessário.

# Ações: 

- A quantidade de ações disponíveis para o agente tomar são 5 ações: cima, baixo, esquerda, direita e parar. Mover contra uma parede deixa o Pac-Man no mesmo lugar.

# Recompensas: 

- Eventos e recompensas:
- Comer uma pastilha = + 10
- Cada passo dado = -1 (incentiva o agente a ser o mais rapido possível e não desperdiçando passos em rotas ruins, quanto mais ele demorar para chegar nas "gomas" mais penalidades ele irá tomar, fazendo com que aprenda a prgar rotas mais curtas e úteis para                               alcançar o objetivo).
- comer todas as pastilhas(vitória) = +500 (serve para o agente aprender que ser pego pelo fantasma é o pior resultado possível, algo a evitar mesmo que isso custe gomas).
- ser pego pelo fantasma(derrota) = -500

- Os valores são propostas iniciais e podem ser ajustados (reward shaping). O objetivo do agente é maximizar o retorno acumulado, com fator de desconto γ.

# Referências: 

- Pac-Man Projects, UC Berkeley CS188: https://inst.eecs.berkeley.edu/~cs188/archive/fa22/projects/
- Sutton, R. S.; Barto, A. G. Reinforcement Learning: An Introduction. 2ª ed. MIT Press, 2018.
