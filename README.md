# password-generator

HTML:==

<!DOCTYPE html>
<html>

<head>
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css  sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP" integrity="sha384-JcKb8q3iqJ61gNV9KGb8thSsNjpSL0n8PARn9HuZOnIxN0hoP+VmmDGMN5t9UJ0Z" crossorigin="anonymous">
    <script src="https://code.jquery.com/jquery-3.5.1.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js" integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js" integrity="sha384-B4gt1jrGC7Jh4AgTPSdUtOBvfO8shuf57BaghqFfPlYxofvL8/KUEfYiJOMMV+rV" crossorigin="anonymous"></script>

</head>


<body>

    <div class="pw-container">
        <div class="pw-header">

            <div class="pw">

                <span id="pw"> Password Here</span>

                <button id="copy">Copy</button>
            </div>

        </div>

        <div class="pw-body">

            <div class="form-control">

                <lable for="length">Password Length</lable>

                <input id="len" value="10" type="number" min="8" max="30">

            </div>

            <div class="form-control">

                Letters</lable>

                <lable for="upper">Contain Uppercase Letters</lable>
                <input id="upper" type="checkbox">

            </div>

            <div class="form-control">

                <lable for="lower">Contain Lowercase

                    Letters</lable>

                <input id="lower" type="checkbox">

            </div>

            <div class="form-control">

                <lable for="number">Contain Numbers </lable>

            </div>

            <div class="form-control">

                <lable for="symbol">Contain Symbol</lable>

                <input id="symbol" type="checkbox">

                <input id="number" type="checkbox">

            </div>

            <button class="generate" id="generate">Generate

                Paaword</button>

        </div>
    </div>


</body>


</html>

CSS:==

@import url('https://fonts.googleapis.com/css2?family=Bree+Serif&family=Caveat:wght@400;700&family=Lobster&family=Monoton&family=Open+Sans:ital,wght@0,400;0,700;1,400;1,700&family=Playfair+Display+SC:ital,wght@0,400;0,700;1,700&family=Playfair+Display:ital,wght@0,400;0,700;1,700&family=Roboto:ital,wght@0,400;0,700;1,400;1,700&family=Source+Sans+Pro:ital,wght@0,400;0,700;1,700&family=Work+Sans:ital,wght@0,400;0,700;1,700&display=swap');

@import url('https://fonts.googleapis.com/css?? family=Poppins:wght@200;480; 600&display=swap');

* {

    box-sizing: border-box;
}

body {

    margin: 0;

    font-family: "Poppins, sans-serif; 

        background-color: rebeccapurple;

    display: flex;
    min-height: 100vh;
}

color: yellow;

align-items: center;
justify-content: center;
}

pw-container {

    width: 400px;
    background-color: rgb(69, 17, 118);
    box-shadow: @ 4px 10px rgba(0, 0, 0, 0.6);

}

pw-header {
    padding: 1em;
}

+pw {

    width: 100%;

    height: 70px;

    align-items: center;

    background-color: rebeccapurple;
    display: flex;
    position: relative;
    font-size: 1.5rem;
    padding: 1rem;
    /* overflow: auto; */



}

-pw button {

    position: absolute;

    top: 0;

    right: 0;

    transform: translate(0, 50%);

    transition: opacity 0.25 ease, transform 0.25 ease;

    opacity: 0;

    background-color: rgb(35, 5, 66);

    padding: 0.25rem Irem;

    font-family: inherit;

    font-weight: bold;

    color: #fff;

    border: none;

    cursor: pointer;

}

.pw:hover button {

    opacity: 1;

    transform: translate(0, -80%);
}

.pw-body {

    padding: 81rem 1rem;
}

.form-control {

    color: #eee;
    display: flex;

    justify-content: space-between;
    margin: 0.75rem 0;

}

.generate {

    display: block;

    background-color: #ecb602;

    color: rebeccapurple;

    padding: 1rem;

    font-size: 1.5rem;

    font-weight: bold;
    margin-top: 1rem;
    width: 100%;
    border: none;
    cursor: pointer;

    width: 100%;
}

js:==


 const Pwel = document.getElementById("pw");
 const copyEl = document.getElementById("copy");

 const lenEl = document.getElementById("len");
 const upperE1 = document.getElementById("upper");

 const lowerEl = document.getElementById("lower");

 const symbolEI = document.getElementById("symbol");

 const generateE =

     document.getElementById("generate");

 const numberEl = document.getElementById("number");

 const upperletters = "ABCDEFGHIJKLMNOPQSRTUVWXYZ";

 const lowerLetters = "abcdefghijk lmnopqrstuvwxyz";

 const numbers = "0123456789";

 const symbol = "~1@#$%^&()_+=|";

 function getLowercase() {
     return lowerLetters[Math.floor(Math.random() *
         lowerLetters.length)];
 }

 function getUppercase() {
     return upperLetters[Math.floor(Math.random() *
         upperLetters.length)];

 }

 function getNumber() {
     return numbers[Math.floor(Math.random() *

         numbers.length)];
 }

 function getsymbol() {
     return symbol[Math.Floor(Math.random() *

         symbol.length)];
 }

 function generatePassword() {

     const len = lenEl.value;
     let password = "";

     for (let i = 0; 1 < len; i++) {

         const x = generatex();

         password += x;

     }
     PwEl.innerText = password;

 }

 function generatex() {

     const xs = [];

     if (uppertl.checked) {
         xs.push(getuppercase());

     }

     if (lowerEl.checked)(
         xs.push(getLowercase());
     }
     if (numbert1.checked) {
         xs.push(getNumber());

     }
