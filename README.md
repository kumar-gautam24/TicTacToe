<h1 align="center"> Tic Tac Toe </h1> <br>





## Introduction

Simple Tic Tac Toe game : it uses, hive for local database, minimax algorithm for AI in single player mode,
multiplayer is meant to be played among two players offline.
RiverPod  for state management.


## MiniMax Algo


int minimax(List<List<String>> board, bool isMaximizing) {
    if (checkWin(board, 'O')) {
    return 1;
} else if (checkWin(board, 'X')) {
    return -1;
} else if (checkDraw(board)) {
    return 0;
}

if (isMaximizing) {
    int bestScore = -1000;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (board[i][j].isEmpty) {
                board[i][j] = 'O';
                int score = minimax(board, false);
                board[i][j] = '';
                bestScore = max(score, bestScore);
        }
    }
}
    return bestScore;
} else {
    int bestScore = 1000;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (board[i][j].isEmpty) {
            board[i][j] = 'X';
            int score = minimax(board, true);
            board[i][j] = '';
            bestScore = min(score, bestScore);
        }
    }
}
        return bestScore;
    }
}
![Screenshot_2024-06-14-13-58-26-12_027a076a3654661bf7a847856e46c730](https://github.com/kumar-gautam24/TicTacToe/assets/80573770/64d9d699-db14-4562-8595-d7bcfb7cc8a8)    ![Screenshot_2024-06-14-13-58-33-41_027a076a3654661bf7a847856e46c730](https://github.com/kumar-gautam24/TicTacToe/assets/80573770/bcc88c36-8ed5-4890-b764-b8189af7a3ab)    ![Screenshot_2024-06-14-13-57-04-61_027a076a3654661bf7a847856e46c730](https://github.com/kumar-gautam24/TicTacToe/assets/80573770/64392c4e-6f00-4e6d-929d-4863e2324f06)

![Screenshot_2024-06-14-13-57-47-85_027a076a3654661bf7a847856e46c730](https://github.com/kumar-gautam24/TicTacToe/assets/80573770/f2f6a6bc-c155-47ad-9ba8-617a60bc611b)   ![Screenshot_2024-06-14-13-58-02-94_027a076a3654661bf7a847856e46c730](https://github.com/kumar-gautam24/TicTacToe/assets/80573770/24485715-fe34-4225-a883-cbe156e3af97)



