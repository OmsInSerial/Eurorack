# FM Einheit eurorack module

FM Einheit is a 2 operators FM synthesis module.
With its flexible FM engine, FM Einheit allows you to patch almost every algorithm you dream about.

<img src="pics/algorythms.png" width="300" height="315">

Imagine you get 2 or more modules... and you are in some sort of DX7 territory within Eurorack!

This module is developed under macOS with the help of [Erb Eurorack-Blocks](https://github.com/ohmtech-rdi/eurorack-blocks) framework + ElectroSmith Daisy Patch SubModule.

[Erb Eurorack-Blocks](https://github.com/ohmtech-rdi/eurorack-blocks) allows to test modules in the VCV Rack environment before going to the next stage of development.
From idea to final hardware module, via VCV:

| Idea          | VCV           |Hardware|
| ------------- | ------------- |--------|
| FM synthesizer | <img src="pics/FMEinheit_VCV.jpeg" width="192" height="346"> | <img src="pics/FMEinheit_hard.jpeg" width="384" height="512">  |

You can freely test FM Einheit under the VCV rack environment --> [FM Einheit VCV rack module](https://github.com/OmsInSerial/VCV)

## Controls

<img src="pics/FMEinheitPanel.png" width="300">

A - Shift button to access shifted controls. The LEDs indicate wether or not you've reached the previous control/shifted control  value. For instance, you've set the overall Harmonic (I) to 10 o'clock and plugged a CV in (N). Hold the shift button (A), the Harm LED turns red which indicates that you can't control the CV depth before reaching the previous Harm Depth CV value (which is set at noon first). Still holding the Shift button (A), turn the Harm knob (I) CCW. The closer you get to the previous value, the brighter the red LED. It turns green when the previous value is reached, then the Harm knob (I) acts as an Harm attenuverter CV depth control. The same is true when backing to Harm control when unholding the Shift button (A).
You can check [this video](https://youtu.be/jMld3nkBkAo?t=131) for a more visual explanation.

B - Frequency knob (10Hz to 11KHz).

B shifted - Fine tune knob (-1 oct / +1 oct). Default at noon. Available in the VCV Rack module, as a beta firmware for the hardware module

C - Operator 1 index (0 to 30) exponential response --> index 1 * (operator 2 based frequency) corresponds to generated sidebands harmonics strength above and under operator 1 based frequency. The more the index, the more audible sidebands.

C shifted - Index CV depth (-1 / 1), same for both Index 1 and Index 2. Default at noon.

D - Operator 2 index (0 to 30) exponential response.

D shifted - Index CV depth (-1 / 1), same for both Index 1 and Index 2. Default at noon.

E - Operator 1 ratio,  1 to 24, quantized (2 octaves wide). Multiple of core frequency.

E shifted - Ratio 1 CV depth (0 / 1).

F - Operator 2 ratio, 1 to 24 not quantized (2 octaves wide). Multiple of core frequency.

F shifted - Ratio 2 CV depth (0 / 1).

G - FM1 depth modulation applied to operator 1, linear response.

H - FM2 depth modulation applied to operator 2, linear response.

I - Harm allows to add more clarity to operator 1 or 2 by adding harmonics thanks to a bit of tropical additive synthesis. At noon no clarity, on left add clarity to operator 1, on right add clarity to operator 2.

I shifted - Harm CV depth (-1 / 1). Default at noon.

J - Mix is an equal power mixer between operator 1 and operator 2. FCCW operator 1 only, FCW operator 2 only.

J shifted - Mix CV depth (-1 / 1). Default at noon.
K, L - Trimmers control depth from CV input.

M to R - CV input (-5V to +5V) to indicated destination.

S - FM1 audio input.

T - FM2 audio input.

U - Fondamental frequency V/oct input (0V to +5V).

V - Mix CV input (-5V to +5V).

W - Audio output, operator 1 only

X - Audio output, mix of both operator (J)

## DIY

FM Einheit is avalable as a DIY module as a PCB + PCB panel set (Daisy Patch SM not included) at Tindie or Modulargrid..

<img src="pics/DIY_PCB_set.jpeg" width="400">

Here is the [BOM as a xlsx file](https://github.com/OmsInSerial/Eurorack/blob/4a29439237996cb19d1aecce53c95c5186f58875/FM%20Einheit/files/FMEinheitv1_2.xlsx) or [as a csv file](https://github.com/OmsInSerial/Eurorack/blob/4a29439237996cb19d1aecce53c95c5186f58875/FM%20Einheit/files/FMEinheitv1_2.csv) to source the parts with Mouser references for SMD/THT components and other providers (Thonk, Banzaï...). Click on the Download raw file button.
 <img src="pics/Download_bin.png" width="100">

If you are not confortable with SMD soldering, you can buy the module fully built (Daisy Patch SM not included) at Tindie or Modulagrid.

1. SMD parts

| Placement         | Description   |Index|
| ------------------| ------------- |--------|
| <img src="pics/DIY_SMD_U1U2.jpeg" width="300">     | CD4051        |   U1,U2    |
| <img src="pics/DIY_SMD_U3.jpeg" width="300">       | CD4021        |   U3    |
| <img src="pics/DIY_SMD_U6.jpeg" width="300">       | PCA9685PW     |   U6  |
| <img src="pics/DIY_SMD_D30.jpeg" width="300">      | BAT54SW       |   D30  |
| <img src="pics/DIY_SMD_1K.jpeg" width="300">       | 1K resistors  |   R1,R44,R45,R48,R49,R50,R51,R52,R53,R54,<br>R55,R56,R57,R58,R59  |
| <img src="pics/DIY_SMD_4K7.jpeg" width="300">      | 4K7 resistors |   R79,R80  |
| <img src="pics/DIY_SMD_10K.jpeg" width="300">      | 10K resistors |   R3,R9,R11,R12,R13,R19,R20,R21 |
| <img src="pics/DIY_SMD_100K.jpeg" width="300">     | 100K resistor |   R4 |
| <img src="pics/DIY_SMD_1M.jpeg" width="300">       | 1M resistor   |   R22 |
| <img src="pics/DIY_SMD_100n.jpeg" width="300">     | 100n capacitors   | C3,C4,C5,C8 |
| <img src="pics/DIY_SMD_Schottky.jpeg" width="300"> | Schottky Rectifiers. You can also refer to the Leds pic below for rectifiers orientation.  | L1,L2 |
| <img src="pics/DIY_SMD_beads.jpeg" width="300">    | ferrite beads   | L1,L2 |
| <img src="pics/DIY_SMD_10u.jpeg" width="300">      | 10u capacitors   | C1,C2 |

2. THD parts
   
First, place the 4 headers.

<img src="pics/DIY_Headers_1.jpeg" width="200"> 

Secure them with the panel and a ruber band as shown here and solder them :

<img src="pics/DIY_Headers_2.jpeg" width="200"> <img src="pics/DIY_Headers_3.jpeg" width="200"> <img src="pics/DIY_Headers_4.jpeg" width="200"> 

Get the rubber band off, place the power header J0 and solder it.

<img src="pics/DIY_Power_header_1.jpeg" width="200"> <img src="pics/DIY_Power_header_2_1.jpeg" width="200">

Place the remaining THD parts on the board as indicated below, **but do not solder anything now!**

| Placement         | Description   |Index|
| ------------------| ------------- |--------|
|   <img src="pics/DIY_Jack_2.jpeg" width="400">            | PJ398SM, common ground |   J_1,J_2,J_3,J_4,J_5,J_6,J_7,J_8,J_9,J_10,J_11,J_12    |
|   <img src="pics/DIY_Pot_1_1.jpeg" width="200">           | B10K, cut the orange part before placing the pot      |   RV1    |
|   <img src="pics/DIY_Standoff.jpeg" width="300">          | Trimmers, switch, standoff |  RV2,RV3,RV4,RV5,RV6,RV7,RV8,RV9,RV10,RV11,<br>SW1,D17,D18,D20,D21,D25,D26,D27   |
|   <img src="pics/FM_Einheit_front_PCB.jpeg" width="300">  | Leds |   D17,D18,D20,D21,D25,D26,D27   |

Once every THD is placed on the board, secure the parts with the panel and screw every nuts. Be carefull with the leds, it's very easy to bend the legs when placing the panel!

<img src="pics/DIY_Finished_front.jpeg" width="400"> 

Now return the board + panel and solder the THD parts. and you're done!
You should get something like that :

<img src="pics/DIY_Finished_back.jpeg" width="400">

3. Test

One thing I always do, is to check if there is a short with the power circuit. Get a multimeter, turn the dial to Continuity Test mode, place one lead to the negative pins and the other one to the positives as shown below. You shouldn't ear any BIP, if you do, it means you've a short somewhere on the board ...

<img src="pics/DIY_Short_test.jpeg" width="600">

Repeat the test between the ground pins and the positive and negative ones. You shouldn't ear anything!

4. Finishing
   
You can now put the pot knob, and plug your DPSM.

<img src="pics/DIY_Finished_perspective.jpeg" width="400"> <img src="pics/DIY_Finished_back_2.jpeg" width="400">

## Downloading and installing the firmware
Download the latest firmware [here](https://github.com/OmsInSerial/Eurorack/blob/d59d7773702f3af148da5864a59d35fe75e9dd92/FM%20Einheit/files/FMEinheit.bin). On the download page, click on the Download raw file button.
 <img src="pics/Download_bin.png" width="100">


You can also test the beta release which include the pitch fine tune control [here](Beta.md). Keep in mind that the purpose of this release is to test functionalities and is subject to frequent change.

You can use the [ElectroSmith web configurator page](https://electro-smith.github.io/Programmer/) to do so with a last updated Google Chrome.

Follow this procedure:

1. Connect the Daisy to the Computer with a micro USB cable.

2. Enter the system bootloader by holding the BOOT button down, and then pressing, and releasing the RESET button.

3. Click the Connect button at the top of the page.

4. Select, "DFU in FS Mode" and click connexion.

   <img src="pics/DPSMconnect.png" width="300">

5. Click the Choose File button, and select the .bin file you downloaded.

6. Click Program, and wait for the progress bar to finish.

   <img src="pics/FlashingProcess.png" width="500">

Now, if the program does not start immediatley, pressing RESET on the Daisy will cause the program to start running.

Requirements : 
In order to use this, you will need: an up-to-date version of Chrome, at least version 61 or newer

That's all! :+1:

All other details about FM Einheit are available here: [https://omsinserial.com](https://www.omsinserial.com/p/fm-einheit.html)
