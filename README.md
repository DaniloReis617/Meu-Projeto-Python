# Meu-Projeto-Python
Projeto de graficos animados criados com python.
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.animation import FuncAnimation

# Dados para a animação
dados = np.random.randint(0, 100, (20, 10))

# Criando a figura
fig, ax = plt.subplots()

# Criando a barra inicial
barra = ax.bar(range(len(dados[0])), dados[0])

# Função de animação
def animacao(i):
    for j, b in enumerate(barra):
        b.set_height(dados[i, j])

# Criando a animação
anim = FuncAnimation(fig, animacao, frames=len(dados), interval=100)

# Mostrando a animação
plt.show()
