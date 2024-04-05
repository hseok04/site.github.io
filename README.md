<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Project 1</title>
<style>
    #rectangle {
        width: 50px;
        height: 50px;
        background-color: blue;
        position: absolute;
    }
     #redSquare {
        width: 40px;
        height: 40px;
        background-color: red;
        position: absolute;
        display: none;
    } 
</style>
</head>
<body>
    <!-- 배경 -->
    <div style="background-color:lightgoldenrodyellow">
    <!-- 인게임-->
    <h1>방향키와 f.s 키</h1> <br />

<div id="rectangle"></div>

<script>
    const rectangle = document.getElementById('rectangle');
    let x = 0;
    let y = 0;
    let speed = 5;
    let dx = 0;
    let dy = 0;

    function moveRectangle() {
        x += dx;
        y += dy;
        rectangle.style.left = x + 'px';
        rectangle.style.top = y + 'px';
        requestAnimationFrame(moveRectangle);
    }

    window.addEventListener('keydown', function(event) {
        switch(event.key) {
            case 'ArrowUp':
                dy = -speed;
                dx = 0;
                lastDirection = 'up';
                break;
            case 'ArrowDown':
                dy = speed;
                dx = 0;
                lastDirection = 'down';
                break;
            case 'ArrowLeft':
                dx = -speed;
                dy = 0;
                lastDirection = 'left';
                break;
            case 'ArrowRight':
                dx = speed;
                dy = 0;
                lastDirection = 'right';
                break;
            default:
                break;
            case 'f':
            case 'F':
                // F 키를 누르면 이전 이동 방향으로 30만큼 이동합니다.
                switch(lastDirection) {
                    case 'up':
                        y -= 100;
                        break;
                    case 'down':
                        y += 100;
                        break;
                    case 'left':
                        x -= 100;
                        break;
                    case 'right':
                        x += 100;
                        break;
                }
                break;    
        }
    });

    window.addEventListener('keyup', function(event) {
        if (event.key === 's') {
            dx = 0;
            dy = 0;
        }
    });

    moveRectangle();

</script>
<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/><br/></div>
</body>
</html>
