### NAME : Vijayaraj V
### REGISTER NO : 212222230174
### DATE :

## EX. NO.8 <H1 ALIGN =CENTER>Implementation of Speech Recognition</H1>

### Aim:
 To implement the conversion of live speech to text.<BR>

### Algorithm:

Step 1: Import the speech_recognition library<Br>
Step 2: Initialize the Recognizer<Br>
Step 3: Create an instance of the Recognizer class, which will be used for recognizing speech.<Br>
Step 4: Set the duration for audio capture<Br>
Step 5: Define a variable to specify the duration (in seconds) for which the program will capture audio from the microphone.<Br>
Step 6: Display a message in the console to prompt the user to speak.<Br>
Step 7: Capture audio from the default microphone<Br>
Step 9: Use the default microphone as the audio source.<Br>
Step 10: Record audio for the specified duration using the Recognizer instance.<Br>
Step 11: Perform speech recognition with exceptional handling:<Br>
•	Attempt to recognize speech from the captured audio using the Google Speech Recognition service.<Br>
•	If successful, print the recognized text.<Br>
•	Handle specific exceptions: If the recognition result is unknown or if there is an issue with the request to the Google Speech Recognition service, print corresponding error messages.<Br>
•	A generic exception block captures any other unexpected errors.<Br>

### Program:
```
import speech_recognition as sr
def record_audio():
    r=sr.Recognizer()
    r.energy_threshold = 6000
    voicedata=''
    try:
        with sr.Microphone() as source:
            audio=r.listen(source)
            voicedata=r.recognize_google(audio)            
    except sr.UnknownValueError:
        print("Unable to Recognize Audio")
    except sr.RequestError:
        print("Unable to find the Resource")
    return voicedata
while True:
    print("Say Something ....")
    text=record_audio()
    print(text)
    if text=="stop" or text=="close" or text=="exit":
        exit(1)
```

### Output:
![{1C2AC8A3-60A1-4819-8DA9-CB0D7E5ABE23}](https://github.com/user-attachments/assets/d4558dd3-614d-4def-96bf-47e5cf06c3c6)

### Result:
Thus, The implementation of speech recognition is executed successfully.
