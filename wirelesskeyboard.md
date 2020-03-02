# Wireless Keyboard?
The dream was simple, a normal split wireless keyboard: better posture, no wires, clean desk. How hard is that supposed to be.

Okay, yeah sure i had a checklist of things to make it perfect. But that's besides the point. The whole mechanical keyboard community should have a least solved this problem by now. But i guess now. So leave it to me to make some jank garbage, in attempt to create this "Dream Keyboard"

This is a build guide, but it's mostly my journey into the depths of the keyboard world. 

# Research
A quick google search of "wireless split keyboard" does not in fact lead to the dream but a bunch of lame big company ergo keyboards that are wireless. lame.

"wireless split keyboard reddit" on the other hand does direct us to one of the best designed keyboards and well documented build process, the Mitosis keyboard [https://www.reddit.com/r/MechanicalKeyboards/comments/66588f/wireless_split_qmk_mitosis/](https://www.reddit.com/r/MechanicalKeyboards/comments/66588f/wireless_split_qmk_mitosis/). This keyboard is A+ design of reusability of PCBs and A+ documentation. But, didn't fit my dreams of a "normal" keyboard. The custom bluetooth receiver though is a bit much. Wonderfully designed and done, but too much for me. The search continues... 

Googling and asking friends came upon this normal looking split keyboard from Keebio [https://keeb.io/products/quefrency-60-65-split-staggered-keyboard](https://keeb.io/products/quefrency-60-65-split-staggered-keyboard). Clearly we have standard keybard split by the left and right now sides (looks good so far), but is not wireless... Why do we even have wires in this day and age?

## Research Research
So with my mind decided on the Quefrency keyboard and do note that there are plans for a new version with back lighting, i decided to research what it would take to make a normal designed PCB into two wireless halves.

This starts from their own build guide [https://docs.keeb.io/quefrency-build-guide/](https://docs.keeb.io/quefrency-build-guide/). This build guide is the basis of what i build on, obviously since i use their PCB i can only deviate so much. 

Knowledge #1 - ATmega32U4 - the usage of Pro Mircos is very common [https://keeb.io/products/pro-micro-5v-16mhz-arduino-compatible-atmega32u4](https://keeb.io/products/pro-micro-5v-16mhz-arduino-compatible-atmega32u4). When i was looking around all usb-c versions were sold out, now many version are around and even mid mount designs which are slim and nice. Though because they seem to be new ish they seem to have their own sets of problems: [https://keeb.io/products/elite-c-usb-c-pro-micro-replacement-arduino-compatible-atmega32u4](https://keeb.io/products/elite-c-usb-c-pro-micro-replacement-arduino-compatible-atmega32u4), [https://keeb.io/products/elite-c-low-profile-version-usb-c-pro-micro-replacement-atmega32u4](https://keeb.io/products/elite-c-low-profile-version-usb-c-pro-micro-replacement-atmega32u4). And of course you don't have to get them through Keebio many people make their own versions of them, it's just easier to get them all together. But the true knowledge here is the processor used, ATmega32U4.

Knowledge #2 - QMK - i've researched this far, yet i still don't know what this mysterious QMK acronym is, maybe that should be next to look in to. And presto google and done QMK (Quantum Mechanical Keyboard Firmware) [https://docs.qmk.fm/#/](https://docs.qmk.fm/#/). Thank you google. Fantastic, code to edit before flashing these ATmega32u4 (note i did not say pro micros).

Knowledge #3 - Bluetooth (nRF51822) - QMK with the power of community anything is possible. Bluetooth is already supported and with a couple options as well, [https://docs.qmk.fm/#/feature_bluetooth](https://docs.qmk.fm/#/feature_bluetooth). Their links led me to the Adafruit company, down to a search and found out about a product line called [Feather](https://www.adafruit.com/category/777). They have a product with the nRF51822 bluetooth chip as well as the ATmega32U4 processor, [https://www.adafruit.com/product/2829](https://www.adafruit.com/product/2829). 

# Idea