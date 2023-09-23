# Random Access Memory

**Random Access Memory (RAM):** RAM is like a super-fast memory storage in a computer. It's made up of many small storage units, like tiny boxes, called **registers**. Each of these registers can store a number (0 or 1).

**How RAM Works:**

- RAM contains lots of these **registers**, and each register has its own number, like 0, 1, 2, and so on.
- You can quickly choose any register you want by saying its number, like "**I want register number 3**."
- The amazing thing is, no matter how many registers RAM has, you can pick any of them super fast, and it doesn't matter which number you choose or how many registers there are.

**What You Can Do with RAM:**

- You can read what's inside a chosen register to see the number stored there.
- You can also change the number inside a register. Just say the new number you want to store, and RAM will put it there for you.

So, RAM is like a **super-fast storage** space with many tiny boxes (registers), and you can pick any box you want to read or change the number inside, and it's always super fast, no matter how many boxes there are.

![[Screenshot 2023-09-21 at 10.11.45 AM.png|700]]
**How to Use RAM:**

- To **read** the contents of a specific memory register (let's say register number 3), you set the address input to 3. This action selects register number 3, and the RAM immediately outputs its value.
- To **write** a new value (let's call it "v") into register number 3, you set the address input to 3, set the data input (in) to v, and activate the load bit (set it to 1). This process selects register number 3, enables it for writing, and sets its value to v. From the next time unit onward, the RAM's output will emit v.

**Key Feature:** The RAM behaves as expected—a collection of addressable registers that can be accessed and modified independently. For reading (when load == 0), it instantly provides the selected register's value. For writing (when load == 1), it updates the chosen memory register with the new value, and the RAM begins emitting this value from the next time unit.

**Speed:** It's crucial that the RAM ensures almost instant access time to any register within it. If not, fetching instructions and manipulating data would be too slow, rendering computers impractical. The technical details behind this rapid access time will be explained further in the Implementation section.

# Counter

The Counter chip, which we'll later call the **Program Counter** or **PC**, is designed to increase its value by 1 in each time unit. It has an interface similar to that of a register but includes two additional control bits: **inc** and **reset**.

- When **inc** is set to 1, the counter increments its value with every clock cycle, essentially performing the operation PC++.
- If we need to reset the counter to 0, we activate the reset bit.
- To set the counter to a specific value, say "v," we place v in the in input and **activate the load bit**, just like we do with registers.

In summary, the PC chip behaves much like a register but has the added ability to increment its value automatically (when inc is enabled) or reset itself (when reset is activated). These features are especially useful in computer architecture, and we'll explore them further when we build our computer system in chapter 5.

![[Screenshot 2023-09-21 at 10.18.11 AM.png|700]]
Usage: - To check the current value of the PC, simply look at the out pin. - To reset the PC to 0, activate the reset bit and ensure that the other control bits are set to 0. - If you want the PC to increment by 1 in each time unit until you instruct otherwise, activate the inc bit and ensure that the other control bits are set to 0. - To set the PC to a specific value, such as "v," put v in the in input, activate the load bit, and make sure the other control bits are set to 0.
