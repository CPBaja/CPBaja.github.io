# 🖥️ C++ Tutorials

Welcome to the C++ learning guide! This document covers how we use C++ on the team and provides the best resources to get you up to speed.

## What is C++ Used For?

On our team, **C++ is exclusively used for Firmware Development.** While our web applications use TypeScript and Angular, the physical hardware on the Baja car—such as the microcontrollers reading sensor data, managing the dashboard, and controlling actuators—requires a language that can execute extremely fast and interact directly with memory and hardware registers.



To manage our C++ firmware projects, we use **PlatformIO**, an extension for VSCode. PlatformIO handles our compiler toolchains, external libraries, and the process of "flashing" (uploading) the compiled C++ code directly onto the vehicle's microcontrollers.

---

## Prerequisites

Before diving into the code, ensure your environment is set up for firmware development:
1. **VSCode:** Installed and configured.
2. **PlatformIO IDE:** Install the PlatformIO extension directly through the VSCode extension marketplace.

---

## 📚 Learning Resources

C++ is a powerful but complex language. We do not expect new members to master it overnight. Depending on your current experience level, choose the track below that fits you best.

### 1. The Absolute Basics (For Beginners)
If you have never written C++ before, you need to understand the basic syntax, data types, loops, and functions.
* **[LearnCpp.com](https://www.learncpp.com/)**: This is the gold standard for learning C++. It is entirely free and comprehensive.
    * *Recommended Sections:* Read through Chapters 1 to 4 to understand the core syntax and program structure.

### 2. Firmware-Specific C++ (For Intermediate Developers)
Writing C++ for a microcontroller is slightly different than writing it for a desktop computer. Because microcontrollers have very limited memory (RAM), we heavily restrict the use of dynamic memory allocation.
* **[Arduino C++ Reference](https://www.arduino.cc/reference/en/)**: Even though we use PlatformIO instead of the Arduino IDE, we often use the Arduino C++ framework under the hood. Familiarize yourself with standard firmware functions like `setup()`, `loop()`, and `pinMode()`.
* **Pointers and Memory:** In firmware, you will frequently use pointers to read specific hardware registers.
    * *Tutorial:* **[LearnCpp: Pointers and References](https://www.learncpp.com/cpp-tutorial/introduction-to-pointers/)**

### 3. PlatformIO Workflow
Once you understand the basics of the language, you need to know how to build and upload it using our tools.
* **[PlatformIO Quick Start Guide](https://docs.platformio.org/en/latest/core/quickstart.html)**: Learn how a `platformio.ini` file works, how to manage dependencies, and how to compile and upload your code to a board.

---

## 🛑 Team Best Practices for Firmware

When writing C++ for the car, keep the following rules in mind:
* **Avoid `new` and `malloc`:** Dynamic memory allocation can cause memory fragmentation and crash the microcontroller mid-race. Pre-allocate your arrays and objects globally whenever possible.
* **Avoid `std::vector` or `std::string`:** For the same reasons as above, use fixed-size C-style arrays and `char` arrays (C-strings) to ensure memory stability.
* **Keep Interrupts Short:** If you are writing an Interrupt Service Routine (ISR), it should execute as quickly as possible. Set a flag and do the heavy lifting in your main `loop()`.