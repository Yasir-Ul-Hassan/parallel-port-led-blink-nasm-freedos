# parallel-port-led-blink-nasm-freedos
📌 Parallel Port LED Blink (NASM + FreeDOS)
📖 Project Overview

This project shows how to control an LED using a PC parallel port (DB25) with Assembly language.
The program is written using NASM and runs on FreeDOS to allow direct hardware port access.

The goal of this project is to demonstrate low-level hardware control using x86 assembly and I/O port programming.

🎯 Project Objective

Learn how parallel port data pins work

Learn basic assembly hardware programming

Control external hardware (LED) using PC port

Understand real I/O port communication

🛠 Technologies Used

Assembly Language (x86 16-bit)

NASM Assembler

FreeDOS

PC Parallel Port (DB25 / LPT)

💡 How It Works

The program sends binary data to the parallel port address (0x378).

When data bit D0 becomes HIGH (5V), the LED turns ON.
When D0 becomes LOW (0V), the LED turns OFF.

🔌 Hardware Requirements

PC with Parallel Port (LPT / DB25)

1 LED

220Ω – 330Ω Resistor

Parallel Port Cable / Connector

⚠ Safety Note

Always use a resistor with LED.
Without resistor:

LED may burn

Parallel port may get damaged

🧩 Circuit Connection
Component	Connection
LED Anode (Long Leg)	Resistor → Pin 2 (D0)
LED Cathode (Short Leg)	Pin 25 (Ground)
💻 Software Requirements

FreeDOS Bootable USB

NASM Assembler

📂 Project Structure
parallel-port-led-blink-nasm-freedos
│
├── blink.asm
├── blink.com
├── README.md
├── circuit-diagram.png
└── docs/

🧾 Assembly Code
org 0x100

mov dx, 0x378

mov al, 1
out dx, al

mov cx, 0FFFFh
delay:
loop delay

mov al, 0
out dx, al

mov ah, 4Ch
int 21h

⚙ Build Instructions
Step 1 — Boot FreeDOS
Step 2 — Compile Code
nasm -f bin blink.asm -o blink.com

▶ Run Program
blink


LED should turn ON then OFF.

🧪 Testing Tips

If LED does not work:

Check wiring

Check resistor connection

Check port address (0x378)

Make sure running in FreeDOS

📚 Learning Outcome

After this project you will understand:

Parallel port hardware basics

Assembly OUT instruction

Real hardware control using software

DOS assembly program structure
