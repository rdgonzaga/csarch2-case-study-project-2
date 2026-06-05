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
| **Project Title** | Memory Block Blast: Reallocating Voyager 1’s Fragmented Memory Map |
| **Chosen Topic** | The 2024 Voyager 1 Flight Data Subsystem (FDS) Memory Rescue |
| **Category** | Problem-solving stories |

---

## II. Exhibit Narrative Content

### 1. What is Voyager 1?
Launched on September 5, Voyager 1 is one of the two space probes launched by NASA in 1977. It holds the record for traveling further than any man-made object originating from Earth. It is currently drifting through interstellar space at a speed of around 17 kilometers per second, over 15 billion miles from Earth. It operates on legacy computer architecture built during the 1970s, acting as a sort of time capsule of early computing. Because of the distance, any radio command sent to the space probe takes around 23.5 hours to arrive, making a full communication round-trip take 47 hours.

### 2. Background/Context of Voyager 1 FDS Failure
In November 2023, the Telemetry Modulation Unit (TMU) of Voyager 1 suddenly stopped sending readable data, instead transmitting a gibberish pattern of binary 1s and 0s. After months of remote debugging, NASA pinpointed the root cause: a corrupted 256-word memory chip inside the Flight Data Subsystem (FDS). Since physical repair is impossible to do, the spacecraft's operating code on that faulty chip had to be relocated to a different memory.

### 3. Why This is a Computer Architecture Topic (Problem & Solution)
This situation is a real-world example of hardware constraints and memory mapping. It highlights how software instructions are permanently tied to physical memory addresses. Working with highly restricted 1970s memory banks, NASA engineers had to calculate the exact byte sizes of the stranded instructions and chop the code into smaller fragments. From there, they meticulously rewrote the internal memory pointers so the CPU could pull and execute these scattered pieces of code across different, non-contiguous hardware blocks.

### 4. Timeline of the mission

1. September 5, 1977 - Launch of Voyager 1
2. November 14, 2023 - Voyager 1 stopped sending readable science and engineering data back to Earth
3. March 3, 2024 - NASA team noticed that activity from one part of the flight data system stood out from the rest of the garbled data.
4. April 20, 2024 - Mission flight team heard back from the spacecraft after five months.

---

## III. Interactive Element: "Fix Voyager's RAM"

> **The Concept:** 2D Interactive Puzzle Game
> To make the architecture problem interactive, the exhibit will feature an interactive mini-game. Voyager 1’s minigame will be focused on memory defragmentation.

*   **User Flow:** The user will encounter a console with a terminal that is supposed to send updates from Voyager 1 back to Earth. Due to a memory chip failure, memory in the FDS that is responsible for packaging and sending engineering and science data became corrupted. They must transfer packages of code from the old memory chip to the new working memory chip by selecting memory chunks from the old memory chip and selecting a sector in the new memory chip for the memory chunk to transfer to. The user must successfully transfer all necessary code to the new memory chip and initiate CPU Jump Remapping to fix Voyager 1’s output stream.
  
* This gamified task shows the real-world engineering challenge NASA faced. This interactive element relates to CSARCH2 through Binary Data Organization and Memory Addressing. When NASA Engineers first discovered the problem with Voyager 1, they narrowed the failure down to a 256-word block of code responsible for packaging the spacecraft’s engineering data. Voyager 1’s code was sliced into smaller fragments and was reallocated in the memory chip by controlling the processor’s Instruction Pointer, and since the code was spread across the new memory chip, they had to end each fragment with an Assembly JMP instruction to leap across physical memory addresses to the next snippet of code without crashing.
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
The visual motif will be a blend of the monochromatic aesthetic of 1970s NASA Mission Control terminals for the narrative sections and the vibrant, flat-design UI of an Among Us task screen for the interactive mini-game.

### Color Palette & Typography

| Element | Specification |
| :--- | :--- |
| **Background** | Deep Space Black (#050505) and Dark Slate (#1E1E1E) to create an immersive, void-like backdrop. |
| **Primary Text (Narrative)** |  Ghost White (#F8F8FF) and Light Ash (#D3D3D3) for maximum readability against the dark backgrounds. |
| **Accent / Interactive UI** | Alert Red (#E63946) for the corrupted memory block and flashing error messages. |
| **Heading / Terminal Font** | *Century Gothic Bold* or *Space Grotesk* for wide, commanding section titles. |
| **Body / Instruction Font** | *Roboto Mono* for memory addresses and raw data streams, paired with Inter for standard paragraph readability. |

### Layout & Interface

*   **Content Sections:** A single-column layout centered on the screen, reading like a chronological mission log.
*   **Interactive Area:** The memory grid will be inside a rounded container with a thick, gray border, designed to look like a physical "tablet" or "maintenance panel" the user just pulled up.

### Site References & Inspiration

*   [Star Wars Eclipse Website](https://www.starwarseclipse.com/)
*   [Solar System Scope](https://www.solarsystemscope.com/)
*   [Prototype of the new NASA site (Pinterest Reference)](https://ph.pinterest.com/pin/422281211192498/)
