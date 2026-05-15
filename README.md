<!DOCTYPE html>
<html lang="ky">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Түнкү деңиз</title>

<style>
    *{
        margin:0;
        padding:0;
        box-sizing:border-box;
    }

    body{
        overflow:hidden;
        background:#1b346b;
    }

    .sky{
        position:absolute;
        width:100%;
        height:100%;
        background:linear-gradient(to bottom,#0a306a,#001d3d,#003566);
    }

    .moon{
        position:absolute;
        top:70px;
        right:120px;
        width:90px;
        height:90px;
        border-radius:50%;
        background:#fff7c2;
        box-shadow:0 0 40px #fff7c2;
    }

    .star{
        position:absolute;
        background:white;
        border-radius:50%;
        animation:moveStars linear infinite;
    }

    @keyframes moveStars{
        from{
            transform:translateX(0px);
            opacity:0.5;
        }

        50%{
            opacity:1;
        }

        to{
            transform:translateX(100vw);
            opacity:0.3;
        }
    }

    .sea{
        position:absolute;
        bottom:0;
        width:100%;
        height:35%;
        background:#001219;
        overflow:hidden;
    }

    .wave{
        position:absolute;
        width:200%;
        height:100%;
        background:rgba(0,119,182,0.4);
        border-radius:40%;
        animation:waveMove 8s linear infinite;
    }

    .wave:nth-child(2){
        top:20px;
        opacity:0.5;
        animation-duration:12s;
    }

    @keyframes waveMove{
        from{
            transform:translateX(0);
        }

        to{
            transform:translateX(-50%);
        }
    }

</style>
</head>
<body>

<div class="sky"></div>

<div class="moon"></div>

<div class="sea">
    <div class="wave"></div>
    <div class="wave"></div>
</div>

<script>

for(let i=0;i<150;i++){

    let star=document.createElement("div");

    star.classList.add("star");

    let size=Math.random()*3;

    star.style.width=size+"px";
    star.style.height=size+"px";

    star.style.top=Math.random()*window.innerHeight*0.7+"px";
    star.style.left=Math.random()*window.innerWidth+"px";

    star.style.animationDuration=
        (Math.random()*20+10)+"s";

    document.body.appendChild(star);
}

</script>

</body>
</html>
