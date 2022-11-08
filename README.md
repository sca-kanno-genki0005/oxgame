# oxgame
#include <iostream>
#include <string>
#include <vector>
#include <algorithm>
using namespace std;
/*int main() {
  //declare a pointer
  //ポインタを宣言する
  int* pAPoint;

  //ポインタの宣言と初期化
  int* pScore = 0;

  int score = 1000;

  //score変数のアドレスをポインタpScoreに代入する
  pScore = &score;

  //&scoreをpScoreに代入
  cout << "Assigning &score to pScore\n";
  //scoreの変数のアドレスは
  cout << "&score is: " << &score << "\n";
  //pScoreに格納されたアドレスは
  cout << "pScore is: " << pScore << "\n";
  cout << "score is: " << score << "\n";
  //ポインタに指された値
  cout << "*pScore is: " << *pScore << "\n\n";
  //500をscoreに足す
  cout << "Adding 500 to score\n";
  score += 500;
  cout << "score is: " << score << "\n";
  cout << "*pScore is: " << *pScore << "\n\n";

  //*pScoreに500を足す
  cout << "Adding 500 to *pScore\n";
  *pScore += 500;
  cout << "score is: " << score << "\n";
  cout << "*pScore is: " << *pScore << "\n\n";

  //&newScoreをpScoreに代入する
  cout << "Assigning &newScore to pScore\n";
  int newScore = 5000;
  pScore = &newScore;
  cout << "&newScore is:" << &newScore << "\n";
  cout << "pScore is: " << pScore << "\n";
  cout << "newScore is: " << newScore << "\n";
  cout << "*pScore is: " << *pScore << "\n\n";

  //&strをpStrに代入する
  cout << "Assigning &str to pStr\n";
  string str = "score";
  string* pStr = &str;
  cout << "str is: " << str << "\n";
  cout << "*pStr is: " << *pStr << "\n";
  cout << "(*pStr).size() is: " << (*pStr).size() << "\n";
  cout << "pStr->size() is: " << pStr->size() << "\n";
  return 0;
}*/

/*void badSwap(int x, int y);
void goodSwap(int* const pX, int* const pY);

int main()
{
  int myScore = 150;
  int yourScore = 1000;
  cout << "Original values\n";//元々の値
  cout << "myScore: " << myScore << "\n";
  cout << "yourScore: " << yourScore << "\n\n";

  cout << "Calling badSwap()\n";
  badSwap(myScore, yourScore);
  cout << "myScore: " << myScore << "\n";
  cout << "yourScore: " << yourScore << "\n\n";

  cout << "Calling goodSwap()\n";
  goodSwap(&myScore, &yourScore);
  cout << "myScore: " << myScore << "\n";
  cout << "yourScore: " << yourScore << "\n";

  return 0;
}

void badSwap(int x, int y)
{
  int temp = x;
  x = y;
  y = temp;
}

void goodSwap(int* const pX, int* const pY)
{
  //pXに指されている値をtempに格納
  int temp = *pX;
  //pyに指されている値をpXが差しているアドレスに格納する
  *pX = *pY;
  //もともとpXに指されていた値をpYが差しているアドレスに格納する
  *pY = temp;
}*/

/*string* ptrToElement(vector<string>* const pVec, int i);

int main()
{
  vector<string> inventory;
  inventory.push_back("sword");
  inventory.push_back("armor");
  inventory.push_back("shield");

  //返されたポインタが文字列オブジェクトを指している
  cout << "Sending the objected pointed to by returned pointer:\n";
  cout << *(ptrToElement(&inventory, 0)) << "\n\n";

  //返されたポインタを別のポインタに代入--オーバーヘッドが少ない
  cout << "Assigning the returned pointer to another pointer.\n";
  string* pStr = ptrToElement(&inventory, 1);
  //新しいポインタに指された文字列オブジェクトをcoutに送信
  cout << "Sending the object pointer to by new pointer to cout:\n";
  cout << *pStr << "\n\n";

  //文字列オブジェクトをコピー　--　オーバーヘッドが大きい
  cout << "Assigning object pointed by pointer to a string object.\n";
  string str = *(ptrToElement(&inventory, 2));
  //新しいポインタに指された文字列オブジェクトをcoutに送信
  cout << "Sending the new string object to cout:\n";
  cout << str << "\n\n";

  //返されたポインタで文字列オブジェクトをcoutに送信
  cout << "Altering an object through a returned pointer\n";

  *pStr = "Healting potion";

  cout << "Sending the altered object to cout:\n";
  cout << inventory[1] << endl;

  return 0;
}
string* ptrToElement(vector<string>* const pVec, int i)
{
  //pVecに指されているベクトルの要素iのアドレスを返す
  return &((*pVec)[i]);
}*/

/*void increase(int* const array, const int NUM_ELEMENTS);
void display(const int* const array, const int NUM_ELEMENTS);

int main()
{
  cout << "Creating an array of high scores.\n\n";
  const int NUM_SCORES = 3;
  int highScores[NUM_SCORES] = {5000, 3500, 2700};

  cout << "Displaying scores using array name as a constant pointer.\n";
  cout << *highScores << endl;
  cout << *(highScores + 1) << endl;
  cout << *(highScores + 2) << "\n\n";
  
  cout << "Increasing score by passing array as a constant pointer.\n\n";
  increase(highScores, NUM_SCORES);

cout << "Displaying scores by passing array as a constant pointer to a";
  cout << " constant.\n";
  display(highScores, NUM_SCORES);
  return 0;
}
void increase(int* const array, const int NUM_ELEMENTS)
{
  for (int i = 0; i < NUM_ELEMENTS; ++i)
    {
      array[i] += 500;
    }
}
void display(const int* const array, const int NUM_ELEMENTS)
{
  for (int i = 0; i < NUM_ELEMENTS; ++i)
    {
      cout << array[i] << endl;
    }
}*/

//グローバル定数
//global constants
const char X ='X';
const char O ='O';
const char EMPTY =' ';
const char TIE ='T';
const char NO_ONE ='N';
//関数プロトタイプ
//function prototypes
void instructions();
char askYesNo(string question);
int askNumber(string question,int high,int low=0);
char humanPiece();
char opponent(char piece);
void displayBoard(const vector<char>&board);
char winner(const vector<char>&board);
bool isLegal(const vector<char>&board,int move);
int humanMove(const vector<char>&board,char human);
int computerMove(vector<char>board,char computer);
void announceWinner(char winner,char computer,char human);
int main()
{
  int move;const int NUM_SQUARES =9;
  vector<char>board(NUM_SQUARES, EMPTY);
  instructions();
  char human =humanPiece();
  char computer =opponent(human);
  char turn = X;displayBoard(board);
  while(winner(board)== NO_ONE)
  {
    if(turn == human)
    {
      move =humanMove(board, human);
      board[move]= human;
      }else{
      move =computerMove(board, computer);
      board[move]= computer;
      }
    displayBoard(board);
    turn =opponent(turn);
  }
  announceWinner(winner(board), computer, human);
  return 0;
}

void instructions()
{
  //三目並べ：人間対AI
  cout <<"Welcome to the ultimate man-machine showdown: Tic-Tac-Toe.\n";
  //人間の脳がシリコン・プロセッサーと対戦する。
  cout <<"--where human brain is pit against silicon processor\n\n";
  //0〜8の数字を入力する。
  cout <<"Make your move known by entering a number, 0-8. The number\n";//数字は下記のように盤の位置を示す。
  cout <<"corresponds to the desired board position, as illustrated:\n\n";
  cout <<"0 | 1 | 2\n";
  cout <<"3 | 4 | 5\n";
  cout <<"6 | 7 | 8\n\n";
  //人間、準備せよ。戦いが始まる。
  cout <<"Prepare yourself, human. The battle is about to begin.\n\n";}
char askYesNo(string question)
{
  char response;
  do{
    cout << question <<"(y/n): ";
    cin >> response;
    }while(response !='y'&& response !='n');
  
  return response;
}
int askNumber(string question,int high,int low)
{
  int number;
  do
  {
    cout << question <<"("<< low <<"- "<< high <<"): ";
    cin >> number;
  }while(number > high || number < low);return number;
}

char humanPiece(){//先攻になる必要ある？
  char go_first =askYesNo("Do you require the first move?");
  if(go_first =='y'){
    //先攻どうぞ。どうせ負ける
  cout <<"\nThen take the first move. You will need it.\n";
    return X;
    }
  else{
    //なんて勇敢さ、負けるに決まっている。では、先にやるよ。
    cout <<"\nYour bravery will be your undoing... I will go first.\n";
    return O;
    }
  }
char opponent(char piece)
{
  if(piece == X)
  {
    return O;
  }
  else
  {
    return X;
  }
}
void displayBoard(const vector<char>&board)
{
  cout <<"\n\t"<< board[0]<<"| "<< board[1]<<"| "<< board[2];
  cout <<"\n\t"<<"--------";cout <<"\n\t"<< board[3]<<"| "<< board[4]<<"| "<< board[5];cout <<"\n\t"<<"--------";
  cout <<"\n\t"<< board[6]<<"| "<< board[7]<<"| "<< board[8];cout <<"\n\t"<<"\n\n";
}

char winner(const vector<char>&board)
{  //勝利条件
   //all possible winning rows
  const int WINNING_ROWS[8][3] = { {0,1,2},
                                   {3,4,5},
                                   {6,7,8},
                                   {0,3,6},
                                   {1,4,7},
                                   {2,5,8}, 
                                   {0,4,8},
                                   {2,4,6} };
  const int TOTAL_ROWS =8;
  //いずれかの勝利行に同じ3つの値がある（空じゃない）場合は
  //if any winning row has three values that are the same (and not EMPTY),
  //勝者が決まる
  //then we have a winner
  for(int row =0; row < TOTAL_ROWS;++row)
  {
    if(      (board[WINNING_ROWS[row][0]]!= EMPTY)&&  
             (board[WINNING_ROWS[row][0]]== board[WINNING_ROWS[row][1]])&&
             (board[WINNING_ROWS[row][1]]== board[WINNING_ROWS[row][2]])  )
      {
        return board[WINNING_ROWS[row][0]];
      }
  }

//勝者が出てないので、引き分けであることを確認
//since nobody has won, check for a tie (no empty squares left)
  if (count(board.begin(), board.end(), EMPTY)==0)
    return TIE;
  //勝者が出ていなくて引き分けになっていないので、ゲームオーバーじゃない。
  //since nobody has won and it isn't a tie, the game isn't over
  return NO_ONE;
  }
inline bool isLegal(int move,const vector<char>&board)
{
  return(board[move]== EMPTY);
}
int humanMove(const vector<char>&board,char human)
{
  //次はどうする？
  int move =askNumber("Where will you move?",(board.size()-1));
  while(!isLegal(move, board))
  {
    //愚かな人間め、そのマスはもう埋まっているぞ
    cout <<"\nThat square is already occupied, foolish human.\n";
    //次はどうする？
    move =askNumber("Where will you move?",(board.size()-1));}
  //わかった
  cout <<"Fine...\n";return move;
  }
int computerMove(vector<char>board,char computer)
{
  unsigned int move =0;
  bool found =false;
  //もし次の番AIが勝つならこうする
  //if computer can win on next move, that's the move to make
  while(!found && move < board.size())
  {
    if(isLegal(move, board))
    {
      board[move]= computer;found =winner(board)== computer;board[move]= EMPTY;
    }
    if(!found)
    {
      ++move;
    }
  }

//それとも、もし次の番プレイヤーが勝つならこうする
//otherwise, if human can win on next move, that's the move to make
  if(!found)
  {
    move =0;
    char human =opponent(computer);
    
    while(!found && move < board.size())
    {
      if(isLegal(move, board))
      {
        board[move]= human;
        found =winner(board)== human;
        board[move]= EMPTY;
      }
      
      if(!found)
      {
          ++move;
      }
    }
  }
  //そうではない場合、今空いているマスのうちにもっとも良い選択をする
  //otherwise, moving to the best open square is the move to make
  if (!found)
  {
    move =0;
    unsigned int i =0;
    const int BEST_MOVES[]={4,0,2,6,8,1,3,5,7};
    //もっとも良いマスを決める
    //pick best open square
    while (!found && i < board.size())
    {
      move = BEST_MOVES[i];
      if(isLegal(move, board))
      {
        found =true;
        }
      
      ++i;
      }
    }
  //目のマスを埋めるぞ。
  cout <<"I shall take square number "<< move << endl;
  return move;
  }
void announceWinner(char winner,char computer,char human)
{
  if(winner == computer)
  {
    //が勝った
  cout << winner <<"'s won!\n";
    //思った通り、またオラの勝ちだ。
    cout <<"As I predicted, human, I am triumphant once more -- proof\n";
    //AIは人間より優れていることの証拠だ
    cout <<"that computers are superior to humans in all regards.\n";
    }
  else if(winner == human)
  {
    //が勝った
    cout << winner <<"'s won!\n";
    //うそだ。ありえない。オラ負けるはずがない。騙されたに決まっている。
    cout <<"No, no! It cannot be! Somehow you tricked me, human.\n";
    //もう２度と負けない。絶対にな。
    cout <<"But never again! I, the computer, so swear it!\n";
    }else{
    //引き分けだ
    cout <<"It's a tie.\n";
    //とても運のいい人間だな。引き分けになってくれやがった。
    cout <<"You were most lucky, human, and somehow managed to tie me.\n";
    //祝うといい。引き分け以上になることはないのだ。
    cout <<"Celebrate... for this is the best you will ever achieve.\n";
    }
  }
