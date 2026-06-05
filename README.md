# CSARCH2 Virtual Exhibit Proposal

**S03 Group 3**

## Group Members

| Name |
| :--- |
| Gonzaga, Rainer D. |
| Gonzales, Aaron James S. |
| Manalang, Kennese Ross F. |
| Marcaida, Duncan Joseph B. |
| Ramos, Richmond Jose G. |

---

## I. Topic Theme

| Field | Details |
| :--- | :--- |
| **Project Title** | There is an Imposter in the RAM Among Us: Ejecting the Voyager 1 Glitch |
| **Chosen Topic** | The 2024 Voyager 1 Flight Data Subsystem (FDS) Memory Rescue |
| **Category** | Problem-solving stories |

---

## II. Exhibit Narrative Content

### 1. What is Voyager 1?
Launched on September 5, 1977, **Voyager 1** is one of the two space probes launched by NASA. It holds the record for traveling further than any man-made object originating from Earth. It is currently drifting through interstellar space at a speed of around 17 kilometers per second, over 15 billion miles from Earth. It operates on legacy computer architecture built during the 1970s, acting as a sort of time capsule of early computing. Because of the distance, any radio command sent to the space probe takes around 23.5 hours to arrive, making a full communication round-trip take 47 hours.

### 2. Background/Context of Voyager 1 FDS Failure
In November 2023, the **Telemetry Modulation Unit (TMU)** of Voyager 1 suddenly stopped sending readable data, instead transmitting a repeating pattern of binary 1s and 0s. After months of remote debugging, NASA pinpointed the root cause: a corrupted 256-word memory chip inside the **Flight Data Subsystem (FDS)**. Since physical repair is basically impossible, the spacecraft's operating code on that faulty chip had to be relocated to a different memory block.

### 3. Why This is a Computer Architecture Topic (Problem & Solution)
This story is a masterclass in extreme hardware constraints and memory mapping. It illustrates how software instructions are fundamentally tethered to physical memory addresses. Because early memory architecture was so limited back then, NASA had to understand the exact byte sizes of the corrupted instructions, fragment the code into smaller pieces, and then meticulously update the internal memory pointers so the CPU could still execute the fragmented code synchronously across different blocks of hardware.

---

## III. Interactive Element: "Fix Voyager's RAM"

> **The Concept:** An *Among Us* style 2D interactive game focused on memory defragmentation, replacing standard mini-games like "Fix Wiring" or "Download Data."

*   **User Flow:** The visitor encounters a retro control panel flashing a red "COMMS FAILURE" warning, outputting gibberish binary text. They must open the "FDS Diagnostics" tab, revealing a grid of memory blocks where one corrupted block is glowing red. The visitor must manually drag and drop smaller "code fragments" from the bad block into scattered, non-contiguous "healthy" RAM slots without exceeding their byte capacity.
*   **Relation to the Problem and Solution:** This gamified task directly translates the real-world architectural challenge NASA faced. At first, the task shows gibberish which represents the actual garbled telemetry caused by the hardware fault. By forcing the user to manually slice code and fit it into constrained, non-contiguous spaces, they practically experience the difficulty of memory allocation and fragmentation. Once they solve the puzzle, a "Task Complete" animation plays, and the telemetry dashboard restores to clean data, perfectly mirroring NASA's successful software patch solution.

---

## IV. Technical Stack

To build this highly interactive exhibit, our group will utilize a modern web stack that satisfies all project requirements:

| Technology | Implementation Details |
| :--- | :--- |
| **Astro 6 & Node.js 26** | Astro serves as the primary framework for fast, zero-JavaScript static delivery of the narrative, running on the mandatory Node.js 26 environment. |
| **MDX (Markdown Extended)** | Authors the historical Voyager narrative while allowing seamless embedding of our interactive JSX components directly into the text. |
| **React & TypeScript** | Powers the *Among Us* drag-and-drop mini-game. React hooks (e.g., `useState`) manage the complex memory block logic in real-time, while TypeScript ensures strict data typing for the hardware structures. |
| **Tailwind CSS** | Provides utility classes to efficiently style the retro 1970s NASA aesthetic mixed with vibrant, touch-friendly, and mobile-responsive UI for the gamified tasks. |

---

## V. Tentative Style Guide Snapshot & Motif

**Theme:** Retro Space Website  
The visual motif will be a blend of two worlds: the monochromatic aesthetic of 1970s NASA Mission Control terminals for the narrative sections and the vibrant, flat-design UI of an *Among Us* task screen for the interactive mini-game.

### Color Palette & Typography

| Element | Specification |
| :--- | :--- |
| **Background** | Deep Space Black (`#050505`) and Dark Slate (`#1E1E1E`) to create an immersive, void-like backdrop. |
| **Primary Text (Narrative)** | CRT Green (`#00FF41`) or Terminal Amber (`#FFB000`) for paragraphs and headings, mimicking vintage phosphor displays. |
| **Accent / Interactive UI** | "Sus" Red (`#FF0000`) for corrupted memory blocks and errors. Cyan (`#38b6ff`), Yellow (`#ffde59`), and Magenta (`#ff007f`) for draggable "code fragments". |
| **Heading / Terminal Font** | *VT323* or *Share Tech Mono* to simulate early digital computer screen readouts. |
| **Body / Instruction Font** | *Inter* or *Roboto* (sans-serif) for the main narrative and task instructions to ensure maximum readability for the grading panel. |

### Layout & Interface

*   **Content Sections:** A single-column layout centered on the screen, reading like a chronological mission log.
*   **Interactive Area:** The memory grid will be inside a rounded container with a thick, gray border, designed to look like a physical "tablet" or "maintenance panel" the user just pulled up.
*   **Mobile Responsiveness:** The interactive task grid will use flex-wrapping. On desktop, the draggable fragments will sit beside the memory grid. On mobile, they will neatly stack above the grid so users can easily tap-and-drop.

### Site References & Inspiration

*   [Star Wars Eclipse Website](https://www.starwarseclipse.com/)
*   [Solar System Scope](https://www.solarsystemscope.com/)
*   [Prototype of the new NASA site (Pinterest Reference)](https://ph.pinterest.com/pin/422281211192498/)