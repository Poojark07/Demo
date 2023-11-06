# Demo
#My first project 
#this is voice calculator application:

import speech_recognition as sr

# Initialize the recognizer
recognizer = sr.Recognizer()

# Capture audio from the microphone
with sr.Microphone() as source:
    print("Say something:")
    audio = recognizer.listen(source)

# Recognize the speech
try:
    text = recognizer.recognize_google(audio)
    print("You said:", text)

    # Parse and evaluate the mathematical expression
    result = eval(text)
    print("Result:", result)

except sr.UnknownValueError:
    print("Could not understand audio")
except sr.RequestError as e:
    print("Could not request results; {0}".format(e))
except Exception as e:
    print("Error: {0}".format(e))
```
