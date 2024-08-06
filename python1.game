import random

random_number = str(random.randint(0, 999)).zfill(3)
print(random_number)
chance = 0

while chance < 10:
    user_guess = input("Guess a number between 0 and 999: ").zfill(3)

    if user_guess == random_number:
        print("Well DONE.")
        break

    correct_positions = sum(1 for i in range(3) if user_guess[i] == random_number[i])
    correct_digits = sum(min(user_guess.count(x), random_number.count(x)) for x in set(user_guess))

    if len(user_guess) == 1:
        percentage = 100 if correct_digits > 0 else 0
    elif len(user_guess) == 2:
        if correct_digits == 1 and correct_positions == 0:
            percentage = 25
        elif correct_digits == 1 and correct_positions == 1:
            percentage = 50
        elif correct_digits == 2:
            percentage = 100
        else:
            percentage = 0
    elif len(user_guess) == 3:
        if correct_positions > 0:
            percentage = (correct_positions / 3) * 100
        else:
            percentage = (correct_digits / 3) * 100

    print(f"Percent: {percentage:.0f}%")

    chance += 1

if chance == 10:
    print("Your chances are over. The correct answer is:")
    print(random_number)
