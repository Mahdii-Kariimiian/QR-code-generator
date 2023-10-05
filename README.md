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
-Vercel: https://qr-code-generator-omega-seven.vercel.app/

![QRcode generator](https://github.com/Mahdii-Kariimiian/QR-code-generator/assets/134393975/284229c1-30ea-43da-a6af-5e1eb3288e72)

![QRcode generated](https://github.com/Mahdii-Kariimiian/QR-code-generator/assets/134393975/6c33eac3-ec24-49b0-a604-388f0d6fba04)

![QRcode generator alert ](https://github.com/Mahdii-Kariimiian/QR-code-generator/assets/134393975/318275b7-27c9-4940-a865-72ab9bddf605)

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


