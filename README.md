QR code Generator 

## Table of contents

- [Overview](#overview)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I used](#what-i-learned)
- [Author](#author)

## Overview
This App use goqr.me API to create QR code for imported links.

### Screenshot

### Links
-Netlify: 



### Built with

- Semantic HTML5 markup
- CSS custom properties
- JavaScript
- API

### What I used

Here is a glimpse of what I used to build this mini project.
````
JavaScript


const button = document.querySelector("form button");
const qrCodeBox = document.querySelector(".qr-code");
const qrInput = document.querySelector ("form input");
const qrImage = document.querySelector (".qr-code img");
const alert = document.createElement("p")

// Enter keypress
window.addEventListener("keypress" ,(e)=>{
    if (e.key === "Enter") {
        e.preventDefault()
        QRGenerate ()
    }
})
// button event
button.addEventListener('click', QRGenerate)

// Remove previous QR code when input is empty
qrInput.addEventListener ("keyup" , ()=> {
    if (!qrInput.value) {
        qrCodeBox.classList.add("hidden")
    }
 })

 function QRGenerate () {
    let input = qrInput.value;
    if (!input) {
        alert.innerText = "Please insert a link"
        alert.style.color = "red"
        alert.style.position = "absolute"
        alert.style.bottom = "12px"
        alert.style.right = "calc(50% - 68px)"
        button.insertAdjacentElement("afterend" , alert)
     } else {
        alert.remove()
        button.innerHTML = "Generating"
    qrImage.setAttribute("src", `https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=${input}`)
    qrImage.addEventListener ("load" , () =>{
        qrCodeBox.classList.remove("hidden")
        button.innerHTML = "Generate"
        })
     }
    
 }

````
## Author
Mahdi Karimian
- linkedin (www.linkedin.com/in/mahdi-karimian-116643273)
- Frontend Mentor – @Mahdii-Kariimiian (https://www.frontendmentor.io/profile/Mahdii-Kariimiian)


