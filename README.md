# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS3 Transitions & LocalStorage</title>
  <style>
    /* Button and animation styles */
    button {
      padding: 10px 20px;
      font-size: 16px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    button:hover {
      animation: buttonAnim 1s ease-in-out infinite alternate;
    }

    @keyframes buttonAnim {
      0% {
        background-color: #3498db;
        transform: scale(1);
      }
      100% {
        background-color: #e74c3c;
        transform: scale(1.2);
      }
    }

    /* Default (light theme) styles */
    body {
      background-color: white;
      color: black;
      transition: background-color 0.5s, color 0.5s;
    }

    /* Dark theme styles */
    body.dark-theme {
      background-color: #2c3e50;
      color: white;
    }

    /* Button click animation */
    button.clicked {
      animation: clickAnim 0.5s ease-in-out;
    }

    @keyframes clickAnim {
      0% {
        transform: scale(1);
      }
      50% {
        transform: scale(1.2);
      }
      100% {
        transform: scale(1);
      }
    }
  </style>
</head>
<body>

  <button id="themeToggle">Toggle Theme</button>

  <script>
    // Get the button and body element
    const themeButton = document.getElementById('themeToggle');
    const body = document.body();

    // Check if there's a saved theme in localStorage
    if (localStorage.getItem('theme') === 'dark') {
      body.classList.add('dark-theme');
    }

    // Add event listener to toggle theme
    themeButton.addEventListener('click', () => {
      if (body.classList.contains('dark-theme')) {
        body.classList.remove('dark-theme');
        localStorage.setItem('theme', 'light');
      } else {
        body.classList.add('dark-theme');
        localStorage.setItem('theme', 'dark');
      }

      // Trigger animation on click
      themeButton.classList.add('clicked');
      setTimeout(() => {
        themeButton.classList.remove('clicked');
      }, 1000); // Animation duration
    });
  </script>
</body>
</html>



