# How a Program Runs (Double Click → Execution)

## 🎯 Objective

Understand what happens inside a computer from the moment a user double-clicks an application until the CPU begins executing its instructions.

---

## 📖 What is a Program?

A program is a set of instructions written by a programmer that tells a computer what to do.

A program is simply a file stored on a storage device (SSD or HDD). By itself, it is inactive—it does nothing until the operating system loads it into memory.

### Example

When Google Chrome is installed on your computer:

```
chrome.exe
```

At this stage:

- It is stored on the SSD.
- It is not running.
- It is simply a program.

---

## 🖱️ What Happens When You Double-Click?

When you double-click a program, you are telling the operating system:

> "Load this program and start running it."

The operating system performs the following steps:

1. Finds the executable file (`chrome.exe`)
2. Reads the file from the SSD
3. Loads the program into RAM
4. Creates a process
5. Hands control to the CPU for execution

This is the core process that happens whenever an application starts.

---

## ⚙️ What is a Process?

When the operating system loads Chrome into RAM and starts running it, that running instance is called a **process**.
When the OS loads Chrome into RAM and starts running it, that running instance is called a process.
	• Chrome the file on disk = program
	• Chrome currently open and running = process
If you open Chrome three times, you have three processes. Same program, three running instances.

### Program vs Process

| Program | Process |
|----------|----------|
| File stored on disk | Running instance of a program |
| Not executing | Currently executing |
| Stored on SSD/HDD | Stored in RAM |

If you open Chrome three times, you have three separate processes created from the same program.

Each process receives:

- **Process ID (PID)** – A unique number assigned by the operating system.
- **Memory Space** – RAM allocated for the program's code and data.
- **Access to System Resources** – Permission to use files, CPU, network, printers, memory, and other OS services.

---

## 🖥️ CPU Starts Executing Instructions

Chrome contains millions of machine instructions.

The CPU repeatedly performs the following cycle:

### Fetch

Reads the next instruction from RAM using the Program Counter.

↓

### Decode

Determines what the instruction means.

↓

### Execute

Carries out the instruction.

This cycle repeats billions of times every second.

### Example

Instruction 1

Create the Chrome window.

Instruction 2

Display the address bar.

Instruction 3

Load bookmarks.

Instruction 4

Start networking services.

---

## 📌 Summary

When you double-click a program such as `chrome.exe`:

1. The operating system locates the program on the SSD.
2. The operating system reads the program from storage.
3. The operating system loads the program into RAM.
4. The operating system creates a process.
5. The process receives a Process ID (PID), memory space, and access to system resources.
6. The CPU executes the program using the **Fetch → Decode → Execute** cycle.
7. The application begins performing its tasks.
8. The user sees the application running.

---

## 🧠 Key Takeaways

- A **program** is an inactive file stored on disk.
- A **process** is a running program in memory.
- Programs cannot execute directly from an SSD or HDD.
- The operating system loads programs into RAM.
- The CPU executes instructions stored in RAM.
- Every running process has its own PID.

---

## ❓ Self-Review Questions

1. What is the difference between a program and a process?
2. Why can't the CPU execute instructions directly from the SSD?
3. Why is RAM necessary?
4. What is a PID?
5. Explain the Fetch → Decode → Execute cycle.

---



