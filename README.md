# G-PO — PCB Manufacturing Machine

An interactive 3D simulator of a desktop machine that takes a blank copper board all the way to a finished, soldered circuit.

**Designed and developed by Gawdat Muhammed — Qualität Lab**

The machine was first designed in **Zoo Design Studio**, and the simulation was then built with **Claude Code**.

Available in three languages: Arabic, English and Chinese.


## Overview

G-PO is a desktop PCB manufacturing machine that brings together, in one enclosure, four processes that normally need four separate machines: CNC isolation milling and drilling, solder-paste dispensing, SMT pick and place with optical inspection (AOI), and reflow soldering.

The machine has three stations. The drill station mills the copper traces and drills the holes, using a 500 W spindle, an alignment camera and dust extraction. The assembly station dispenses solder paste, picks and places the components from four 8 mm tape feeders, and inspects them with a vision camera and an LED ring light. The reflow oven solders the board with four quartz infrared heaters, a thermocouple and cooling fans.

A transfer axis carries the board between the three stations on one shared coordinate frame, so the board is never unclamped between milling and soldering.

This repository contains the interactive simulator of the machine: a single web page that runs the complete 3D model, the motion system, the manufacturing process and the bill of materials directly in the browser.


## How the project was made

**Step 1 — Mechanical design.** The complete machine was designed in Zoo Design Studio and exported as a STEP file containing 224 parts.

**Step 2 — Simulation.** The interactive simulator was built with Claude Code. It turns the CAD model into a working machine on screen: moving axes, a full manufacturing program, a G-code terminal, a price list and a three-language interface.


## What you can do in the simulator

**Explore the machine.** Browse all 224 parts from the CAD file, plus 4 parts added from the reference image (the touch screen, the signal tower and the start and stop buttons). Click any part to see its name, material, dimensions, weight, which axis moves it, and how much it costs. You can also hide parts, isolate them, look through the enclosure, or cut the machine in half to see inside.

**Take it apart.** An exploded view moves every group of parts out along its real direction of removal. Twenty step-by-step disassembly instructions explain what to remove, in which order, and which tools you need.

**Run it.** Start a complete ten-stage program on a sample LED-driver board and watch the machine work: alignment, milling, drilling, transfer, paste dispensing, pick and place, inspection, reflow soldering and unloading. The simulator includes an emergency stop, a door safety interlock, live readings for every axis, a live oven temperature chart, manual control of each head, and a G-code terminal for typing machine commands.

**Check the cost.** The bill of materials lists 70 items, with prices from Egyptian stores and international suppliers, links to the sources, and notes. The estimated cost of the complete machine is about 82,181 Egyptian pounds (about 1,481 US dollars), based on prices collected on 8 November 2026. The list can be filtered, searched and copied into Excel or Google Sheets.

**Choose your language.** A globe button in the top bar switches between Arabic, English and Chinese. Arabic reads from right to left, while English and Chinese read from left to right. Everything is translated, including part names, process stages, instructions, specifications and prices. Standard technical terms such as CNC, SMT, Reflow, AOI and G-code are kept as they are. The site remembers the language each visitor chose the next time they open it.


## The manufacturing process

1. Load and clamp the raw copper board
2. Align the board with the camera
3. Mill the isolation channels around the copper traces
4. Drill the component and mounting holes
5. Move the board to the assembly station
6. Dispense solder paste on every pad
7. Pick and place the components
8. Inspect the components optically (AOI)
9. Solder the board in the reflow oven: preheat to 150 °C, soak at 180 °C, peak at 245 °C, then cool with fans
10. Cool down and unload the finished board


## The machine at a glance

- **Size:** 745 × 440 × 430 mm, including the signal tower
- **Work area:** 350 × 250 mm (design target)
- **Motion:** 10 stepper motors covering the drill station, the three assembly heads, the nozzle rotation and the transfer axis
- **Accuracy:** ±0.05 mm positioning and ±0.02 mm repeatability (design target)
- **Spindle:** 500 W, 48 V, ER11 collet
- **Assembly:** four 8 mm electric tape feeders and one vacuum pick-up nozzle
- **Oven:** four 300 W quartz infrared heaters with temperature control
- **Control:** two Arduino Mega 2560 boards with RAMPS 1.4, a Raspberry Pi 4 for the interface and vision, and a 7-inch touch screen
- **Power:** 220 V AC
- **Estimated weight:** about 34 kg
- **Estimated cost:** about 82,181 EGP (about 1,481 USD)


## How to open it

Download the file index.html and open it in any recent browser, such as Chrome, Edge, Firefox or Safari. An internet connection is needed the first time it opens.

To publish it as a live website, turn on GitHub Pages in the settings of this repository.


## Important note

This simulator is made for design review and education. The physics are simplified, the specifications are design targets, and the prices are estimates from November 2026, so please confirm them before buying. The default solder paste in the simulation contains lead, so it needs good ventilation and careful handling, or it can be replaced with a lead-free alloy.


## Author

**Gawdat Muhammed** — design, engineering and development, Qualität Lab.

Machine designed in Zoo Design Studio. Simulator built with Claude Code.


## Thanks

Zoo Design Studio, for the CAD design of the machine. Claude Code by Anthropic, for building the simulator. Three.js, for the 3D graphics. The IBM Plex, Readex Pro and Noto Sans SC typefaces.


## Copyright

© 2026 Gawdat Muhammed. All rights reserved.


---


## بالعربي

**G-PO** ماكينة مكتبية لتصنيع اللوحات الإلكترونية (PCB). بتاخد لوحة نحاس خام وتطلعها دايرة كاملة وملحومة، وده كله جوه ماكينة واحدة.

**صاحب المشروع:** Gawdat Muhammed — Qualität Lab

**المشروع اتعمل إزاي:** الماكينة اتصممت الأول على برنامج **Zoo Design Studio**، وبعد كده اتعملت المحاكاة بـ **Claude Code**.

الماكينة بتجمع أربع عمليات بتحتاج عادةً أربع ماكينات منفصلة: حفر المسارات والتخريم بالـ CNC، وتوزيع معجون اللحام، وتركيب المكونات (SMT) مع فحص بصري، واللحام في فرن Reflow. واللوحة بتتنقل بين المحطات التلاتة من غير ما تتفك من مكانها.

**في المحاكي تقدر:**
- تستكشف القطع كلها، وتعرف اسم كل قطعة وخامتها وأبعادها وسعرها.
- تفك الماكينة خطوة بخطوة، 20 خطوة بالعدة المطلوبة لكل واحدة.
- تشغّل برنامج تصنيع كامل من 10 مراحل، وتتابع حرارة الفرن والقراءات الحية، وتتحكم يدويًا.
- تشوف قائمة المكونات والأسعار: 70 بند، والتكلفة التقديرية حوالي 82,181 جنيه.
- تختار اللغة: عربي أو إنجليزي أو صيني. الموقع بيفتكر اختيارك لما تفتحه تاني.

**التشغيل:** افتح ملف index.html في أي متصفح حديث، ومحتاج إنترنت أول مرة.


---


## 中文简介

**G-PO** 是一台桌面式 PCB 制造设备，可以把一块空白覆铜板直接加工成焊接完成的电路板。

**作者：** Gawdat Muhammed — Qualität Lab

**项目过程：** 设备先在 **Zoo Design Studio** 中完成机械设计，随后使用 **Claude Code** 开发了仿真器。

该设备在同一台机器中集成了通常需要四台设备才能完成的工序：CNC 隔离铣削与钻孔、锡膏点胶、SMT 元件贴装与光学检测（AOI），以及回流焊。PCB 在三个工位之间传送，全程无需重新装夹。

在仿真器中，您可以浏览全部零件、按 20 个步骤拆解设备、运行 10 个阶段的完整制造程序、查看包含 70 项物料的价格清单（整机估算约 82,181 埃及镑），并在阿拉伯语、英语和中文之间切换。

**使用方法：** 用任意现代浏览器打开 index.html 即可，首次打开需要联网。
