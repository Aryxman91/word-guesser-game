Word Guesser Game

    import random

    def play_game():
    word_bank = ["matcha", "labubu", "loveisland", "huzz", "tuff"]
    word = random.choice(word_bank)
    guessed_word = ['_'] * len(word)
    attempts = 10

    print("\n🎮 New Game Started!\n")

    while attempts > 0:
        print('\nCurrent word: ' + ' '.join(guessed_word))
        guess = input('Guess a letter: ').lower()

        if not guess.isalpha() or len(guess) != 1:
            print("Please enter a single valid letter.")
            continue

        if guess in word:
            for i in range(len(word)):
                if word[i] == guess:
                    guessed_word[i] = guess
            print('✅ Great guess!')
        else:
            attempts -= 1
            print(f'❌ Wrong guess! Attempts left: {attempts}')

        if '_' not in guessed_word:
            print('\n🎉 Congratulations!! You guessed the word: ' + word)
            break

    if '_' in guessed_word:
        print('\n💀 You\'ve run out of attempts! The word was: ' + word)

    while True:
    play_game()
    again = input("\n🔁 Do you want to play again? (y✅/n❌): ").strip().lower()
    if again != 'yes':
        print("👋 Thanks for playing!")
        break



