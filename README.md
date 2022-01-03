# ROCK-PAPER-SCISSOR-GAME
#include<iostream>
#define player1_win 1
#define player2_win 2
#define ROCK 1
#define PAPER 2
#define SCISSOR 3
#define DRAW 0

using namespace std;
int compare(int p1,int p2){
    int result;
    if ((p1 == PAPER && p2 == ROCK) || (p1 == SCISSOR && p2 == PAPER) || (p1 == ROCK && p2 == SCISSOR))
    {
         result = player1_win;
    }
     else if(( p1==ROCK && p2==PAPER) || (p1==PAPER && p2==SCISSOR)|| ( p1==SCISSOR && p2==ROCK))
     {
          result = player2_win;
     }
     else {
     cout<<"Draw";
    }
    return result;
}

int main(){
    int player1_score=0;
    int player2_score=0;
    
    int p1, p2;
    char ch[10];
    do{
    cout << "Enter 1 for rock" << endl;
    cout << "Enter 2 for paper" << endl;
    cout << "Enter 3 for Scissor" << endl;
    int round = 1;
    while (round < 4)
    {
        cout << "Round " << round <<endl;
        cout << "-----------------------------"<<endl;
        cout << "Enter player 1 choice: ";
        cin >> p1;
        if (p1<=0 || p1>3){
            cout << "Sorry, wrong input"<<endl;
            continue;
        }        
        
        cout << "Enter player 2 choice: " ;
        cin >> p2;
        if (p2<=0 || p2>3){
            cout << "Sorry, wrong input"<<endl;
            continue;
        }
        
        //int round = 0;

        int result = compare(p1, p2);

        if (result == player1_win)
        {
            cout <<"Winner: "<< "player 1 wins"<<endl;
            player1_score++;
        } else if(result==player2_win){
            cout << "Winner: "<<"player 2 wins"<<endl;
            player2_score++;
        }
        else {
            cout<<"invalid";
        }
        cout << "---------------" << endl;
        

        round++;


        
    }

    cout << "Final Score"<<endl;
    cout << " ------------------------"<<endl;
    cout << "|"<< "    P 1    " << "|"<< "    P 2     "<<"|"<<endl;
    cout << "-------------------------"<<endl;
    cout << "|      "  <<player1_score<<"    |     "<<player2_score <<"      |"<<endl;
    cout << "-------------------------"<<endl;
    if (player1_score > player2_score)
    {
        cout << "Player 1 wins"<<endl;
    }
    else if(player2_score>player1_score)
        cout << "player 2 wins"<<endl;

    else{
        cout << "Draw"<<endl; 
    }
    
        cout << "Do you want to terminate? (y/n)" << endl;
        cin >> ch;

    } while (ch[0]=='n');

    return 0;
}
