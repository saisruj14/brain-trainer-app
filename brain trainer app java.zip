package com.example.exerciseyourbrain;
import androidx.appcompat.app.AppCompatActivity;
import androidx.gridlayout.widget.GridLayout;
import android.os.Bundle;
import android.os.CountDownTimer;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;
public class MainActivity extends AppCompatActivity {
Button playbutton,playagain;
GridLayout gridLayout;
TextView score,timer,question,answer;
Button button1,button2,button3,button4;
CountDownTimer countDownTimer;
int[] arr = new int[20];
boolean click=false;
int a,b;
int score_num=0;
int numofques=0;
public int getRandomNumber(int min, int max) {
return (int) ((Math.random() * (max - min)) + min);
}
public void timerFunc(){
countDownTimer=new CountDownTimer(30100,1000){
@Override
public void onTick(long l) {
timer.setText(Integer.toString((int)l/1000)+" s");
}
@Override
public void onFinish() {
answer.setText("DONE!!");
answer.setVisibility(View.VISIBLE);
playagain.setVisibility(View.VISIBLE);
click=true;
}
}.start();
}
}
public void startGame(){
click=false;
playagain.setVisibility(View.INVISIBLE);
a=getRandomNumber(1,20);
b=getRandomNumber(1,20);
question.setText("Question:
"+Integer.toString(a)+"+"+Integer.toString(b));
int pos_right=getRandomNumber(0,3);
for(int i=0;i<4;i++){
if(i==pos_right){
arr[i]=a+b;
}
else
{
int wrong=getRandomNumber(1,41);
while(wrong==(a+b)){
wrong=getRandomNumber(1,41);
}
arr[i]=wrong;
}
}
button1.setText(Integer.toString(arr[0]));
button2.setText(Integer.toString(arr[1]));
button3.setText(Integer.toString(arr[2]));
button4.setText(Integer.toString(arr[3]));
}
public void playGame(View view){
playbutton.setVisibility(View.INVISIBLE);
score.setVisibility(View.VISIBLE);
timer.setVisibility(View.VISIBLE);
question.setVisibility(View.VISIBLE);
gridLayout.setVisibility(View.VISIBLE);
startGame();
timerFunc();
}
public void correctAns(View view){
numofques++;
if(!click) {
int val = Integer.parseInt(view.getTag().toString());
if (arr[val - 1] == (a + b)) {
answer.setText("CORRECT");
answer.setVisibility(View.VISIBLE);
score_num++;
} else {
answer.setText("INCORRECT");
answer.setVisibility(View.VISIBLE);
}
click=true;
score.setText(Integer.toString(score_num)+"/"+Integer.toString(num
ofques));
startGame();
}
}
@Override
protected void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.activity_main);
playbutton=findViewById(R.id.playbutton);
score=findViewById(R.id.score);
timer=findViewById(R.id.timer);
question=findViewById(R.id.question);
answer=findViewById(R.id.answer);
gridLayout=(androidx.gridlayout.widget.GridLayout)findViewById(R.id.gr
idLayout);
playagain=findViewById(R.id.playagain);
button1=findViewById(R.id.button1);
button2=findViewById(R.id.button2);
button3=findViewById(R.id.button3);
button4=findViewById(R.id.button4);
score.setVisibility(View.INVISIBLE);
timer.setVisibility(View.INVISIBLE);
question.setVisibility(View.INVISIBLE);
gridLayout.setVisibility(View.INVISIBLE);
answer.setVisibility(View.INVISIBLE);
}
}

