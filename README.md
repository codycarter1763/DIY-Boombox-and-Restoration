# DIY Boombox and Restoration
<p align="left">
  <img src="https://github.com/user-attachments/assets/ba224f2e-2fce-4025-bdbc-15a49843db1e" width="48%" height="48%" alt="Left Image">
  <img src="https://github.com/user-attachments/assets/e7626d17-3227-4e4b-a83e-bb92d2b0b476" width="48%" height="48%" alt="Right Image">
</p> 


# About My Boomboxes
I design and fabricate custom-made boomboxes tailored to customers' specific desires not found on the market. Originally started as a way to fuse my love of music with technology as a kid, quickly turned into a very rewarding and successful venture with many different models and iterations for various applications. This repo contains my story, parts lists, design aspects and iterations, and additional information for anyone to pursue a truly unique project!

## First Iterations
When I was 12, I decided to take on a challenge and design my own boombox from the ground up. Having no clue what I was doing, I referenced a lot of websites and helpful Youtube videos that helped with my intuition on how everything connects together. Most if not all parts came from a scrap bin somewhere that I repurposed into a system. This initial build featured:
- Bluetooth
- Full-range stereo audio with woofer, midrange, and tweeters
- 3.5mm aux input for wired connections
- Lithium battery for 6 hours of continuous playback

I faced many challenges for this build, but after a lot of trial and error came a very useable and capable boombox that really motivated me to keep pursuing technology as a career. 

<p align="left">
  <img src="https://github.com/user-attachments/assets/6129a7fc-5046-4f1d-aa31-f4d7af28f7ff" width="48%" height="48%" alt="Left Image">
  <img src="https://github.com/user-attachments/assets/321d13d1-e7a6-4711-b7b8-c8ab406ccc88" width="48%" height="48%" alt="Right Image">
</p> 

## After Development and Experience 
Building off of the experience I gained from my first boombox build, I started incorporating Autodesk Fusion for CAD, CNC machining, and audio physics with WinISD for the highest fidelity and consistent audio quality. After multiple iterations, commissions started to gain traction from people who wanted a fully custom speaker system with aspects not found on the market. Notable builds include:
- Studio monitor systems for mastering music in a recording studio and band hall
- Desktop speakers for high-fidelity audio quality
- Portable boomboxes for parties and outdoor use

<p align="left">
  <img src="https://github.com/user-attachments/assets/cb164321-e334-4e32-bffc-d568d28da9fc" width="48%" height="48%" alt="Left Image">
  <img src="https://github.com/user-attachments/assets/09d6acad-b404-4c20-ab4c-29c617294e5f" width="48%" height="48%" alt="Right Image">
</p> 

# Restoration Of A Previous Build
Between the fabrication of my first boombox and the standard models shown above, I experimented with making a portable boombox with advanced features to see whether it would be worth pursuing. Features include:
- JVC KD-RD99BTS stereo reciever for highly customizeable audio
- 200W of Class D amplifier power
- Full range hi-fi audio
- Carefully sized box with WinISD for optimum subwoofer performance
- Precision fabricated with CNC machining
- Motorized AM/FM antenna for automatic raising/lowering
- Guitar input
- Microcontroller for custom RGB lighting

While this speaker system did work, there were certain issues like air leaks, size of enclosure, radio battery charging, and ease of use that steered me to make Bluetooth-only speaker systems after this one. As a result, I just used this speaker system as a project box, where I can try out different speaker setups, features, tunings, and really anything else to potentially make into a new model.

Fast forward to the present, I decided to take this speaker system out of retirement and make it into a very useable and functional boombox to bring with me to tailgates. Several improvements were made to the original design and ended up being my favorite boombox that I have made thus far. These improvements include:
- New lead-acid battery and charger for radio setting backup
- High-excursion subwoofer visualized with WinISD for deeper bass with the same box size
- Cleaned up and simplified wiring
- Downsized 200 watt amp to a 100 watt amp, ended up being just as loud with the same percieved volume without distortion
- Resealed speaker enclosure with new foam strips to prevent air leaks
- Disconnected the guitar input

# Parts List
## Audio
- JVC KD-RD99BTS stereo reciever
- Parts Express ground loop isolator
- Pyramid TW44 Heavy Duty Titanium Super Tweeter
- Pyle PDMR5 5" Sealed Back Midrange Speaker Driver
- GRS 8SW-4HE 8" High Excursion Subwoofer 4 Ohm
- Doudou TPA3116D2 Class D Stereo 2x50W amp board
- Parts Express Polyfill
- Motorized AM/FM Antenna

## Power
- AC 110V/220V to DC 12V 20A 240W Universal Regulated Switching Power Supply
- 400W 15A DC Boost Module
- Mighty Max Battery ML5-12 - 12 Volt 5 AH
- 12V Sealed Lead Acid (SLA) Battery Charger 1300mA
- ChromaTek Full-Color RGB (WS2812) 19mm Momentary Push Button Switch
- Arduino Uno for RGB Button
- Buck Converter for Arduino
- Toggle Switches
  
# Enclosure Construction
Using a speaker designing software like WinISD, speakers and enclosures can be simulated to see how the system will perform under certain parameters. 

## WinISD Simulation 
Using a GRS 8SW-4HE 8" High Excursion Subwoofer and a 0.71 ft^3 sized sealed enclosure, below is a graph that plots the Sound Pressure Level (SPL) over the frequency spectrum in decibels with the enclosure parameter listed in the subwoofer datasheet. 

<img width="1088" height="561" alt="image" src="https://github.com/user-attachments/assets/3f63e68d-b891-4af9-9750-6f30de1388df" />

<img width="1172" height="226" alt="image" src="https://github.com/user-attachments/assets/50e95631-01a4-4416-b217-86a5d2532621" />

Since this is a sealed box, analyzing the graph shows a smooth increase starting at 10 Hz and leveling off at 100 Hz. The effect of this is flat, predictible bass without the boomniness that comes from specific frequencies from ported speaker enclosures. This means the sealed enclosure size is perfect in getting the best performance.

# Electronics
Below is the electrical diagram for the boombox:
![Boombox Electrical Diagram](https://github.com/user-attachments/assets/315d507c-56ac-4d56-b87f-217c2e4bce10)

## Ground Loop Isolator
The purpose of the ground loop isolator is to block unwanted DC signals that may be injected into the ground signal due to slightly different potentials or audio noise. This eliminates the common hum that audio systems might encounter for a noisefree audio experience. Using two 1:1 audio transformers for the ground loop isolation is the best solution to prevent audio signal attenuation.

## Stereo To Mono Converter
Since the boombox has one speaker per frequency band, where there is one subwoofer, one midrange, and one tweeter all close together, some stereo dependent audio can have parts cut off or attentuated. So using 220 ohm or above resistors wired as above, will convert the stereo signal into a single mono signal without any issues with ground loops or signal issues. 

# Conclusion
Originally started as a way to fuse my love of music with technology as a kid, quickly turned into a very rewarding and successful venture with many different models and iterations for various applications. This has been a really fun hobby and I will continue seeing how I can improve these designs in the future.
