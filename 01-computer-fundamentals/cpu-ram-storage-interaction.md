# 2. CPU, RAM & Storage Interaction

## a) What is the CPU?

The **CPU (Central Processing Unit)** is the brain of the computer.

Its job is to execute instructions from programs and perform calculations.

However, the CPU does **not** usually read instructions directly from RAM.

Between the CPU and RAM is an even faster type of memory called **Cache**.

The CPU normally fetches instructions from **Cache**, and the cache is automatically filled with frequently used data from RAM.

This makes program execution much faster because accessing RAM every time would slow the CPU down.

### Memory Hierarchy (Fastest → Slowest)

```
CPU Registers
      ↓
L1 Cache
      ↓
L2 Cache
      ↓
L3 Cache
      ↓
RAM
      ↓
SSD / HDD
```

The closer the memory is to the CPU, the faster it can be accessed.

### Example

When you open Google Chrome:

- Windows loads Chrome into RAM.
- Frequently used instructions are copied into the CPU Cache.
- The CPU fetches instructions from Cache.
- If the required instruction is not in Cache (a **Cache Miss**), it is retrieved from RAM and stored in Cache for future use.

Without the CPU, no program can run.

---

## b) What is RAM?

**RAM (Random Access Memory)** is the computer's temporary working memory.

RAM stores programs and data that are currently being used.

RAM is **volatile memory**, which means its contents are lost when the computer loses power or shuts down.

Because RAM is much faster than storage devices, programs must be loaded into RAM before they can execute.

### Example

When Chrome starts:

- Chrome is copied from the SSD into RAM.
- Frequently used data is copied from RAM into Cache.
- The CPU executes instructions from Cache.

If you close Chrome, the RAM used by Chrome becomes available for other programs.

---

## c) What is Storage?

Storage refers to devices such as **SSDs** and **HDDs**.

Storage permanently keeps:

- Programs
- Documents
- Photos
- Videos
- Operating System files

Storage is **non-volatile memory**, meaning the data remains even after the computer is turned off.

### Example

Chrome.exe is stored on the SSD.

It remains there until Windows loads it into RAM.

---

## d) What is Cache?

Cache is a very small, extremely fast type of memory located inside or very close to the CPU.

Its purpose is to reduce the time the CPU spends waiting for data from RAM.

Frequently used instructions and data are automatically stored in Cache.

Modern processors usually contain three levels of cache:

- **L1 Cache** – Smallest and fastest.
- **L2 Cache** – Larger but slightly slower.
- **L3 Cache** – Largest cache, shared between CPU cores.

Even L3 Cache is significantly faster than RAM.

---

## e) How do CPU, Cache, RAM and Storage work together?

Imagine you double-click Chrome.

### Step 1

Windows finds **Chrome.exe** on the SSD.

↓

### Step 2

Windows copies Chrome into RAM.

↓

### Step 3

Frequently used instructions are copied into the CPU Cache.

↓

### Step 4

The CPU fetches instructions from Cache.

↓

### Step 5

If the instruction is not in Cache (Cache Miss), Cache retrieves it from RAM.

↓

### Step 6

The CPU decodes and executes the instruction.

↓

### Step 7

Chrome opens on your screen.

This interaction happens every time you start an application.

---

## f) Why can't the CPU execute directly from Storage?

Storage devices are designed for **long-term data storage**, not for high-speed execution.

Although SSDs are much faster than HDDs, they are still much slower than RAM and Cache.

If the CPU had to execute every instruction directly from the SSD, it would spend most of its time waiting for data instead of processing instructions.

Instead, Windows follows this process:

```
SSD/HDD
      ↓
RAM
      ↓
CPU Cache
      ↓
CPU
```

This ensures programs execute as quickly as possible.

---

## g) What happens when RAM becomes full?

If RAM becomes full, the operating system uses **Virtual Memory**.

Virtual Memory is a portion of the SSD or HDD that acts as an extension of RAM.

Windows moves less frequently used data from RAM to a **Page File** (also called a Swap File).

This frees RAM for programs that need it immediately.

Although Virtual Memory prevents programs from crashing, it is much slower than real RAM because SSDs and HDDs have higher access times.

---

## h) Real-World Example

Suppose you open Microsoft Word.

1. Word.exe is stored on the SSD.
2. Windows copies Word into RAM.
3. Frequently used instructions are copied into Cache.
4. The CPU executes instructions from Cache.
5. As you type, RAM stores temporary data while the CPU processes every keystroke.
6. If RAM becomes full, Windows may temporarily move inactive data to Virtual Memory.

---

## CPU vs Cache vs RAM vs Storage

| Component | Primary Purpose | Volatile? | Relative Speed |
|------------|-----------------|-----------|----------------|
| CPU | Executes instructions | No | Fastest processor |
| Cache | Stores frequently used data for the CPU | Yes | Faster than RAM |
| RAM | Stores running programs and data | Yes | Faster than Storage |
| SSD/HDD | Permanent storage | No | Slowest in this hierarchy |

---

## Conclusion: CPU, Cache, RAM & Storage Interaction

Every program follows the same interaction between these components.

1. Programs are permanently stored on an SSD or HDD.
2. The operating system loads the program into RAM.
3. Frequently used instructions and data are copied into CPU Cache.
4. The CPU fetches instructions from Cache.
5. If necessary, Cache retrieves missing data from RAM.
6. The CPU executes the instructions.
7. If RAM becomes full, Windows uses Virtual Memory to temporarily store less frequently used data.

In simple terms:

```
Storage
      ↓
RAM
      ↓
Cache
      ↓
CPU
```

Each layer exists to reduce the time the CPU spends waiting for data.

---

## Self Review Questions

1. What is the role of the CPU?
2. Why does the CPU use Cache instead of accessing RAM every time?
3. What is the difference between volatile and non-volatile memory?
4. Why can't programs execute directly from an SSD?
5. What happens when RAM becomes full?
6. What is Virtual Memory?
7. Explain how CPU, Cache, RAM and Storage work together when opening Chrome.
