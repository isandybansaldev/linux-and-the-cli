# Complete intro to the Linux and the CLI

This is an introduction on how to use command line and in the process we will learn linux too.

## What we will cover

- **What is Linux?**
- **What problems Linux solves for you?**
- **How Linux is generally laid out?**
- **What the command line is?**
- **Basic navigation in the command line**
- **Common tasks with the command line**
- **Some basic customizations**

## What is Linux?

Linux is a unix-like operating system, MacOS and FreeBSD would be two more examples of unix-like operating system.

Unix was created in the 70s at Bell Labs. A big part of unix software is the idea of the **Unix Philosophy**. The idea is instead of having few very specialized tools (or programs) we should have many small composable tools that we can use to compose to solve larger problems.

```java
Original Unix (1969)
├── V6 Unix (1975)
│   ├── PWB/UNIX               → Internal Bell Labs dev tools
│   └── Unix/32V (1978)        → 32-bit port of V6
│       └── V7 Unix (1979)     → Clean, portable Unix; base of most descendants
│           ├── BSD (3BSD → 4.4BSD)       → Research-focused, networked Unix
│           │   ├── NetBSD (1993)         → Portable
│           │   ├── FreeBSD (1993)        → Stable and fast
│           │   ├── OpenBSD (1995)        → Secure
│           │   └── Darwin/macOS (2001)   → Apple’s Unix
│           └── System III → System V     → AT&T’s commercial Unix line
│               ├── SVR4 (1989)           → Merged BSD, Sun, System V
│               │   ├── Solaris (Sun)     → Once dominant enterprise Unix
│               │   ├── AIX (IBM)         → Enterprise use
│               │   ├── HP-UX (HP)        → HP’s proprietary Unix
│               │   └── SCO Unix          → Controversial lawsuits
├── MINIX (1987)               → Educational, small OS
│   └── Linux Kernel (1991)    → Unix-like, modern open-source OS kernel
│       ├── Debian, Red Hat, Ubuntu, etc. → Linux distros
│       └── Android (2008)     → Mobile OS based on Linux

```

---

## 📝 Notes:

- **BSD** evolved from V7 and introduced networking and open-source licensing.
- **System V** was AT&T’s effort to standardize and commercialize Unix.
- **MINIX** was a teaching OS that inspired **Linux**, which is Unix-like but not Unix-derived.
- **macOS** is a certified Unix built on a BSD foundation.
- **Linux** became the most widely adopted Unix-like system, especially in servers, embedded devices, and Android.

---

## How to run Linux using VM

- Install multipass (https://canonical.com/multipass/install)
- Virtual box by oracle is also a good option too.
