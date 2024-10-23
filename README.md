# number_guessing
number guessing game written in Python.

It picks a random number from 1 to 100 and then let's the user guess the number. Each time user is getting a hint if hers/his guess was too high or too low. This way user is able to get a sense of which direction to follow next :sweat_smile:. The first prompt about the difficulty level is aimed to assign the amount of guesses: either 5 or 10.

## Intro

Yet another project coming from [100 Days of Code: The Complete Python Pro Bootcamp](https://www.udemy.com/course/100-days-of-code/?utm_source=adwords&utm_medium=udemyads&utm_campaign=Search_DSA_Alpha_Prof_la.EN_cc.ROW-English&campaigntype=Search&portfolio=ROW-English&language=EN&product=Course&test=&audience=DSA&topic=Python&priority=Alpha&utm_content=deal4584&utm_term=_._ag_162511578924_._ad_696197165262_._kw__._de_c_._dm__._pl__._ti_aud-2268488108799%3Adsa-1705455366924_._li_9061062_._pd__._&matchtype=&gad_source=1&gclid=Cj0KCQjwmt24BhDPARIsAJFYKk1n_RKZqRozrq50JSKKd9kj96AGmaDbbhZsI_oAjqboOmuLYrjKTlMaAjqoEALw_wcB&couponCode=2021PM20) 

<br/>New functionalities in scope:
- None - just practicing all of the concepts learned earlier 

#100daysofcode

```python
import random

secret_number = random.choice(range(1, 101))
difficulty = ""
is_game_over = False
current_attempts = 0
start_attempts = 0

print("Welcome to the Number Guessing Game! \nI'm thinking of a number between 1 and 100.")
#Test code
#print(f"Pssst, the correct answer is {secret_number}")
difficulty = input("Choose a difficulty. Type 'easy' or 'hard':").lower()

if difficulty == "easy":
    start_attempts = 10
elif difficulty == "hard":
    start_attempts = 5
else:
    print("Invalid input")
    exit()

current_attempts = start_attempts

def decrease_attempts(current_attempts):
    return current_attempts - 1

def attempts_status(current_attempts):
    print(f"You have {current_attempts} attempts remaining to guess the number.")

while not is_game_over and current_attempts > 0:
    attempts_status(current_attempts)
    guess = int(input("Make a guess: "))

    if guess != secret_number:
        current_attempts = decrease_attempts(current_attempts)
        if guess < secret_number:
            print("Too low.\nGuess again.")
        elif guess > secret_number:
            print("Too high.\nGuess again.")
    else:
        print(f"You got it! The answer was {secret_number}.")
        is_game_over = True

    if current_attempts == 0:
        print("You lost!")
        is_game_over = True
```
