
board = [["-", "-", "-"], ["-", "-", "-"], ["-", "-", "-"]]


for turns in range(9):
    if turns % 2 == 0:
        print("turno jugador uno")      
    else:
        print("turno jugador dos")
    row = int(input("Introduzca fila; "))
    column = int(input("Introduzca una columna; "))
    if turns % 2 == 0:
        board[row-1][column-1] = "X"
    else:
        board[row-1][column-1] = "O"
    for row in board:
        print(row)
    
