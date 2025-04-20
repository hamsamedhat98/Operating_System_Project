Operating Systems Scheduler Simulation

Project Description

This repository contains the implementation of a process scheduler simulation for the Operating Systems course (CSEN 602) at the Faculty of Media Engineering and Technology, Spring 2025. The project, specifically Milestone 2, focuses on designing and implementing a simulated operating system environment that manages processes, memory, and resources using various scheduling algorithms and mutual exclusion mechanisms.

Key Features

Process Management:
      Implements a Process Control Block (PCB) to store process information, including Process ID, State, Priority, Program Counter, and Memory Boundaries.

Supports three programs:
      Program 1: Prints numbers between two given inputs (inclusive).
      Program 2: Writes data to a specified file.
      Program 3: Reads and prints the contents of a specified file.
      Parses program files and executes instructions based on a defined syntax (e.g., print, assign, writeFile, readFile, printFromTo, semWait, semSignal).

Memory Management:
      Simulates a fixed-size memory of 60 words, capable of storing process instructions, variables, and PCBs.
      Allocates memory dynamically for each process, ensuring no overlap and efficient space utilization.
      Tracks memory allocation and displays memory state in a human-readable format.

Scheduling Algorithms:
      Implements three scheduling algorithms from scratch:
      First Come First Serve (FCFS): Executes processes in the order of arrival.
      Round Robin (RR): Schedules processes with a user-defined quantum.
      Multilevel Feedback Queue (MLFQ): Uses four priority levels with increasing quantum (doubled per level) and Round Robin at the lowest level.

Mutual Exclusion:
      Implements three mutexes to ensure mutual exclusion for critical resources:
      userInput: For user input operations.
      userOutput: For screen output operations.
      file: For file read/write operations.
      Handles resource contention by blocking processes and prioritizing unblocking based on process priority.

Console-Based Interface:
      Provides a real-time display of system state, including:
      Process details (PID, state, priority, program counter, memory boundaries).

Ready and blocked queues.
      Mutex status and blocked processes per resource.

Memory allocation.
      Logs execution details to a file (execution_log.txt) for tracking instructions and system events.
      Allows user interaction to select scheduling algorithms, set quantum for Round Robin, and step through or run the simulation continuously.

Implementation Details
Language: C
Files:
      os_scheduler.c: Main implementation of the scheduler, memory management, mutex operations, and process execution.
      Program_1.txt, Program_2.txt, Program_3.txt: Sample program files for testing.
      execution_log.txt: Output log file generated during simulation.

Key Components:
      PCB Structure: Manages process metadata and state.

Memory Structure: Tracks 60 memory words and their occupancy.

Mutex Structure: Manages resource locking and blocked process queues.

Scheduler Structure: Handles ready and blocked queues, tracks the running process, and implements scheduling algorithms.

Simulation Flow:
        Loads programs at specified arrival times.
        Allocates memory and initializes PCBs.
        Executes instructions cycle-by-cycle, respecting mutexes and scheduling policies.

Updates and displays system state after each clock cycle.
