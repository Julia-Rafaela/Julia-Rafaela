## Olá! Eu sou a Júlia Rafaela


### 📊 Estatísticas

<p>
  <img 
    align="left" 
    alt="GitHub Stats" 
    height="200" 
    style="padding-right: 10px;" 
    src="https://github-readme-stats.vercel.app/api?username=Larissakich&show_icons=true&theme=tokyonight&include_all_commits=true&locale=pt-br" 
  />

<img 
      align="left" 
      alt="GitHub Stats" 
      height="200" 
      src="https://github-readme-stats.vercel.app/api/top-langs/?username=larissakich&theme=tokyonight&layout=compact&custom_title=Tecnologias&langs_count=9" 
  />

</p>

### 🤖 Linguagens 

<img 
    align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;" 
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg" 
/>
<img 
    align="left" 
    alt="CSS" 
    title="CSS"
    width="30px" 
    style="padding-right: 10px;" 
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg" 
/>
<img 
    align="left" 
    alt="Javat" 
    title="Java"
    width="30px" 
    style="padding-right: 10px;" 
    src="https://blog.geekhunter.com.br/wp-content/uploads/2020/07/pngwing.com_.png" 
/>
<img 
    align="left" 
    alt="SQL"
    title="SQL" 
    width="30px" 
    style="padding-right: 10px;" 
    src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSvXkY-p0TK4Yoe7bYv-T7PffxOvi2iQOnDa4ejeD9eGW8zCzi500UOUr-nPm7xOk4jXZM&usqp=CAU" 
/>
<div align="center">
    <h3>🐍 Joguinho da Cobrinha</h3>
    <canvas id="gameCanvas" width="300" height="300"></canvas>
    <script>
        const canvas = document.getElementById("gameCanvas");
        const ctx = canvas.getContext("2d");

        let snake = [{ x: 150, y: 150 }];
        let food = { x: 100, y: 100 };
        let dx = 10, dy = 0;

        function drawRect(color, x, y) {
            ctx.fillStyle = color;
            ctx.fillRect(x, y, 10, 10);
        }

        function move() {
            let head = { x: snake[0].x + dx, y: snake[0].y + dy };
            snake.unshift(head);
            if (head.x === food.x && head.y === food.y) {
                food = { x: Math.floor(Math.random() * 30) * 10, y: Math.floor(Math.random() * 30) * 10 };
            } else {
                snake.pop();
            }
        }

        function checkCollision() {
            if (snake[0].x < 0 || snake[0].x >= canvas.width || snake[0].y < 0 || snake[0].y >= canvas.height) {
                return true;
            }
            for (let i = 1; i < snake.length; i++) {
                if (snake[i].x === snake[0].x && snake[i].y === snake[0].y) {
                    return true;
                }
            }
            return false;
        }

        function update() {
            if (checkCollision()) {
                alert("Game Over! Recarregue a página para jogar novamente.");
                document.location.reload();
            }
            move();
        }

        function draw() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            snake.forEach(part => drawRect("green", part.x, part.y));
            drawRect("red", food.x, food.y);
        }

        function gameLoop() {
            update();
            draw();
            setTimeout(gameLoop, 100);
        }

        document.addEventListener("keydown", event => {
            if (event.key === "ArrowUp" && dy === 0) { dx = 0; dy = -10; }
            else if (event.key === "ArrowDown" && dy === 0) { dx = 0; dy = 10; }
            else if (event.key === "ArrowLeft" && dx === 0) { dx = -10; dy = 0; }
            else if (event.key === "ArrowRight" && dx === 0) { dx = 10; dy = 0; }
        });

        gameLoop();
    </script>
</div>

