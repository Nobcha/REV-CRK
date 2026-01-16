# REV-CRK
Reviving the Chinese Radio Kit - Mottainai strategy
**Three Fatal Flaws, Three Engineering Disciplines: Complete Rescue of a Chinese Radio Kit**

Found this $15 Chinese airband receiver kit in my junk drawer. 
Built it years ago, discovered THREE dealbreakers, gave up.

Recently thought: "Can each problem be solved?"

Spoiler: Yes - but each required completely different expertise! 🎯

![Air band receiver PCB ASSY in the junk box](/PCBASSY_IN_JB.jpg)
----------------------------------------------------------------

**The Three Fatal Flaws:**

**Flaw 1: Unstable VFO** ❌
Frequency drifted several kHz. LC oscillator was garbage.

**Flaw 2: Ear-Splitting Squelch Pops** ❌
Switching squelch produced painful pops. Circuit design flaw.

**Flaw 3: Terrible Sensitivity** ❌
PCB pattern coils = deaf receiver. Barely usable.

Any ONE would make the kit useless. This had ALL THREE. 😅

---------------------------------------------------------------

**The Three Fixes - Three Different Skill Sets:**

**Fix 1: Digital Control (Software/Hardware)**

Replaced LC oscillator with digital VFO:
- Arduino Pro Mini + Si5351a clock generator
- LCD display + rotary encoder
- Clean, stable frequency generation

**Skills needed:**
- Microcontroller programming
- I2C communication
- User interface design

**Result:** Drift <100 Hz (rock solid!) ✅

--------------------------------------------------------------

**Fix 2: Analog Circuit Design (Theory/Simulation)**

Original circuit shorted audio to ground for mute, causing 
huge bias swings in LM386's BTL output.

My solution:
- Inject positive bias into LM386's input transistors
- Saturate input stage (stops amplification)
- No bias swing = no pop!
- Verified in LTspice before building

**Skills needed:**
- IC internal architecture understanding
- Circuit simulation
- Creative problem-solving

**Result:** Silent, clean squelch operation ✅

**Technical deep-dive with LTspice simulation:**
https://nobcha23.hatenadiary.com/entry/2022/01/04/230130

-------------------------------------------------------------

**Fix 3: RF Optimization (Craftsmanship/Black Magic)**

PCB pattern coils have terrible Q factor. Can't replace them 
without redesigning the whole board.

My solution:
- Precision measurement of circuit behavior
- Optimized capacitor values for resonance
- Careful implementation technique
- Iterative refinement

This is pure craftsmanship - requires:
- RF measurement equipment
- Understanding of impedance matching
- Precise soldering technique
- Experience and "feel"

**Skills needed:**
- RF theory and practice
- Measurement technique
- Implementation craftsmanship

**Result:** Sensitivity band coverage improved ✅

**Detailed techniques and measurements:**
https://nobcha23.hatenadiary.com/entry/2020/12/02/174051
If you ask more, you shall change those to the air core coils.
--------------------------------------------------------------

**The Complete Transformation:**

Before:
- Unusable drift ❌
- Painful pops ❌
- Deaf as a post ❌
- Junk drawer resident ❌

After:
- Rock-solid frequency ✅
- Clean audio ✅
- Actually receives signals ✅
- Daily use for several months ✅

-------------------------------------------------------------

**Why This Project Matters:**

This isn't just a radio rescue - it's a case study in 
multi-disciplinary problem-solving.

**Each problem required different expertise:**
- Digital/Software skills (Problem 1)
- Analog circuit design (Problem 2)
- RF craftsmanship (Problem 3)

**Key Lessons:**
1. Systematic diagnosis (identify ALL problems)
2. Match solution to problem type
3. Leverage different skill sets
4. Document everything (help others)

This is why I love electronics - always learning something new!

-------------------------------------------------------------

**The Questionable Economics:**

Original kit: $15 (wasted years ago)
Rescue parts: ~$30
Time invested: 3 weekends
Total: $40

vs.

Commercial receiver: $150-300
Skills learned: Priceless 😄

--------------------------------------------------------------

**For Anyone With These Kits:**

**Warning signs:**
🚩 PCB pattern coils (not wire-wound)
🚩 LC oscillator (not PLL/digital)
🚩 Poor squelch design

If you have these problems, they CAN be fixed - 
but each requires different skills!

---------------------------------------------------------------

**Evolution Plans:**

v1 (current): Make it work
v2 (in progress): OLED display, more features
v3 (planned): ESP32 platform

---------------------------------------------------------------

**All Documentation:**
- Blog (detailed fixes): https://nobcha23.hatenadiary.com/
- GitHub (code, schematics): [github.com/nobcha/rock-solid-vfo](https://github.com/Nobcha/REV-CRK/edit/main/)
- YouTube (build process): https://www.youtube.com/@nobchaa2255

---------------------------------------------------------------

**Credits:**
- CeaserSound: Si5351a tutorials: https://projecthub.arduino.cc/CesarSound/10khz-to-225mhz-vforf-generator-with-si5351-version-2-acdc25
- TJ lab: Si5351 library: https://github.com/tjlab-jf3hzb/Digital_VFO_with_analog_dial/
- Years of trial and error across three disciplines 😅

---------------------------------------------------------------

**Three problems. Three skill sets. One functional receiver.**

What's YOUR junk-drawer rescue project? 
Let's fix it together!

