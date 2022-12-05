board = [["-", "-", "-"], ["-", "-", "-"], ["-", "-", "-"]]

# Establecemos la cantidad max de turnos, identificamos al jugador 1 y jugador 2
turns = 0
while turns < 9:
    if turns % 2 == 0:
        print("Es el turno del jugador uno")    
    else:
        print("Es el turno del jugador dos")
    row = int(input("Introduzca fila: "))
    column = int(input("Introduzca una columna: "))  
    # Establecemos que de error si se sale del tablero y vuelva a pedir posición
    if row > 3 or column > 3:
        print("Se ha salido del tablero!")
        continue
    # Establecemos que la posción no puede ser re-escrita
    if board[row-1][column-1] != "-":
        print("Esa posición ya fue ocupada previamente")
        continue
    # Declaramos que el primer jugador sea 1 y el segundo jugador 2
    if turns % 2 == 0:
        board[row-1][column-1] = "X"
    else:
        board[row-1][column-1] = "O"
    # Declaramos las condiciones de victoria
    for row in range(3):
        if board[row-1][0] == "X" and board[row-1][1] == "X" and board[row-1][2] == "X":
            print("Ha ganado el jugador 1")
            for row in board:
                print(row)
            exit()
        if board[row-1][0] == "O" and board[row-1][1] == "O" and board[row-1][2] == "O":
            print("Ha ganado el jugador 2")
            for row in board:
                print(row)
            exit()
        if board[row-1][0] == "X" and board[row][1] == "X" and board[row+1][2] == "X":
            print("Ha ganado el jugador 1")
            for row in board:
                print(row)
            exit()
        if board[row-1][2] == "X" and board[row][1] == "X" and board[row+1][0] == "X":
            print("Ha ganado el jugador 1")
            for row in board:
                print(row)
            exit()
        if board[row-1][0] == "O" and board[row][1] == "O" and board[row+1][2] == "O":
            print("Ha ganado el jugador 2")
            for row in board:
                print(row)
            exit()
        if board[row-1][2] == "O" and board[row][1] == "O" and board[row+1][0] == "O":
            print("Ha ganado el jugador 2")
            for row in board:
                print(row)
            exit()
        if board[0][column-1] == "X" and board[1][column-1] == "X" and board[2][column-1] == "X":
            print("Ha ganado el jugador 1")
            for row in board:
                print(row)
            exit()
        if board[0][column-1] == "O" and board[1][column-1] == "O" and board[2][column-1] == "O":
            print("Ha ganado el jugador 2")
            for row in board:
                print(row)
            exit()
        
    for row in board:
        print(row)
    turns += 1

print("Ha habido un empate!")
    
