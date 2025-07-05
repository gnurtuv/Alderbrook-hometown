# Alderbrook Echoes
### A Self-Contained Visual Novel Experience

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://en.wikipedia.org/wiki/HTML5)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://en.wikipedia.org/wiki/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://www.javascript.com)
[![SVG](https://img.shields.io/badge/SVG-FFB13B?style=for-the-badge&logo=svg&logoColor=white)](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

A short, elegant visual novel that runs entirely in a web browser from a single HTML file. It tells the story of Avery and Cassian reconnecting after years apart, exploring themes of memory, nostalgia, and identity through sophisticated dialogue and dynamic, context-aware visuals.

There are **no external images, libraries, or dependencies**. Everything you see is generated on-the-fly with SVG and animated with pure CSS and JavaScript.

---

## ✨ Key Features

*   🎨 **Dynamic SVG Visuals:** All characters and environments are rendered as Scalable Vector Graphics, ensuring a crisp, illustrative style that looks great on any screen.
*   🎭 **Contextual Storytelling:** The background art transforms to reflect the emotional subtext of the conversation—from a hazy, forgotten town to cracked roads and echoing cityscapes.
*   🎬 **Subtle & Illustrative Animations:** Characters feel alive with subtle breathing animations. The active speaker is highlighted, dialogue appears with a typewriter effect, and scenes transition smoothly.
*   🖋️ **Elegant & Evocative Dialogue:** The conversation between Avery and Cassian uses advanced vocabulary and subtext, creating a mature and contemplative tone.
*   📦 **Zero Dependencies, Single File:** The entire experience is contained within one `.html` file. No need for a server, no `npm install`, no external files. Just download and open.

---

## 🚀 Getting Started

Running this visual novel is as simple as it gets:

1.  **Create a File:** Create a new file on your computer named `alderbrook.html`.
2.  **Copy & Paste:** Copy the entire code block provided.
3.  **Save:** Paste the code into your `alderbrook.html` file and save it.
4.  **Open:** Open the file in any modern web browser (like Chrome, Firefox, or Safari).

That's it! Click anywhere on the screen to advance the story.

---

## 🛠️ How It Works: A Technical Deep Dive

This project serves as a demonstration of what's possible with modern, vanilla web technologies.

### The Story Engine

The narrative is driven by a simple JavaScript array of objects. Each object represents a line of dialogue and contains all the necessary state information:

```javascript
const story = [
    {
        character: "Avery",
        text: "It's been... what, almost a decade since we left Alderbrook?",
        background: "bg-hazy-town", // The ID of the background SVG to display
        avery: "active",           // 'active' makes the character bright (speaker)
        cassian: "present",        // 'present' keeps the character on screen but dim
        cassianExpr: "neutral"     // Controls SVG facial expressions
    },
    // ... more lines
];
```
A `displayLine()` function reads the current line from the array and updates the DOM, while a `typewriter()` function handles the text animation.

### Pure SVG Art & Animation

*   **Characters & Backgrounds:** Instead of `.png` or `.jpg` files, all visuals are `<svg>` elements embedded directly in the HTML. This makes the project self-contained and infinitely scalable.
*   **Dynamic Backgrounds:** Backgrounds are not static. The "cracked roads" background uses SVG `<animate>` tags to draw the lines when the scene loads. The "parallel paths" background uses a combination of `<animate>` and `stroke-dasharray` to create a feeling of infinite, uncertain movement.
*   **Character Expressions:** Cassian's smirk is achieved by hiding one `<path>` (the neutral mouth) and showing another within the same SVG, controlled via JavaScript.

### CSS-Driven Dynamics

*   **Highlighting:** A simple `.active` class is toggled on the speaker's SVG. CSS handles the `filter: brightness(1)` transition, creating a smooth focus shift. This approach avoids inline styles and keeps the logic clean.
*   **Breathing Animation:** A subtle, infinite `characterBreathe` keyframe animation is applied to all characters, which uses `transform: translateY()` to give them a lifelike quality.
*   **Scene Transitions:** Backgrounds fade in and out using `opacity` transitions, ensuring a cinematic flow between narrative beats.

---

> ### A Glimpse of the Dialogue
>
> 👤 **Avery:**  
> > You make it sound poetic. I remember more potholes than poetry.
>
> 👤 **Cassian:** (smirking)  
> > The roads were metaphorical, too—cracked, winding, resistant to smooth passage.

---

## 📜 License

This project is licensed under the MIT License. Feel free to use, modify, and learn from it.