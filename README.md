# STM32-Button-Controlled-LED-GPIO-Input-Output-Using-STM32F103C8-


This project demonstrates a **basic STM32 HAL-based GPIO application** using STM32CubeIDE.  
It reads a push button (as input) and controls an LED (as output) based on its state.

---

##  Description

- When **Button (PA0)** is **pressed** (logic LOW due to pull-up), the **LED (PA1)** turns **ON**
- When the button is **not pressed**, the LED remains **OFF**

This project is perfect for learning:
- GPIO Input with pull-up configuration
- GPIO Output control
- STM32 HAL Initialization
- Using STM32CubeIDE with C

---

##  Hardware Setup

| Component   | Pin    | Description        |
|-------------|--------|--------------------|
| Push Button | PA0    | Input (with pull-up) |
| LED         | PA1    | Output (active LOW) |

 *Connect push button between PA0 and GND.*

---

## Pin Configuration

| Pin   | Mode   | Pull     | Speed         | Function   |
|--------|--------|----------|---------------|------------|
| PA0    | Input  | Pull-Up  | —             | Button     |
| PA1    | Output | No Pull  | Low Frequency | LED        |

---

##  Code Logic Summary

```c
int k = HAL_GPIO_ReadPin(GPIOA, GPIO_PIN_0); // Read button

if (k == 1) {
    HAL_GPIO_WritePin(GPIOA, GPIO_PIN_1, GPIO_PIN_RESET); // LED ON
} else {
    HAL_GPIO_WritePin(GPIOA, GPIO_PIN_1, GPIO_PIN_SET);   // LED OFF
}
