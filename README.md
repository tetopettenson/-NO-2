# -NO-2
import numpy as np
import random

# プレイヤーのビンゴボード生成
Bingo_board = np.zeros((5, 5), dtype=object)
numbers = list(range(1, 76))
random.shuffle(numbers)

for i in range(5):
    for j in range(5):
        if i == 2 and j == 2:
            Bingo_board[i, j] = "★"
        else:
            Bingo_board[i, j] = numbers.pop()

print(f'あなたのカードです！\n{Bingo_board}')

cpu = input("VScpu?/yes or no/")

if cpu == "yes":
    # CPUのビンゴボード生成
    Bingo_board2 = np.zeros((5, 5), dtype=object)
    numbers2 = list(range(1, 76))
    random.shuffle(numbers2)

    for i in range(5):
        for j in range(5):
            if i == 2 and j == 2:
                Bingo_board2[i, j] = "★"
            else:
                Bingo_board2[i, j] = numbers2.pop()

    print(f"CPUのビンゴボードです！\n{Bingo_board2}")