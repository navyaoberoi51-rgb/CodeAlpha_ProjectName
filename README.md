# CodeAlpha_ProjectName
[hangman.py](https://github.com/user-attachments/files/24637787/hangman.py)
Python 3.14.2 (v3.14.2:df793163d58, Dec  5 2025, 12:18:06) [Clang 16.0.0 (clang-1600.0.26.6)] on darwin
Enter "help" below or click "Help" above for more information.
>>> import random
... 
... # List of predefined words
... word_list = ["python", "coding", "hangman", "intern", "project"]
... 
... # Randomly choose a word
... secret_word = random.choice(word_list)
... 
... # Game variables
... guessed_letters = []
... incorrect_guesses = 0
... max_guesses = 6
... 
... print(" Welcome to Hangman Game!")
... print("You have 6 incorrect guesses allowed.")
... 
... # Create display word with underscores
... display_word = ["_"] * len(secret_word)
... 
... # Game loop
... while incorrect_guesses < max_guesses and "_" in display_word:
...     print("\nWord:", " ".join(display_word))
...     print(f"Incorrect guesses left: {max_guesses - incorrect_guesses}")
...     guess = input("Guess a letter: ").lower()
... 
...     # Input validation
...     if len(guess) != 1 or not guess.isalpha():
...         print("❌ Please enter a single alphabet letter.")
...         continue
... 
...     if guess in guessed_letters:
...         print("⚠️ You already guessed that letter.")
...         continue
... 
...     guessed_letters.append(guess)
... 
...     # Check guess
...     if guess in secret_word:
...         print("✅ Good guess!")
...         for i in range(len(secret_word)):
...             if secret_word[i] == guess:
...                 display_word[i] = guess
...     else:
...         print("❌ Wrong guess!")
...         incorrect_guesses += 1
... 
... # Game result
... if "_" not in display_word:
...     print("\n🎉 Congratulations! You guessed the word:", secret_word)
... else:
...     print("\n💀 Game Over! The word was:", secret_word)
