# Final Project Proposal: Caesar Cipher Encoder
Inspired by the Past       |  To Transform the Future
:-------------------------:|:-------------------------:
![image](https://github.com/user-attachments/assets/df71db2f-1572-45c8-9943-a1e5dedede5d)  |  ![ChatGPT Image May 17, 2025, 01_35_56 AM](https://github.com/user-attachments/assets/7a2d156f-c05d-4bde-b1c1-b5abf4592e9b)

Encryption has been at the core of secure communication since medieval times, driven by the need to protect sensitive information—especially in military contexts—from interception and interpretation by adversaries. My project, the **Caesar Cipher Encoder**, is a minimalistic yet functional recreation of one of the earliest known encryption techniques.

Devised by Julius Caesar, this cipher secures messages by shifting each letter of the plaintext by a fixed number of positions in the alphabet. For example, with a shift of 1, A becomes B, B becomes C, and so on, wrapping around such that Z becomes A. Thus, the word **HELLO** would be encrypted as **IFMMP**. The recipient, knowing the shift value, can decrypt the message by shifting in the opposite direction.

This project presents a digital implementation of the Caesar cipher, simulated using Logisim, showcasing how classical encryption concepts can be realized using fundamental logic circuits.

## Design Overview
The Caesar Cipher Encoder simulates the process of encrypting a single uppercase alphabet character (A–Z) by shifting it forward in the alphabet by a specified number of positions (the key). Internally, each letter is treated as a 7-bit ASCII value.
The encoder follows these major steps:
- **ASCII Input (A–Z):** The user inputs a 7-bit ASCII value (e.g., A = 65, Z = 90).
- **Normalize to Alphabet Index:** The circuit subtracts 65 to convert the ASCII input into a 0–25 range.
- **Apply Shift:** The user provides a 3 bit encryption key (0~7) which is added to the alphabet index.
- **Modulo 26 Operation:** If the result exceeds 25, the circuit wraps around using modulo 26 logic.
- **Convert Back to ASCII:** The final index is converted back to ASCII by adding 65.
- **Display Output:** The encrypted ASCII value is displayed via the 7-segment hex display.

## Circuit Components
| Component| Purpose |
| -------- | ------- |
| Input (7 bit)  | ASCII character input (plaintext)    |
| Input (3-bit) | Key input (shift amount)    |
| Adder    | For ASCII - 65, index + key, and + 65    |
| Constant    | Values: -65 (191), 65, 26    |
| Subtractor    | For modulo 26 logic    |
| Comparator    | To verify if shifted index >= 26    |
| Multiplexer   | To select wrapped or unwrapped value    |
| Hex Display    | To show the final encrypted ASCII    |

## Testing Phase
- Input characters: A (65), M (77), Z (90)
- Keys: 0, 3, 7 (TBD)
- Expected outputs to be verified manually and cross-checked with ASCII tables.
```
Input    Key    Expected Output    ASCII
A        3            D              68
Z        1            A              65
M        7            T              84
```
## Expected Results
- A fully functional Caesar Cipher Encoder capable of simulating the encryption of any uppercase letter using any configurable key.
- A modular design that can be reused or expanded to include decryption, support for lowercase letters, or full strings in future work.

![image](https://github.com/user-attachments/assets/8b329dd0-1dda-4005-b0ac-68ef118b9485)

