# Typing-Speed-Calculator-in-Python
Develop a Python program that prompts the user to type a given set of words or
sentences. The program should record the time taken to type and calculate the
typing speed in WPM. Provide feedback on accuracy and speed.

    import time

    def calculate_wpm(time_elapsed, num_words):
      wpm = (num_words / time_elapsed) * 60
      return wpm

    def calculate_accuracy(original_text, user_text):
    original_words = original_text.split()
    user_words = user_text.split()
    
    correct_words = 0
    for original, user in zip(original_words, user_words):
        if original == user:
            correct_words += 1
    
    accuracy = (correct_words / len(original_words)) * 100
    return accuracy

    def typing_speed_test():
    # The sentence to type
    text_to_type = "The quick brown fox jumps over the lazy dog"
    print("Type the following sentence as fast as you can:")
    print(f"\n{text_to_type}\n")
    
    # Start the timer
    start_time = time.time()
    
    # User types the sentence
    user_input = input("Start typing: ")
    
    # End the timer
    end_time = time.time()
    
    # Calculate elapsed time
    time_elapsed = end_time - start_time
    
    # Calculate words per minute (WPM)
    num_words = len(text_to_type.split())
    wpm = calculate_wpm(time_elapsed, num_words)
    
    # Calculate accuracy
    accuracy = calculate_accuracy(text_to_type, user_input)
    
    # Provide feedback
    print(f"\nTime taken: {time_elapsed:.2f} seconds")
    print(f"Your typing speed is: {wpm:.2f} WPM")
    print(f"Your typing accuracy is: {accuracy:.2f}%")

    # Run the typing speed test
      typing_speed_test()
