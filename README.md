# 20.1.4-assignment-Trivia
Marked


This assignment is not about solving a hard problem. Instead, it is designed to get you to read existing code that uses functions and figure out how it works. In other words, it is about getting comfortable with functions that use parameters before you have to write them yourself.

# Setting up
- Create a new Javascript file using the proper title
- See below for the starter code


## Task 1- Familiarize Yourself with the Code
- Read through the code carefully to see how it is structured.  Look carefully at how the question() and marking() functions are written.
- Test it by answering the first question in a variety of ways.  You will discover that the displayScore() function produces an error.


## Task 2 - Improve the displayScore Function (20%)
- The line text("Current score: " + badvariable, 50, 360); needs to be fixed.  Change it so that it prints the sc variable.  
- Remember that sc is the local variable that stores the score -inside the displayScore function.  

- Alter or add textSize() lines so that the 'Correct' message is printed in large text and the score is printed in somewhat smaller text.


## Task 3 - Change the Theme
- Change the first question to be about a movie/game or some other trivia topic.
- **Optional:** Add text or a ZERO scene that introduces the trivia game.


## Task 4 - Adding the Other Questions
For the rest of this assignment, you are only adding to the keyPressed() function.

- Add 4 additional questions by adding to the keyPressed() function. Each is worth 20%:
- Base each on the code exactly as written for question 1. Find the CODE To COPY comment and paste it under each KeyPress IF statement.
- Each question should have 3 marking levels (IF… ELSE IF… ELSE)
- For the Partially Correct IF statement code, you must use a few different String Functions for full marks (see final 20%)

## Final 20%
- Within your IF statements, you must use all of the following String functions:
  - Includes,		StartsWith,		EndsWith,		CharAt,
  - https://www.w3schools.com/jsref/jsref_obj_string.asp. 

Remember that we used all of these in our Band Name Analyzer example. 
5% for each.

```
let scenenum = 1;
let score = 0;

function setup() {
 createCanvas(600, 400);
 background(0, 255, 0);
 textSize(20);
 
}//end setup

function draw() {
    question(scenenum);
}//end draw

function keyPressed() {
    if (key === '1' && scenenum === 1) {
        scenenum = 2;
        //--------------- Start of code to copy -------------------------------
        let answer = window.prompt("Who is the best teacher");
        
        if(answer === "Mrs. Krabappel"){
            score += 2;
            displayScore("Fully Correct", score);
        } else if (answer.includes("k")){  //this must be altered for each question you add
             score += 1;
            displayScore("Partially Correct", score);
        } else{
             displayScore("Wrong", score);
        }

        //--------------- End of code to copy -------------------------------

    }//end 1

    else if (key === '2' && scenenum === 2) {
        scenenum = 3;

    }//end 2




}//end keyPressed

function displayScore(correct, sc){
    //background box
    fill(255, 255, 0);
    strokeWeight(3);
    stroke(0);
    rect(10, 270, width-20, 120);

    //text
    fill(0)
    noStroke();
    textSize(10);
    text(correct + "!", 50, 315);
    textSize(10);
    text("Current score: " + badvariable, 50, 360);
}

function question(questionNum) {
    //background box
    fill(255, 255, 0);
    strokeWeight(3);
    stroke(0);
    rect(10, 10, width-20, 250);

    //text
    fill(0)
    noStroke();
    text("Question " + questionNum, 50, 100);
    text("Press the " + questionNum + " key to answer this question", 50, 160);
    
}//question
``` 
