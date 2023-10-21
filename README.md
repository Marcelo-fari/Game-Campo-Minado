# Game-Campo-Minado
Campo Minado Em Python

# Campo Minado
importrandom, time, copy

WIDTH = 10
HEIGHT = 10
BOMBS = 10

# Cria a lista de celulas do jogo (escondidas):
hiddenCells = []
for x in range(WIDTH):
column = [] # Cria uma coluna.
    for y in range(HEIGHT):
column.append('.') # Adiciona uma celula.
hiddenCells.append(column) # hiddenCells é uma lista de colunas.

# Inseri as bombas embaralhadas dentro da matrixhiddenCells
while BOMBS > 0:
xRandom = random.randint(0, WIDTH-1)
yRandom = random.randint(0, HEIGHT-1)
ifhiddenCells[xRandom][yRandom] == '.':
hiddenCells[xRandom][yRandom] = '#'
        BOMBS -= 1

# Verifica o numero que será inserido em cada celula baseado na quantidade de bombas proximas
for x in range(WIDTH):
    for y in range(HEIGHT):
leftCoord = (x - 1)
rightCoord = (x + 1)
aboveCoord = (y - 1)
belowCoord = (y + 1)

        # Conta o numero de bombas vizinhas a celula:
numNeighbors = 0
ifaboveCoord>= 0:
ifleftCoord>= 0:
ifhiddenCells[leftCoord][aboveCoord] == '#':
numNeighbors += 1 # Lado superior esquerdo tem bomba.
ifhiddenCells[x][aboveCoord] == '#':
numNeighbors += 1 # Lado esquerdo tem bomba.
ifrightCoord< 10:
ifhiddenCells[rightCoord][aboveCoord] == '#':
numNeighbors += 1 # Lado superior direito tem bomba.
ifleftCoord>= 0:
ifhiddenCells[leftCoord][y] == '#':
numNeighbors += 1 # Lado esquerdo tem bomba.
ifrightCoord< 10:
ifhiddenCells[rightCoord][y] == '#':
numNeighbors += 1 # Lado direito tem bomba.

ifbelowCoord< 10:
ifleftCoord>= 0:
ifhiddenCells[leftCoord][belowCoord] == '#':
numNeighbors += 1 # Lado inferior esquerdo tem bomba.
ifhiddenCells[x][belowCoord] == '#':
numNeighbors += 1 # Lado inferior tem bomba.
ifrightCoord< 10:
ifhiddenCells[rightCoord][belowCoord] == '#':
numNeighbors += 1 # Lado inferior direito tem bomba.
ifhiddenCells[x][y] == '.':
hiddenCells[x][y] = str(numNeighbors)

# Cria a lista de celulas do jogador, inicialmente todas vazias (com '.')
playerCells = []
for x in range(WIDTH):
column = [] # Cria uma coluna.
    for y in range(HEIGHT):
column.append('.') # Adiciona um '.'.
playerCells.append(column) # playerCells é uma lista de colunas.



whileTrue: # Loop principal.
    print('\n\n\n\n\n') # Separa cada jogada pulando as linhas.
    # Mostra a matrixplayerCells na tela:
    for y in range(HEIGHT):
        for x in range(WIDTH):
            print(playerCells[x][y], end='') # Mostra a matrix das jogadas realizadas pelo jogador.
print() # Muda de linha ao término de cada linha.
    print('\n')

    # Aguarda a seleção do jogador para a posição X e Y
    print ("digite um numero de coluna para testar")
xPosition = int(input())-1
    print ("digite um numero de linha para testar")
yPosition = int(input())-1
print("A celula que voce escolheu tem...")
time.sleep(0.5)
    print(hiddenCells[xPosition][yPosition])
print()

    # Verifica se pisou em uma bomba:
ifhiddenCells[xPosition][yPosition] == '#':
print("\nVoce pisou em uma Bomba!!!\n")
        for y in range(HEIGHT):
            for x in range(WIDTH):
                print(hiddenCells[x][y], end='') # Mostra todo o tabuleiro.
print()
        print('\n')
        #break
elifplayerCells[xPosition][yPosition] != hiddenCells[xPosition][yPosition]: # Se não pisou em bomba e ainda não selecionou esta celula
playerCells[xPosition][yPosition] = hiddenCells[xPosition][yPosition] # Salva a posição da celula na matrix do jogador
else: # Caso selecione uma celula que já foi selecionada anteriormente
print("Voceja escolheu esta celula")

