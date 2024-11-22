# malikUmarTest.github.io![Firefox-nighty-logo](https://github.com/user-attachments/assets/9c72d2ea-c98a-4b74-bfbb-07ceee61309a)
![pngegg](https://github.com/user-attachments/assets/dee55e6e-1f7f-4bd1-99ca-e34336e486c5)
<!doctype html>
<html lang="en-US">

<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width" />
  <link rel="stylesheet" href="styles/styles.css">
  <title>My test page</title>
</head>

<body>
  <h1>Mozilla is cool</h1>
  <img src="images/Firefox-nighty-logo.png" alt="Firefox Nighty Logo image-A blue fox covering earth" />
  <p>At Mozilla, we are global community of</p>
  <ul>
    <li>technologist</li>
    <li>thinkers</li>
    <li>builders</li>
  </ul>
  <p>working together to keep the Internet alive and accessible,
    so people worldwide can be informed contributors and creators of the Web.
    We believe this act of human collaboration across an open platform is essential
    to individual growth and our collective future.</p>

  <p> Read the <a href="">Mozilla Manifesto</a> to learn even more about the values and principles that guide the
    pursuit of our mission.</p>
  <button>Change User</button>
  <script src="scripts/main.js"></script>
</body>

</html>

p, li{
    color: red;
    font-size: 16px;
    line-height: 2;
    letter-spacing: 1px;
}
h1{
    /*border: 1px solid black;*/
    margin: 0;
    padding: 20px 0;
    color: red;
    font-size: 60px;
    text-align: center;
    color: #00539f;
    text-shadow: 4px 4px 2px black;
}

html{
    font-size: 10px;
    font-family: "Opens Sans", sans-serif;
    background-color: #00539f;
}

img {
    display: block;
    width: 250px;
    margin: 0 auto;
}
body {
    width: 600px;
    margin: 0 auto;
    background-color: #ff9500;
    padding: 0px 20px 20px 20px;
    border: 5px solid black;
  }


  const myImage = document.querySelector("img");

myImage.onclick = () => {
  const mySrc = myImage.getAttribute("src");
  if (mySrc === "images/Firefox-nighty-logo.png") {
    myImage.setAttribute("src", "images/pngegg.png");
  } else {
    myImage.setAttribute("src", "images/Firefox-nighty-logo.png");
  }
};

let myButton = document.querySelector("button");
let myHeading = document.querySelector("h1");

function setUserName() {
  const myName = prompt("Please enter your name.");
  if (!myName) {
    setUserName();
  } else {
    localStorage.setItem("name", myName);
    myHeading.textContent = `Mozilla is cool, ${myName}`;
  }
}

//When page first load
if (!localStorage.getItem("name")) {
  setUserName();
} else {
  const storedName = localStorage.getItem("name");
  myHeading.textContent = `Mozilla is cool, ${storedName}`;
}
myButton.onclick = () => {
  setUserName();
};
