# HTML CSS JS ClockProject

## Overview

The "Clock" project is a digital clock implemented using HTML, CSS, and JavaScript. It displays a real-time analog and digital clock and offers a toggle to switch between light and dark themes.

## Table of Contents

1. Project Structure
2. HTML Structure
3. CSS Explanation
4. JavaScript Functionality
5. Contribution
6. License

## 1. Project Structure

- `index.html`: Contains the basic HTML structure.
- `style.css`: Contains the styling for the webpage.
- `script.js`: Contains the logic for the clock functionality and theme toggling.

## 2. HTML Structure

### Key Elements:

- **Toggle Button**: Toggles between dark and light themes.
  
  <button class="toggle">Dark mode</button>
  Clock Container: Contains the clock with needles for hours, minutes, and seconds.

<div class="clock-container">
  <div class="clock">
    <div class="needle hour"></div>
    <div class="needle minute"></div>
    <div class="needle second"></div>
    <div class="center-point"></div>
  </div>
  <div class="time"></div>
  <div class="date"></div>
</div>

Script Link: Connects the JavaScript file.

<script src="script.js"></script>

3. CSS Explanation

Key Styles:

General Styles: Resets and sets font and background colors.

* {
  box-sizing: border-box;
}

:root {
  --primary-color: #000;
  --secondary-color: #fff;
}

Dark Theme Handling: Changes colors based on the theme toggle.

html.dark {
  --primary-color: #fff;
  --secondary-color: #333;
  background-color: #111;
  color: var(--primary-color);
}

Toggle Button: Styles the button for switching themes.

.toggle {
  cursor: pointer;
  background-color: var(--primary-color);
  color: var(--secondary-color);
  border: 0;
  border-radius: 4px;
  padding: 8px 12px;
  position: absolute;
  top: 100px;
}

Clock and Needles: Positions and styles the clock face and needles.

.clock-container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
}

.clock {
  position: relative;
  width: 200px;
  height: 200px;
}

.needle {
  background-color: var(--primary-color);
  position: absolute;
  top: 50%;
  left: 50%;
  height: 65px;
  width: 3px;
  transform-origin: bottom center;
  transition: all 0.5s ease-in linear;
}

4. JavaScript Functionality

Key Features:

Theme Toggle: Allows switching between light and dark modes.

toggle.addEventListener('click', (e) => {
  const html = document.querySelector('html')
  if (html.classList.contains('dark')) {
      html.classList.remove('dark')
      e.target.innerHTML = 'Dark mode'
  } else {
      html.classList.add('dark')
      e.target.innerHTML = 'Light mode'
  }
})

Clock Update: Updates the position of the needles and displays the current time and date.

function setTime() {
  const time = new Date();
  const hoursForClock = hours >= 13 ? hours % 12 : hours;
  // Sets needle rotations and time display
  hourEl.style.transform = `translate(-50%, -100%) rotate(${scale(hoursForClock, 0, 12, 0, 360)}deg)`;
}

Scale Function: Maps a number from one range to another.

const scale = (num, in_min, in_max, out_min, out_max) => {
    return (num - in_min) * (out_max - out_min) / (in_max - in_min) + out_min;
}

5. Contribution

If you wish to contribute to this project, feel free to:

Fork the repository.

Create a new branch (git checkout -b feature-branch).

Commit your changes (git commit -m "Description of changes").

Push to the branch (git push origin feature-branch).

Create a pull request for review.

6. License

This project is open-source and available under the MIT License.

Now, you can copy and paste this documentation directly into your `README.md` file for GitHub or any other purpose.

