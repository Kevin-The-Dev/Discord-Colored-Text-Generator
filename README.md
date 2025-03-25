# Rebane's Discord Colored Text Generator

A browser-based tool to create colored Discord messages using ANSI color codes, compatible with the latest Discord desktop versions. Built with HTML, Tailwind CSS, and JavaScript, this project features a modern, responsive UI with intuitive text formatting and color customization.

---

## Live Demo

Check out the live project here: [[Live Project Link](https://discord-colored-text-generator-bykevin.vercel.app/)]
---

## Features

- **Text Formatting**: Apply bold and underline styles to selected text.
- **Color Customization**: Choose from 8 foreground (FG) colors and 8 background (BG) colors.
- **Reset Functionality**: Revert to the original welcome message with full formatting.
- **Clear Option**: Empty the text area instantly.
- **Copy to Clipboard**: Generate Discord-compatible ANSI-formatted text with rotating confirmation messages.
- **Responsive Design**: Adapts seamlessly to mobile, tablet, and desktop screens.
- **Tooltips**: Hover over color buttons to see color names with dynamic positioning.

---

## How It Works

### Core Logic

1. **HTML Structure**:
   - Organized into a header, main sections (About, Text Editor, Source Code), and footer.
   - Uses a `contenteditable` `<div>` as the textarea for user input and formatting.
   - Buttons for styles (Reset All, Bold, Line, Clear) and colors (FG: 8 buttons, BG: 8 buttons) are laid out in a responsive grid.

2. **CSS Styling (Tailwind CSS)**:
   - Leverages Tailwind for a Discord-inspired design with a gradient background (`linear-gradient`), shadows, and blur effects (`backdrop-blur-md`).
   - ANSI color classes (e.g., `.ansi-31` for red, `.ansi-45-bg` for blurple background) define the color palette.
   - Responsive utilities (`sm:`, `md:`) adjust font sizes, padding, and layout (e.g., FG/BG grid stacks on mobile, side-by-side on desktop).

3. **JavaScript Functionality**:
   - **Text Editing**:
     - `oninput` sanitizes input, allowing only `<br>` and `<span>` tags with ANSI classes, stripping other HTML.
     - Enter key triggers `document.execCommand('insertLineBreak')` for line breaks.
   - **Style Buttons**:
     - "Reset All" sets the textarea to the original welcome message: `Welcome to <span class="ansi-33">Rebane</span>'s <span class="ansi-45"><span class="ansi-37">Discord</span></span> <span class="ansi-31">C</span><span class="ansi-32">o</span><span class="ansi-33">l</span><span class="ansi-34">o</span><span class="ansi-35">r</span><span class="ansi-36">e</span><span class="ansi-37">d</span> Text Generator!`.
     - "Bold" and "Line" wrap selected text in `<span>` tags with `ansi-1` (bold) or `ansi-4` (underline) classes.
     - "Clear" resets the textarea to empty.
   - **Color Buttons**:
     - FG buttons (ansi-30 to ansi-37) and BG buttons (ansi-40 to ansi-47) apply corresponding ANSI classes to selected text.
     - Tooltips show color names on hover, adjusting position to stay within the viewport.

---

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/Kevin-The-Dev/Discord-Colored-Text-Generator.git
