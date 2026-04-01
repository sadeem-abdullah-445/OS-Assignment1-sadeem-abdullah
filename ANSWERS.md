# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
A process is an independent program with its own memory, while a thread is a smaller unit that runs inside a process and shares resources. Threads are usually faster and easier to create than processes. In this assignment, we used threads because all tasks share the same queue and data in one program. This made the simulation easier to manage. Using processes would make it more complicated without much benefit.


---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**
In Round-Robin scheduling, if a process does not finish during its time quantum, it goes back to the ready queue. It waits there until it gets another chance to run. In my program, after a process runs one quantum, if it still has remaining time, it is added back to the queue again. This keeps repeating until the process finishes. This way, all processes get a fair chance to use the CPU.



Example from my output:
```
P1 completed quantum 4000ms  
Remaining time: 5938ms  
P1 yields CPU for context switch  
P1 (Priority: 5) added to ready queue  


**Explanation of example:**
This example shows that P1 did not finish in one quantum, so it returned to the ready queue. It will run again later when it gets another turn.

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

1. **New**: P1 is in the New state when the thread is created using new Thread(process) but has not started yet. At this stage, it has not been scheduled for execution.

2. **Runnable**: P1 becomes Runnable after calling start(). It is ready to run and waiting for the CPU.

3. **Running**: P1 is in the Running state when the run() method is executing. During this time, it uses the CPU for its time quantum.

4. **Waiting**:  P1 enters the Waiting state when it finishes its quantum but still has remaining time, so it is placed back into the ready queue. It waits until it gets another turn.
5. **Terminated**: P1 becomes Terminated when its remaining time becomes zero and the thread finishes execution. After that, it does not run again.


---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Web browser

Description: A web browser runs multiple tasks at the same time like loading pages and handling user actions.

Why Round-Robin works well here: It helps share CPU time between tasks and keeps the browser responsive.




### Example 2: Mobile applications

Description: Mobile apps handle different tasks like updating the screen and processing data.

Why Round-Robin works well here: It allows tasks to share CPU time, so the app runs smoothly without freezing.


---

## Summary

**Key concepts I understood through these questions:**
 1. Difference between threads and processes
 2. Ready queue behavior
 3. Thread states
**Concepts I need to study more:**
1. Thread synchronization
 2. Other scheduling algorithms 
