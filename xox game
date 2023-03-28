# Tahtayı ve sembollerin tanımlanması
board = [' ' for i in range(9)]
player_symbol = 'X'
computer_symbol = 'O'

# Tahtanın çizilmesi
def print_board():
    row1 = '|'.join(board[0:3])
    row2 = '|'.join(board[3:6])
    row3 = '|'.join(board[6:9])
    print(row1)
    print('-'*5)
    print(row2)
    print('-'*5)
    print(row3)

# Kullanıcının hamlesini alması
def player_move():
    while True:
        move = input('Hangi kareye hamle yapmak istiyorsunuz? (1-9): ')
        try:
            move = int(move) - 1
            if move < 0 or move > 8:
                print('Lütfen geçerli bir kare numarası girin.')
            elif board[move] != ' ':
                print('Bu kare dolu. Lütfen başka bir kare seçin.')
            else:
                board[move] = player_symbol
                break
        except ValueError:
            print('Lütfen geçerli bir sayı girin.')

# Bilgisayarın hamlesinin belirlenmesi
def computer_move():
    available_moves = [i for i, x in enumerate(board) if x == ' ']
    if len(available_moves) > 0:
        move = available_moves[0]
        board[move] = computer_symbol

# Kazananın belirlenmesi
def check_win(symbol):
    if board[0] == symbol and board[1] == symbol and board[2] == symbol:
        return True
    if board[3] == symbol and board[4] == symbol and board[5] == symbol:
        return True
    if board[6] == symbol and board[7] == symbol and board[8] == symbol:
        return True
    if board[0] == symbol and board[3] == symbol and board[6] == symbol:
        return True
    if board[1] == symbol and board[4] == symbol and board[7] == symbol:
        return True
    if board[2] == symbol and board[5] == symbol and board[8] == symbol:
        return True
    if board[0] == symbol and board[4] == symbol and board[8] == symbol:
        return True
    if board[2] == symbol and board[4] == symbol and board[6] == symbol:
        return True
    return False

# Oyunun ana döngüsü
while True:
    print_board()
    player_move()
    if check_win(player_symbol):
        print_board()
        print('Tebrikler, kazandınız!')
        break
    computer_move()
    if check_win(computer_symbol):
        print_board()
        print('Üzgünüm, bilgisayar kazandı.')
        break
    if ' ' not in board:
        print_board()
        print('Berabere!')
        break
