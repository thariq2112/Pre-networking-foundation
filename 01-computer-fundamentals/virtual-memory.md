# 3. What Happens When RAM Is Full? (Virtual Memory)

## a) Why does RAM become full?

RAM (Random Access Memory) is the computer's temporary working memory.

Every running application uses a portion of RAM to store its instructions and data.

For example, if your computer has **16 GB of RAM**, only 16 GB of programs and data can be stored in memory at one time.

As you open more applications, more RAM is used.

Example:

- Google Chrome
- Microsoft Word
- Spotify
- Discord
- Visual Studio Code

Each application occupies some RAM.

Eventually, the available RAM becomes limited.

---

## b) What happens when RAM becomes full?

When RAM is nearly full, the operating system does **not** immediately close your applications.

Instead, it uses a feature called **Virtual Memory**.

Virtual Memory uses a portion of the SSD or HDD as temporary storage for memory pages that are not currently being used.

In Windows, this storage area is called the **Page File**.

In Linux, it is called **Swap Space**.

The operating system moves less frequently used pages from RAM to the Page File.

This frees up RAM so active applications can continue running.

---

## c) What is Virtual Memory?

Virtual Memory is a memory management technique used by the operating system.

It extends the usable memory of a computer by using part of the storage device as temporary memory.

Virtual Memory is **not** a replacement for RAM.

It simply provides extra space when physical RAM is exhausted.

Because SSDs and HDDs are much slower than RAM, Virtual Memory keeps the system running but with reduced performance.

---

## d) What is a Page?

Programs stored in RAM are divided into small fixed-size blocks called **Pages**.

Instead of moving an entire program between RAM and storage, the operating system moves only the pages that are not currently needed.

This makes memory management much more efficient.

Example:

Google Chrome may use thousands of pages.

If several tabs have not been used recently, Windows can move only those pages to the Page File while keeping the active tabs in RAM.

---

## e) What is Paging?

**Paging** is the process of moving pages between RAM and Virtual Memory.

When RAM becomes full:

1. The operating system identifies pages that are not actively being used.
2. Those pages are copied from RAM to the Page File.
3. RAM space becomes available for active applications.

Later, if the CPU needs one of those pages again:

1. Windows retrieves the page from the Page File.
2. The page is copied back into RAM.
3. The CPU continues executing the program.

---

## f) What is a Page Fault?

A **Page Fault** occurs when the CPU requests a page that is not currently available in RAM.

The operating system checks where that page is located.

If it is stored in Virtual Memory, Windows loads it back into RAM before the CPU continues execution.

Page Faults are a normal part of modern operating systems.

---

### Are all Page Faults slow?

No.

There are two main types of Page Faults.

### Soft (Minor) Page Fault

The required page is already available somewhere in physical memory.

The operating system only needs to update its memory mapping.

This happens quickly and usually has little or no noticeable impact on performance.

### Hard (Major) Page Fault

The required page is not in RAM.

Windows must retrieve it from the Page File stored on the SSD or HDD.

Because storage devices are much slower than RAM, Hard Page Faults take longer and may cause temporary slowdowns.

Therefore, **not every Page Fault indicates a performance problem**.

Only frequent Hard Page Faults usually affect system performance.

---

## g) Why is Virtual Memory slower?

RAM is designed for extremely fast access.

Storage devices are designed for permanent data storage.

Approximate speed hierarchy:

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
SSD
      ↓
HDD
```

Because Virtual Memory uses SSDs or HDDs instead of RAM, accessing it is significantly slower.

---

### Is High RAM Usage Bad?

Not necessarily.

Modern operating systems intentionally use available RAM to improve performance.

Windows keeps recently used programs and data in RAM so they can be accessed quickly if needed again.

This behavior is called **memory caching**.

For example:

- You close Google Chrome.
- Windows keeps some of Chrome's data in RAM.
- If you open Chrome again shortly afterward, it may launch faster because some of its data is already cached.

Therefore, seeing **80–90% RAM usage in Task Manager is not automatically a problem**.

High RAM usage only becomes an issue when Windows must constantly move pages between RAM and the Page File.

---

## h) What is Thrashing?

**Thrashing** occurs when the operating system spends more time moving pages between RAM and Virtual Memory than actually executing programs.

This usually happens because:

- Too many applications are open.
- The computer does not have enough physical RAM.

Common symptoms include:

- Slow system performance
- Constant SSD or HDD activity
- Programs freezing
- Long loading times

The best solutions are:

- Close unnecessary applications.
- Upgrade the system's RAM.

---

## i) Real-World Example

Imagine your computer has **8 GB of RAM**.

You open:

- Google Chrome
- Microsoft Word
- Spotify
- Discord
- Visual Studio Code
- Photoshop

RAM eventually becomes full.

Windows moves inactive Chrome tabs and other unused memory pages to the Page File.

When you return to those tabs later, Windows copies them back into RAM.

If this happens occasionally, you may notice only a slight delay.

If it happens continuously, the computer becomes noticeably slower.

---

## Conclusion: What Happens When RAM Is Full?

RAM has a limited capacity.

When RAM becomes full:

1. The operating system does not immediately stop running programs.
2. It uses Virtual Memory to extend available memory.
3. Inactive pages are moved from RAM to the Page File.
4. Active programs continue running using the freed RAM.
5. If those pages are needed again, Windows copies them back into RAM.
6. Occasional paging is normal.
7. Frequent Hard Page Faults and excessive paging can reduce performance.
8. If the operating system spends most of its time moving pages instead of executing programs, thrashing occurs.

Virtual Memory allows the computer to continue operating even when physical RAM is full, but it is much slower than using real RAM.

---

## Common Misconceptions

❌ A Page Fault always means the computer is slow.

✔️ False. Soft Page Faults are normal and usually complete quickly.

---

❌ High RAM usage is always bad.

✔️ False. Windows intentionally uses available RAM for caching to improve performance.

---

❌ Virtual Memory is extra RAM.

✔️ False. Virtual Memory uses storage devices as temporary overflow space and is much slower than physical RAM.

---

## Self Review Questions

1. Why does RAM become full?
2. What is Virtual Memory?
3. What is a Page?
4. What is Paging?
5. What is the difference between a Soft and Hard Page Fault?
6. Why is Virtual Memory slower than RAM?
7. Why is high RAM usage not always a problem?
8. What is Thrashing?
9. How does Windows continue running programs when RAM is full?
