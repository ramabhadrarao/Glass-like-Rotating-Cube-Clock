# Glass-like Rotating Cube Clock

This repository contains code to create a glass-like rotating cube that functions as a clock. It utilizes HTML, CSS, and JavaScript to produce an animated 3D cube displaying the current time on its faces.

## Description

### HTML Structure:
- `DOCTYPE Declaration` specifies the document type and version.
- `HTML Tags` create the basic structure, including head and body sections.
- `Container Div` holds the rotating cube.

### CSS Styling:
- `Body Styling` centers content and sets the background color for the page.
- `Container Styling` establishes a perspective for 3D transforms.
- `Cube Styling` sets size, position, and 3D transform properties.
- `Cube Face Styling` defines appearance, positioning, and text properties for each face.

### JavaScript Functionality:
- `updateTime Function` retrieves and displays the current time.
- Generates random transparent colors and applies them to each face.
- Updates the content of each face with the current time string.

## Functionality

- **Visual Representation:** 3D cube with rotating faces representing different times.
- **Animation:** Smooth and continuous rotation using CSS animations and transforms.
- **Color and Styling:** Glass-like effects with random transparent colors.
- **Time Display:** Current time displayed on each face, updating every second.
- **Smoothness Enhancement:** Improved rotation smoothness with a `cubic-bezier` timing function.

Feel free to adjust sizes, colors, or timings to customize the cube's appearance and behavior further.

## Usage

To use the code, simply copy the HTML, CSS, and JavaScript snippets into your project files.

### Example

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Glass-like Rotating Cube Clock</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
      background-color: #f0f0f0;
    }

    .container {
      perspective: 1000px; /* Increased perspective for depth */
    }

    .cube {
      width: 300px; /* Increased width */
      height: 300px; /* Increased height */
      position: relative;
      transform-style: preserve-3d;
      animation: rotate 10s linear infinite; /* Slower rotation */
    }

    .cube div {
      position: absolute;
      width: 300px; /* Increased width */
      height: 300px; /* Increased height */
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 48px; /* Adjusted font size */
      font-family: Arial, sans-serif;
      text-align: center;
      backface-visibility: hidden;
      border-radius: 15px; /* Adjusted border radius */
      background: linear-gradient(45deg, rgba(255, 255, 255, 0.1), rgba(0, 0, 0, 0.1));
      box-shadow: 0 0 20px rgba(255, 255, 255, 0.3), inset 0 0 20px rgba(255, 255, 255, 0.1);
      color: #ffffff; /* Highlighted text color */
    }

    .front {
      transform: translateZ(150px); /* Adjusted translateZ */
    }

    .back {
      transform: rotateY(180deg) translateZ(150px); /* Adjusted translateZ */
    }

    .top {
      transform: rotateX(90deg) translateZ(150px); /* Adjusted translateZ */
    }

    .bottom {
      transform: rotateX(-90deg) translateZ(150px); /* Adjusted translateZ */
    }

    .left {
      transform: rotateY(-90deg) translateZ(150px); /* Adjusted translateZ */
    }

    .right {
      transform: rotateY(90deg) translateZ(150px); /* Adjusted translateZ */
    }

    @keyframes rotate {
      0% {
        transform: rotateX(0) rotateY(0);
      }
      100% {
        transform: rotateX(360deg) rotateY(360deg);
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="cube" id="cube">
      <div class="front" id="front"></div>
      <div class="back" id="back"></div>
      <div class="top" id="top"></div>
      <div class="bottom" id="bottom"></div>
      <div class="left" id="left"></div>
      <div class="right" id="right"></div>
    </div>
  </div>

  <script>
    function updateTime() {
      const now = new Date();
      const timeString = now.toLocaleTimeString();

      document.querySelectorAll('.cube div').forEach(div => {
        const randomAlpha = Math.random();
        const color = `rgba(${Math.floor(Math.random() * 156)}, ${Math.floor(Math.random() * 156)}, ${Math.floor(Math.random() * 156)}, ${randomAlpha})`; /* Adjusted color range */

        div.innerText = timeString;
        div.style.background = `linear-gradient(45deg, ${color}, rgba(0, 0, 0, 0.1))`;
      });
    }

    setInterval(updateTime, 1000);
    updateTime();
  </script>
</body>
</html>
```
## Credits 
- `Created By` Rama Bhadra Rao Maddu.
## License
- This project is licensed under  MIT License
