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
Launched on September 5, Voyager 1 is one of the two space probes launched by NASA in 1977. It holds the record for traveling further than any man-made object originating from Earth. It is currently drifting through interstellar space at a speed of around 17 kilometers per second, over 15 billion miles from Earth. It operates on legacy computer architecture built during the 1970s, acting as a sort of time capsule of early computing. Because of the distance, any radio command sent to the space probe takes around 23.5 hours to arrive, making a full communication round-trip take 47 hours.

### 2. Background/Context of Voyager 1 FDS Failure
In November 2023, the Telemetry Modulation Unit (TMU) of Voyager 1 suddenly stopped sending readable data, instead transmitting a gibberish pattern of binary 1s and 0s. After months of remote debugging, NASA pinpointed the root cause: a corrupted 256-word memory chip inside the Flight Data Subsystem (FDS). Since physical repair is impossible to do, the spacecraft's operating code on that faulty chip had to be relocated to a different memory.

### 3. Why This is a Computer Architecture Topic (Problem & Solution)
This situation is a perfect real-world example of extreme hardware constraints and memory mapping. It highlights exactly how software instructions are permanently tied to physical memory addresses. Working with highly restricted 1970s memory banks, NASA engineers had to calculate the exact byte sizes of the stranded instructions and chop the code into smaller fragments. From there, they meticulously rewrote the internal memory pointers so the CPU could pull and execute these scattered pieces of code seamlessly across different, non-contiguous hardware blocks.

---

## III. Interactive Element: "Fix Voyager's RAM"

> **The Concept:** An *Among Us* style 2D interactive game focused on memory defragmentation, replacing standard mini-games like "Fix Wiring" or "Download Data."

*   **User Flow:** The visitor encounters a retro control panel flashing a red "COMMS FAILURE" warning, outputting gibberish binary text. They must open the "FDS Diagnostics" tab, revealing a grid of memory blocks where one corrupted block is glowing red. The visitor must manually drag and drop smaller "code fragments" from the bad block into scattered, non-contiguous "healthy" RAM slots without exceeding their byte capacity.
*   **Relation to the Problem and Solution:** This gamified task shows the real-world engineering challenge NASA faced. At first, the task shows gibberish memory data, which represents the actual garbled telemetry caused by the hardware fault. By forcing the user to manually slice code and fit it into constrained, non-contiguous spaces, they practically experience the difficulty of memory allocation and fragmentation. Once they solve the puzzle, a "Task Complete" animation plays just like in the real Among Us game, and the telemetry dashboard restores to clean data, perfectly mirroring NASA's successful software patch solution.

---

## IV. Technical Stack

To build this highly interactive exhibit, our group will utilize a modern web stack that satisfies all project requirements:

| Technology | Implementation Details |
| :--- | :--- |
| **Astro 6 & Node.js 26** | This is based on the template repository that will be forked. |
| **MDX (Markdown Extended)** | This lets us write out the historical Voyager story in standard markdown while allowing us to drop our interactive React components straight into the text wherever we need them. |
| **React & TypeScript** | This will be the main stack that will run the interactive Among Us style minigame. React will be used to manage all the moving parts of the memory block in the minigame. While TypeScript is used to ensure strict data typing for the whole project. |
| **Tailwind CSS** | Tailwind CSS will handle the styling for the whole project. It provides utility classes to efficiently style the retro 1970s NASA aesthetic mixed with vibrant, touch-friendly, and mobile-responsive UI for the gamified tasks. |

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

### Site References & Inspiration

*   [Star Wars Eclipse Website](https://www.starwarseclipse.com/)
*   [Solar System Scope](https://www.solarsystemscope.com/)
*   [Prototype of the new NASA site (Pinterest Reference)](https://ph.pinterest.com/pin/422281211192498/)