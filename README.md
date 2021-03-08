# Cat Deterrent
Villanova MSCS IOT Security 2021 Semester Project

## Motivation
Cats are notoriously tricky to train. They respond well to repeated positive encouragement, but hate being told NO. Scolding a cat can make them fearful and sneaky, as they will associate you with cramping their style and return to do the action behind your back.

## Inspiration
If you search "spray pet deterrent", you will find a plethora of motion activated compressed air blasters. The reason they work so well (in many cases) is because instead of you scolding a cat, they become fearful of the area or activity. Some downsides of these devices are the costs, lifespan, and toxicity. To tackle these issues and provide some additional functionality, I created a safer and smarter IoT solution.

## Methods
1. Motion detection and recording
2. Relay - see resources below for super helpful and concise setup
3. Repellent - when the motion detector is tripped, the Pi turns the computer fan on for a few seconds via GPIO pins specified in the Python script and through the relay module
5. Notification
6. Playback

## Materials
_Parts summary, double check resources and make sure everything makes sense before purchasing_

- Raspberry Pi (+ SD card, power cable, etc.)
- Pi Camera
- Breadboard
- 12V DC power supply
- 12V computer fan (2/3/4 pins should all work if you ignore the unused wires)
- TIP120 Darlington Transistor
- 1N4001 Diode
- 2.2K Resistor
- Wires

Helpful:
- Set of jumper wires (MF/MM)
- I found a **multimeter** to be very useful when dealing with DC voltage (youtube: how to test DC power supply)

## Resources
Raspberry Pi to 12V Device Communication: [blog](https://dikuw.wordpress.com/2019/10/20/controlling-a-12v-solenoid-with-a-raspberry-pi/) / [archive](https://archive.fo/QVwbx)
- I wanted to use a solenoid for my initial design which is how I came upon this diagram from [Adafruit](https://cdn-shop.adafruit.com/product-files/412/solenoid_driver.pdf), which this awesome person replicated for use on a Raspberry Pi
- Looking back on it, I could have used a 5V relay module to accomplish this task but 1. I second guessed myself when researching the concepts and 2. It was more fun to do it on the breadboard. Plus I get to reuse the parts later.

Concept: [project](https://hackaday.io/project/159920-cat-trainer)
- Again, I initially wanted to use a solenoid but after thinking it through for a while, my idea seemed a bit too dangerous for a cat. I was going back and forth brainstorming ways to make scary noises, etc. and found this person used a toy fan to do exactly what I needed. Luckily, I recently swapped out my PC fan for a silent model, so I had the perfect candidate for a noisy 12V fan lying around.

## Tips
- The `pinout` command in Raspberry Pi OS is very helpful in finding the GPIO layout if you are switching between devices
