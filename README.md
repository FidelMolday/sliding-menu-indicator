moldays @js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Animated Sliding Menu indicator </title>
</head>
<body>
    <header>
        <a href="#" class="logo">Logo</a>
        <nav>
            <div id="indicator"></div>
            <a href="#" >Home</a>
            <a href="#">About</a>
            <a href="#">Portfolio</a>
            <a href="#">Team</a>
            <a href="#">Contact</a>
        </nav>
    </header>
    <style>
        *{
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'poppins',sans-serif;
        }
        :root{
            --clr: #2c363f ;
        }
        body {
            background: var(--clr);
        }
        header {
            position: fixed;
            width: 100%;
            top: 0;
            background: #2196f3;
            padding: 10px 50px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            z-index: 100000;
        }
        header .logo{
            position: relative;
            color: #fff;
            font-size: 2em;
            font-weight: 600;
            text-decoration: none;
        }
        header nav{
            display: flex;
            gap: 10px;
        }
        header nav a {
            position: relative;
            text-decoration: none;
            padding: 12px 20px;
            color: #fff;
            letter-spacing: 0.1em;
            font-weight: 400;
        }
        header nav #indicator{
            position: absolute;
            width: 88px ;
            height: 58px;
            background: var(--clr);
            border-top-left-radius: 20px;
            border-top-right-radius: 20px;
            transition: 0.5s;
        }
        header nav #indicator::before{
            content: '';
            position: absolute;
            left: -30px;
            bottom: 0;
            width: 30px;
            height: 30px;
            background: transparent;
            border-bottom-right-radius: 20px;
            box-shadow: 5px 5px 0 5px var(--clr);
        }
        header nav #indicator::after{
            content: '';
            position: absolute;
            bottom: 0;
            right: -30px;
            width: 30px;
            height: 30px;
            background: transparent;
            border-bottom-left-radius: 20px;
            box-shadow: -5px 5px 0 5px var(--clr);
        }
    </style>
    <script>
        let indicator = document.querySelector('#indicator');
        let items = document.querySelectorAll('nav a');
        function marker(e) {
            indicator.style.left = e.offsetLeft+"px"; 
            indicator.style.width = e.offsetWidth+"px"; 
        }
        items.forEach(link => {
            link.addEventListener('click', (e) => {
              marker(e.target);
            })
        })
    </script>
</body>
</html>
