# 🎯 JavaScript Event Handling & Interactive Elements Assignment

Welcome to the **ultimate JavaScript playground**! 🎉 This assignment is where we turn boring web pages into dynamic, responsive, *alive* experiences. Get ready to master **event handling**, build **interactive components**, and validate forms like a pro! 💪

## 📁 Assignment Structure

```
📂 js-event-assignment/
├── index.html         # Your playground – where it all comes together
├── style.css          # Keep it cute (optional but encouraged)
└── script.js          # The JavaScript wizardry happens here
```

---

## 🧪 What to Build

Here’s what your interactive bundle of joy should include:

### 1. Event Handling 🎈  
- Button click ✅  
- Hover effects ✅  
- Keypress detection ✅  
- Bonus: A secret action for a *double-click* or *long press* 🤫

### 2. Interactive Elements 🎮  
- A button that changes text or color  
- An image gallery or slideshow  
- Tabs or accordion-style content  
- Bonus: Add some animation using JS or CSS ✨

### 3. Form Validation 📋✅  
- Required field checks  
- Email format validation  
- Password rules (e.g., min 8 characters)  
- Bonus: Real-time feedback while typing

---

## 🧙‍♂️ Pro Tips

- Keep your code clean and commented – your future self will thank you!
- Think about **user experience** – what makes your site more *fun* to use?
- Don’t be afraid to **Google and experiment** – that’s how real developers roll!

---

## 🎉 Now Go Make It Fun!

Remember – this isn't just code. It's your **first step toward creating magical user experiences**. So play around, break stuff (then fix it), and most of all, have FUN! 😄

Happy Coding! 💻✨  

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Playground</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Welcome to the Interactive Playground!</h1>

  <!-- Button for clicking -->
  <button id="myButton">Click Me!</button>

  <!-- Hover effect -->
  <div id="hoverDiv">Hover over me!</div>

  <!-- Form for validation -->
  <form id="myForm">
    <input type="email" id="email" placeholder="Email" required>
    <input type="password" id="password" placeholder="Password" required>
    <button type="button" id="submitBtn">Submit</button>
  </form>

  <!-- Image gallery and navigation -->
  <img id="imageGallery" src="image1.jpg" alt="Gallery">
  <button id="nextButton">Next Image</button>

  <script src="script.js"></script>
</body>
</html>

body {
  font-family: Arial, sans-serif;
  text-align: center;
}

button {
  margin: 20px;
  padding: 10px;
  cursor: pointer;
}

#hoverDiv {
  width: 200px;
  height: 100px;
  background-color: lightgray;
  margin: 20px auto;
}

img {
  width: 300px;
  height: 200px;
  display: block;
  margin: 20px auto;
}

// Event Handling
document.getElementById("myButton").addEventListener("click", function() {
    alert("Button clicked!");
});

document.getElementById("hoverDiv").addEventListener("mouseover", function() {
    this.style.backgroundColor = "lightblue";
});

document.getElementById("hoverDiv").addEventListener("mouseout", function() {
    this.style.backgroundColor = "";
});

document.addEventListener("keydown", function(event) {
    if (event.key === "Enter") {
        alert("Enter key pressed!");
    }
});

// Button that changes text on click
document.getElementById("myButton").addEventListener("click", function() {
    this.innerHTML = "You clicked me!";
});

// Image Gallery (Image slider)
let images = ["image1.jpg", "image2.jpg", "image3.jpg"];
let currentIndex = 0;

function showNextImage() {
    currentIndex = (currentIndex + 1) % images.length;
    document.getElementById("imageGallery").src = images[currentIndex];
}

document.getElementById("nextButton").addEventListener("click", showNextImage);

// Form Validation (Required, Email and Password)
document.getElementById("submitBtn").addEventListener("click", function(event) {
    const emailField = document.getElementById("email");
    const passwordField = document.getElementById("password");

    if (!emailField.value.includes("@")) {
        alert("Please enter a valid email.");
        event.preventDefault();
    }

    if (passwordField.value.length < 8) {
        alert("Password must be at least 8 characters.");
        event.preventDefault();
    }
});

