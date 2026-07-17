# 4. Process vs Thread

## a) What is a Process?

A **process** is a running instance of a program.

When the operating system loads a program into RAM and starts executing it, that running program becomes a process.

Every process receives:

### Process ID (PID)

A unique number assigned by the operating system to identify the process.

The OS uses the PID to manage, monitor, and terminate processes.

### Memory Space

A dedicated area of RAM allocated to the process.

This stores the program's code, variables, and temporary data while it is running.

### System Resources

The operating system provides the process with resources such as:

- CPU
- RAM
- Files
- Network
- Printers
- GPU
- Keyboard and Mouse

These resources allow the process to perform its tasks.

### Security Context

Every process runs with a specific security context.

This determines the permissions the process has and what actions it is allowed to perform.

For example, applications started as an Administrator have more privileges than applications started by a standard user.

Each process is isolated from other processes.

This means one process normally cannot directly access another process's memory.

### Example

When you open Google Chrome:

```
Chrome.exe
        ↓
Operating System
        ↓
Chrome Process
```

If you open Microsoft Word:

```
Word.exe
        ↓
Operating System
        ↓
Word Process
```

Now the computer has two separate processes.

---

## b) What is a Thread?

A **thread** is the smallest unit of execution inside a process.

A process contains one or more threads.

Threads perform different tasks while sharing the same memory and system resources.

Unlike processes, threads do not have separate memory spaces.

---

### Example

When Chrome is running:

```
Chrome Process

├── UI Thread
├── Network Thread
├── Rendering Thread
├── Audio Thread
├── Download Thread
```

All these threads belong to the same Chrome process.

---

## c) Why do programs use multiple threads?

Modern applications perform many tasks at the same time.

Instead of doing everything one after another, they create multiple threads.

This makes applications faster and more responsive.

### Example

While watching a YouTube video, Chrome is simultaneously:

- Playing the video
- Playing the audio
- Loading comments
- Downloading more video data
- Detecting mouse clicks
- Running JavaScript

Multiple threads allow all these tasks to happen concurrently.

---

## d) Process vs Thread

| Process | Thread |
|----------|---------|
| Running program | Smallest unit of execution |
| Has its own memory space | Shares the process memory |
| Has its own PID | Does not have its own process |
| More expensive to create | Faster and lighter |
| Isolated from other processes | Shares resources with other threads |

---

## e) Why are Threads faster?

Creating a new process requires the operating system to:

- Allocate a new memory space
- Assign a PID
- Allocate system resources
- Create a new security context

Creating a thread is much simpler because it shares the existing process's memory and resources.

For this reason, creating threads is much faster than creating processes.

---

## f) What happens if one Thread crashes?

Threads inside the same process share memory.

If one important thread crashes, it can sometimes cause the entire process to crash.

However, other processes continue running normally because each process has its own isolated memory space.

Example:

If Chrome crashes,

Microsoft Word usually continues running without any problems.

---

## g) Real-World Example

Suppose you open Google Chrome.

The operating system creates one Chrome process.

Inside that process are many threads:

- UI Thread
- Rendering Thread
- Network Thread
- Audio Thread
- Video Thread
- Download Thread

Each thread performs a different task.

Together they make Chrome smooth and responsive.

---

## h) Multithreading

**Multithreading** is the ability of a process to execute multiple threads at the same time.

Modern applications use multithreading to improve performance and responsiveness.

Examples include:

- Google Chrome
- Microsoft Word
- Discord
- Spotify
- Visual Studio Code
- Games

---

## i) Advantages of Threads

- Better responsiveness
- Faster execution
- Lower memory usage
- Efficient CPU utilization
- Easy communication between threads

---

## Conclusion: Process vs Thread

A process is a running program created by the operating system.

Every process receives its own PID, memory space, system resources, and security context.

A thread is the smallest unit of execution inside a process.

One process can contain many threads that share the same memory and resources.

Modern applications use multithreading so multiple tasks can run simultaneously, making applications faster and more responsive.

---

## Common Misconceptions

❌ A process and a thread are the same thing.

✔️ A process is a running program. A thread is a task running inside that process.

---

❌ Every process has only one thread.

✔️ Most modern applications have many threads.

---

❌ Threads have their own memory.

✔️ Threads inside the same process share memory and resources.

---

## Self Review Questions

1. What is a process?
2. What is a thread?
3. What resources does every process receive?
4. What is a PID?
5. Why are threads faster than processes?
6. What is multithreading?
7. What happens if one thread crashes?
8. Explain the difference between a process and a thread.
