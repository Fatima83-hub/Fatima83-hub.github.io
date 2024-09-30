flowchart TD
    Start([Start Game]) -->|Generate Random Number| GenerateNum[Generate Random Number within Range]
    GenerateNum --> AskInput[Prompt User for Guess]
    
    AskInput -->|Check if Input is Numeric| CheckInput{Is input valid?}
    CheckInput -->|No| InvalidInput[Display Error: Not a number] --> AskInput
    CheckInput -->|Yes| CheckRange{Is input within range?}
    
    CheckRange -->|No| OutOfRange[Display Error: Out of Range] --> AskInput
    CheckRange -->|Yes| EvaluateGuess[Check if Guess is Correct]
    
    EvaluateGuess -->|Too High| TooHigh[Display "Too High"] --> AskInput
    EvaluateGuess -->|Too Low| TooLow[Display "Too Low"] --> AskInput
    EvaluateGuess -->|Correct| CorrectGuess[Display "Correct! You Win"]
    
    CorrectGuess --> EndGame[End Game]
    TooHigh --> AskInput
    TooLow --> AskInput

    Start Game: The game starts by generating a random number within a right range ( 1 to 100).

Generate Random Number: The game generates a random number that the player must guess.

Ask User to Guess: The user is prompted to input a guess.

Check if Input is Valid:

    If the input is not a valid number, the user will see an error message and will be asked to guess again.
    If the input is valid, it proceeds to check if it is within the correct range.

Check if Input is within Range:

    If the input is out of the range, the user will see an error message and will asked to guess again.
    If the input is within range, the game evaluates the guess.

Evaluate the Guess:

    If the guess is too high, the game gives feedback "Too High" and will aske the user to guess again.
    If the guess is too low, the game gives feedback "Too Low" and asks the user to guess again.
    If the guess is correct, the game congratulates the user with the message "Correct! You Win".

End Game: Once the correct guess is made, the game ends.
