# practical-works-python

def guess_number_game():
    """
    A number guessing game where the computer guesses a number
    thought of by the user using the bisection method.
    """
    print("Привіт! Давай зіграємо в гру вгадай число.")
    n = int(input("Задай верхню межу для загаданого числа (наприклад, 100): "))

    print(f"Загадай ціле число від 1 до {n}. Натисни Enter, коли будеш готовий.")
    input()

    low = 1
    high = n
    guesses = 0

    while True:
        guesses += 1
        guess = (low + high) // 2
        print(f"Мій здогад: {guess}")

        response = input("Це твоє число? (так/більше/менше): ").lower()

        if response == "так":
            print(f"Ура! Я вгадав твоє число за {guesses} спроб!")
            break
        elif response == "більше":
            low = guess + 1
        elif response == "менше":
            high = guess - 1
        else:
            print("Будь ласка, відповідай 'так', 'більше' або 'менше'.")

        if low > high:
            print("Здається, ти помилився у відповідях. Спробуй ще раз.")
            break

if __name__ == "__main__":
    guess_number_game()
