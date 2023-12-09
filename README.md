A = [[' ', '1-', '2-', '3-', '4-', '5-', '6-', '7-', '8-'],
     ['1-', 'п1', 'п1', 'п1', 'п1', 'п1', 'п1', 'п1', 'п1'],
     ['2-', 'п1', 'п1', 'п1', 'п1', 'п1', 'п1', 'п1', 'п1'],
     ['3-', '--', '--', '--', '--', '--', '--', '--', '--'],
     ['4-', '--', '--', '--', '--', '--', '--', '--', '--'],
     ['5-', '--', '--', '--', '--', '--', '--', '--', '--'],
     ['6-', '--', '--', '--', '--', '--', '--', '--', '--'],
     ['7-', 'п2', 'п2', 'п2', 'п2', 'п2', 'п2', 'п2', 'п2'],
     ['8-', 'п2', 'п2', 'п2', 'п2', 'п2', 'п2', 'п2', 'п2']]
b = 2

while True:
    for i in range(9):
        for x in range(9):
            print(A[i][x], end=' ')     
        print('')
    if b % 2 == 0:
        player_1_y_X_Откуда = int(input('Откуда: строка первый игрок: '))
        player_1_x_X_Откуда = int(input('Откуда: столбик первый игрок: '))
        player_1_y_X_Куда = int(input('Куда: строка первый игрок: '))
        player_1_x_X_Куда = int(input('Куда: столбик первый игрок: '))
        while (player_1_y_X_Куда == 1 or A[player_1_y_X_Куда][player_1_x_X_Куда] == 'п1' or A[player_1_y_X_Куда][
            player_1_x_X_Куда] == 'п2'
               or player_1_y_X_Куда <= player_1_y_X_Откуда or abs(player_1_x_X_Куда - player_1_x_X_Откуда) > 1):
            print('Ход недопустим. Попробуйте снова.')
            player_1_y_X_Откуда = int(input('Откуда: строка первый игрок: '))
            player_1_x_X_Откуда = int(input('Откуда: столбик первый игрок: '))
            player_1_y_X_Куда = int(input('Куда: строка первый игрок: '))
            player_1_x_X_Куда = int(input('Куда: столбик первый игрок: '))

        A[player_1_y_X_Куда][player_1_x_X_Куда] = A[player_1_y_X_Откуда][player_1_x_X_Откуда]
        A[player_1_y_X_Откуда][player_1_x_X_Откуда] = '--'
        for i in range(9):
            for x in range(9):
                print(A[i][x], end=' ')
            print('')
        print(
            f"player 1 походил из ({player_1_y_X_Откуда}, {player_1_x_X_Откуда}) в ({player_1_y_X_Куда}, {player_1_x_X_Куда})")
    else:
        player_2_y_X_Откуда = int(input('Откуда: строка второй игрок: '))
        player_2_x_X_Откуда = int(input('Откуда: столбик второй игрок: '))
        player_2_y_X_Куда = int(input('Куда: строка второй игрок: '))
        player_2_x_X_Куда = int(input('Куда: столбик второй игрок: '))
        while (player_2_y_X_Куда == 8 or A[player_2_y_X_Куда][player_2_x_X_Куда] == 'п2' or A[player_2_y_X_Куда][
            player_2_x_X_Куда] == 'п1'
               or player_2_y_X_Куда >= player_2_y_X_Откуда or abs(player_2_x_X_Куда - player_2_x_X_Откуда) > 1):
            print('Ход недопустим. Попробуйте снова.')
            player_2_y_X_Откуда = int(input('Откуда: строка второй игрок: '))
            player_2_x_X_Откуда = int(input('Откуда: столбик второй игрок: '))
            player_2_y_X_Куда = int(input('Куда: строка второй игрок: '))
            player_2_x_X_Куда = int(input('Куда: столбик второй игрок: '))

        A[player_2_y_X_Куда][player_2_x_X_Куда] = A[player_2_y_X_Откуда][player_2_x_X_Откуда]
        A[player_2_y_X_Откуда][player_2_x_X_Откуда] = '--'
        for i in range(9):
            for x in range(9):
                print(A[i][x], end=' ')
            print('')
        print(
            f"player 2 походил из ({player_2_y_X_Откуда}, {player_2_x_X_Откуда}) в ({player_2_y_X_Куда}, {player_2_x_X_Куда})")
    b += 1
