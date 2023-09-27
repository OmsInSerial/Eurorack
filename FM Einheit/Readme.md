# VCV Rack 2 modules

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
You can check this video for a more visual explanation.

B - Frequency knob (10Hz to 11KHz).

B shifted - Fine tune knob (-1 oct / +1 oct). Default at noon.
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

FM Einheit is avalable as a DIY module as a PCB + panel set (Daisy Patch SM not included) at Tindie or Modulargrid..

<img src="pics/DIY_PCB_set.jpeg" width="400">

Here is the [BOM as a xlsx file](src="files/FMEinheitv1_2.xlsx") or [as a csv file](src="files/FMEinheitv1_2.csv") to source the parts with Mouser references for SMD/THT components and other providers (Thonk, Banzaï...).

If you are not confortable with SMD soldering, you can buy the module fully build (Daisy Patch SM not included) at Tindie or Modulagrid.

1. SMD parts

| Placement         | Description   |Index|
| ------------------| ------------- |--------|
| <img src="pics/DIY_SMD_U1U2.jpeg" width="200">     | CD4051        |   U1,U2    |
| <img src="pics/DIY_SMD_U3.jpeg" width="200">       | CD4021        |   U3    |
| <img src="pics/DIY_SMD_U6.jpeg" width="200">       | PCA9685PW     |   U6  |
| <img src="pics/DIY_SMD_D30.jpeg" width="200">      | BAT54SW       |   D30  |
| <img src="pics/DIY_SMD_1K.jpeg" width="200">       | 1K resistors  |   R1,R44,R45,R48,R49,R50,R51,R52,R53,R54,R55,R56,R57,R58,R59  |
| <img src="pics/DIY_SMD_4K7.jpeg" width="200">      | 4K7 resistors |   R79,R80  |
| <img src="pics/DIY_SMD_10K.jpeg" width="200">      | 10K resistors |   R3,R9,R11,R12,R13,R19,R20,R21 |
| <img src="pics/DIY_SMD_100K.jpeg" width="200">     | 100K resistor |   R4 |
| <img src="pics/DIY_SMD_1M.jpeg" width="200">       | 1M resistor   |   R22 |
| <img src="pics/DIY_SMD_100n.jpeg" width="200">     | 100n capacitors   | C3,C4,C5,C8 |
| <img src="pics/DIY_SMD_Schottky.jpeg" width="200"> | Schottky Rectifiers  | L1,L2 |
| <img src="pics/DIY_SMD_beads.jpeg" width="200">    | ferrite beads   | L1,L2 |
| <img src="pics/DIY_SMD_10u.jpeg" width="200">      | 10u capacitors   | C1,C2 |

2. THD parts
   Place the THD parts on the board (except hearders and power header) as indicated below, **but do not solder anything now!**

| Placement         | Description   |Index|
| ------------------| ------------- |--------|
|   <img src="pics/DIY_Jack_2.jpeg" width="400">            | PJ398SM |   J_1,J_2,J_3,J_4,J_5,J_6,J_7,J_8,J_9,J_10,J_11,J_12    |
|   <img src="pics/DIY_Pot_1_1.jpeg" width="100">           | B10K, cut the orange part        |   RV1    |
|   <img src="pics/DIY_Standoff.jpeg" width="400">          | Trimmers, switch, standoff |   RV1,RV2,RV3,RV4,RV5,RV6,RV7,RV8,RV9,RV10,RV11,SW1,D17,D18,D20,D21,D25,D26,D27    |
|   <img src="pics/FM_Einheit_front_PCB.jpeg" width="400">  | Leds |   D17,D18,D20,D21,D25,D26,D27   |

Once every THD is placed on the board (except hearders and power header), secure the parts with the panel and screw every nuts.

<img src="pics/DIY_Finished_front.jpeg" width="400"> 

Now return the board + panel and solder the THD parts.

It's time to place headers. Unscrew every nuts and place the headers.

<img src="pics/DIY_Headers_1.jpeg" width="200"> 

Secure them with the panel and an elastic as shown here and solder them :

<img src="pics/DIY_Headers_2.jpeg" width="200"> <img src="pics/DIY_Headers_3.jpeg" width="200"> <img src="pics/DIY_Headers_4.jpeg" width="200"> 

Get the elastic off, place the power header and solder it.

<img src="pics/DIY_Power_header_1.jpeg" width="200"> <img src="pics/DIY_Power_header_2_1.jpeg" width="200">


## Installing the firmware
Download the latest firmware [here](https://github.com/OmsInSerial/Eurorack/blob/d59d7773702f3af148da5864a59d35fe75e9dd92/FM%20Einheit/files/FMEinheit.bin). Click on the Download raw file button.
 <img src="pics/Download_bin.png" width="100">


You can use the [ElectroSmith web configurator page](https://electro-smith.github.io/Programmer/) to do so with a last updated Google Chrome.

Follow this procedure:

1. Connect the Daisy to the Computer

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
