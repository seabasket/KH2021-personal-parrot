# KH2021-personal-parrot
A personal message recorder/displayer to help combat loneliness in the hustle of day-to-day life.

<p align = "center">
Video of the Personal Parrot in Action  --> https://youtu.be/prRBdDbID60
</p>
 
Built for Knighthacks 2021 by Sebastian Rowe, Rachel Dawns, Evan Fulkerson, and Turner Flynn. 
The following is taken from our Devpost. (https://devpost.com/software/personal-parrot)

# Inspiration
Loneliness and isolation have riddled the past few years so our team wanted to bring a little empathy and joy to those who are physically by themselves. Just as Gandalf the Grey says,“I have found that it is the small everyday deed of ordinary folks that keep the darkness at bay.” Together, our team created something to make someone who is in quarantine or just far away from their community feel heard and listened to by those who are closest to them.

# What it does
Our project detects when a person walks into the room using image regression analyzing a live constant feed. When it recognizes a person, the program will record for 3 seconds listening to what the person has to say. The program will then convert the audio file into a text string using Goggle Cloud’s Speech-to-Text API. That message is then stored until the camera detects another person entering the room. At this moment, the program will display the recorded message on an OLED display, and then prompt the new user to enter a new message.

# How we built it
Software: Personal Parrot utilizes a number of different Python libraries as well as NVIDIA’s own AI libraries, Google Cloud Speech-to-Text API, and Arduino code put together to make it work. The main program is controlled by the Jetson Nano Hardware written solely in Python. When interacting with the Arduino it uses a serial connection. Arduino uses a version of C code to then interact with the Python code that invoked it. *Hardware: * We used an NVIDIA Jetson Nano Linux MCU, an Arduino Nano 33 BLE, a SSD1306 OLED, a webcam, and a conference microphone. We have all of the inputs (Camera and Microphone) running into the Jetson, which then transfers the data to the Speech-to-Text API. The API then transmits the converted string to the Jetson, which then runs that data into the Arduino to power the OLED. All of these electronics are housed in a custom 3D printed casing created in SolidWorks.

# Challenges we ran into
After taking 3-4 hours to set up an image regression live object recognition feed, we as a team struggled to access the python descriptors that held the classifications of the objects in the image, this one line of code took several of us working for ~5 hours to complete for this one line of code. Several group members were (past tense!) not familiar with python so it took a lot of research to figure out the syntax that allowed us to access the data we needed from the live feed frames. It was difficult to synthesize all the components and python imports when we combined our code. Another difficulty was determining how to receive sound. Most of us had little to no knowledge of how Arduino worked with sound especially saving sending or receiving audio files. At first, we were going to use the Arduino mic, but after realizing its limitations prevented us from easily getting the mic output into an audio file we switched gears. Luckily, one group member had a speaker in his backpack that had a microphone we could use. This ended up being to our benefit because we could keep most of our code in python by using this other microphone while our first idea would have had us trying to coordinate Arduino coding and python coding for different components. We also 3D-printed the casing with too little tolerance (Space to slide components in), so we had to remove the inner wall from the case to properly fit the hardware.

# Accomplishments that we're proud of
We ultimately accomplished a successful piece of equipment to recognize a person, record their message, and display that message. Along the way, Sebastian was very excited when he figured out his Python descriptors problem. We also created a custom-3D printed casing to fit all of the electronics. Evan worked hard to do design modifications on the custom casing and it was awesome when it finally fit perfectly. Overall, we came over many obstacles to create a successful product in the end.

# What we learned
We all learned a lot and were relatively in over our heads for much of this hackathon, Sebastian has had a bit of experience with image classification with the NVIDIA Jetson NANO before but had had very little experience with much of the other ML tasks needed for this project, specifically the image regression and inference required to handle a live video feed. Along with Turner, he was one of the main troubleshooters when it came to program and program flow. Evan had had some experience with CAD before (and built the team a killer box), but was needed while said box was 3d printing, to help with coding the NVIDIA kit to speak to and from the Arduino using serial ports. Something he had never done before. Turner has had the most experience out of all of us. He learned about how to implement each library needed to run the program. Turner worked through most of the complex programming issues by applying his past knowledge of Arduinos and the Jetson. Rachel helped in all areas of the project. She learned about programming hardware such as the Arduino and Jetson, and also learned more into using Python to record and transfer audio files.

# What's next for Personal Parrot
As of now, we are restricted to a 16-bit display. In the future, we can either wrap the text to feature a longer message or use a larger display option. We can also build in an option to playback personalized audio messages based on facial identification. For example, you would be able to leave a message for a specific person, and then the program would only replay that message when that person’s face is detected.

# Built with
Arduino Nano 33 BLE, NVIDIA Jetson Nano, SSD1306 OLED 128x64, USB Webcam, USB Microphone, Ender 3 Pro 3D-Printer (Along with SolidWorks), Linux Gedit Text Editor (Python), Arduino IDE, Google Cloud: Speech-to-Text API
