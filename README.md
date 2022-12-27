# temperature-converter
you can check the fahrenheit and celsius of given temperature..
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <link rel="stylesheet" href="./l2task3/public/intern.css">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <script src="https://kit.fontawesome.com/a59b9b09ab.js" crossorigin="anonymous"></script>

    <title>Temprature</title>
    <style>
        /* @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@200;300;400;600&display=swap'); */
        
        * {
            margin: 0px;
            padding: 0;
            box-sizing: border-box;
            font-family: inter;
        }
        
        body {
            display: flex;
            align-items: center;
            justify-content: center;
            padding-top: 20vh;
        }
        
        .container {
            width: 350px;
            border: 2px solid black;
            background-color: #f350d759;;
            border-radius: 10px;
            padding: 20px 10px;
            box-shadow: 0px 0px 10px rgba(50, 49, 49, .6);
            height: auto;
        }
        
        .hed {
            font-size: 20px;
            text-align: center;
            margin-bottom: 10px;
            font-weight: bold;
        }
        
        .boxcontainer {
            display: flex;
        }
        
        p {
            font-size: 1rem;
            color: rgb(126, 125, 125);
            padding: 5px 2px;
        }
        
        .box1 {
            width: 50%;
            padding: 10px 5px;
            /* border: 1px solid red; */
        }
        
        .takval,
        #unit {
            width: 100%;
            font-size: 22px;
            border: none;
            background-color: transparent;
            outline: none;
            border-bottom: 1px solid rgb(126, 125, 125);
        }
        
        #unit {
            font-size: 1.1rem;
            margin-top: 4.5px;
        }
        
        .valuecontainer {
            margin: 10px 0;
            margin-top: 20px;
        }
        
        .value {
            width: 100%;
            height: 30px;
            margin: 8px 0;
            font-size: 1.4rem;
            border-bottom: 1px solid rgb(126, 125, 125);
        }
        
        .button {
            width: 100%;
            height: auto;
            font: 1.6rem;
            color: white;
            background-color: rgb(69, 112, 241);
            border-radius: 10px;
            padding: 10px;
            border: none;
            cursor: pointer;
            margin: 20px 0 0 0;
        }
        
        .emoji {
            width: 100%;
            text-align: center;
            padding: 10px 0;
        }
        
        .emoji>i {
            color: rgb(253, 174, 37);
            font-size: 3rem;
        }
    </style>

</head>

<body>
    <div class="container">
        <div class="hed">Temperature convrter</div>
        <div class="emoji">
            <i id="icon" class="fa-solid fa-face-grin"></i>
            <p id="par"></p>

        </div>
        <div class="boxcontainer">
            <div class="box1">
                <p>Degree</p>
                <input type="number" class="takval" />
            </div>
            <div class="box1">
                <p>Type</p>
                <select name="" id="unit">   
                     <option value="Fahrenheit">Fahrenheit</option>
                     <option value="Celsius">Celsious</option>  
                </select>
            </div>
        </div>
        <div class="valuecontainer">
            <p>Result</p>
            <div class="value"></div>
        </div>
        <button onclick="temprature()" class="button">Converte</button>
    </div>
</body>
<script>
    var emoji = document.querySelector("#icon");
    var par = document.querySelector("#par");
    let temprature = () => {
        let opt = document.querySelector("#unit");
        let display = document.querySelector(".value");
        var a = document.querySelector(".takval").value;
        if (opt.value == "Celsius") {
            console.log(a, "C to F", opt.value)
            let F = a * (9 / 5) + 32
            display.innerHTML = F.toFixed(4) + " F"
            if (F < 32) {
                emoji.style = "color:blue"
                emoji.className = "fa-solid fa-face-grimace"
                par.innerHTML = "Cool at frezing point"
            } else if (F > 122) {
                emoji.style = "color:red"
                emoji.className = "fa-solid fa-face-dizzy"
                par.innerHTML = "So Warm"
            } else {
                emoji.className = "fa-solid fa-face-grin"
                par.innerHTML = ""
                emoji.style = "color:rgb(253, 174, 37)"
            }

        } else {
            console.log(a, "F to C", opt.value)
            let C = (a - 32) * (5 / 9)
            display.innerHTML = C.toFixed(4) + " ºC"
            if (C < 0) {
                emoji.style = "color:blue"
                emoji.className = "fa-solid fa-face-grimace"
                par.innerHTML = "Cool at frezing point"
            } else if (C > 50) {
                emoji.style = "color:red"
                emoji.className = "fa-solid fa-face-dizzy"
                par.innerHTML = "So Warm"
            } else {
                emoji.className = "fa-solid fa-face-grin"
                par.innerHTML = ""
                emoji.style = "color:rgb(253, 174, 37)"
            }
        }
    }
</script>

</html>
