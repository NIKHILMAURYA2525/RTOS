# RTOS
RTOS-Based Menu-Driven Embedded Application
This project demonstrates a FreeRTOS-based embedded system that handles user input via USART2 using interrupt-driven communication and queue-based task signaling. It features a simple menu interface allowing users to trigger different functionalities on an embedded target.
Key Features
• Interrupt-driven UART input:
Uses USART2 to receive user input asynchronously.
• ISR-to-task communication:
Implements queues to safely transfer received data from the UART interrupt context to a command handler task.
• Menu-driven interface:
A user-friendly menu is displayed over the serial terminal.

========================
|         Menu         |
========================
LED effect    ----> 0
Date and time ----> 1
Exit          ----> 2
Enter your choice here :
Task-Based Execution:
Based on the user's input, the system performs:
• 	: Triggers an LED blinking pattern task.
• 	: Displays current date and time.
• 	: Exits or halts the system gracefully.
🛠️ Technologies Used
• 	Platform: STM32 (HAL drivers)
• 	RTOS: FreeRTOS
• 	Communication: USART2 with interrupt mode
• 	Language: C
🔄 Flow Overview
1. 	User sends a command via serial terminal.
2. 	 captures the input.
3. 	Inside the UART ISR, the input is pushed to a queue using .
4. 	A command handler task dequeues the input and dispatches the appropriate task.
