<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Valentine's Day Surprise</title>
    <style>
        /* 基础样式 */
        body {
            margin: 0;
            height: 100vh;
            background: linear-gradient(45deg, #ff6b6b, #ff8e8e);
            font-family: 'Arial', sans-serif;
            overflow: hidden;
        }

        /* 心跳动画 */
        @keyframes heartbeat {
            0% { transform: scale(1); }
            15% { transform: scale(1.3); }
            30% { transform: scale(1); }
            45% { transform: scale(1.15); }
            60% { transform: scale(1); }
        }

        /* 主容器 */
        .container {
            position: relative;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
        }

        /* 动态爱心效果 */
        .heart {
            position: absolute;
            color: #fff;
            font-size: 24px;
            animation: float 3s ease-in forwards;
        }

        /* 照片墙 */
        .photo-wall {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            margin: 20px;
        }

        .photo {
            width: 100px;
            height: 100px;
            border-radius: 10px;
            object-fit: cover;
            transition: transform 0.3s;
        }

        .photo:hover {
            transform: scale(1.1);
        }
    </style>
</head>
<body>
    <div class="container">
        <h1 style="color: white; text-shadow: 2px 2px 4px rgba(0,0,0,0.3);">
            💖 情人节快乐！！亲爱的汪汪! 💖
        </h1>
        
        <!-- 照片墙 -->
        <div class="photo-wall">
            <img src="1.jpg" class="photo" alt="Memory 1">
            <img src="2.jpg" class="photo" alt="Memory 2">
            <img src="3.jpg" class="photo" alt="Memory 3">
        </div>

        <!-- 互动按钮 -->
        <button id="surpriseBtn" style="
            padding: 15px 30px;
            background: #fff;
            border: none;
            border-radius: 25px;
            font-size: 18px;
            cursor: pointer;
            margin: 20px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.1);
        ">
            点击查看惊喜 💝
        </button>

        <!-- 情话语录 -->
        <div id="messageBox" style="
            display: none;
            background: rgba(255,255,255,0.9);
            padding: 20px;
            border-radius: 15px;
            max-width: 80%;
            text-align: center;
            margin: 20px;
        ">
            <p id="loveMessage"></p>
        </div>
    </div>

    <script>
        // 情话库
        const loveMessages = [
            "亲爱的小汪汪~",
            "再次祝你情人节快乐哟~",
            "你的云云超级超级爱你~",
            "云云会一直一直永远陪着可爱的汪汪宝哟~",
            "希望我的汪汪宝天天开心事事顺心~"
        ];

        // 爱心生成器
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = Math.random() * 3 + 2 + 's';
            document.body.appendChild(heart);
            
            setTimeout(() => heart.remove(), 5000);
        }

        // 初始化
        document.getElementById('surpriseBtn').addEventListener('click', () => {
            // 显示情话
            document.getElementById('messageBox').style.display = 'block';
            document.getElementById('loveMessage').textContent = 
                loveMessages[Math.floor(Math.random() * loveMessages.length)];
            
            // 创建爱心特效
            setInterval(createHeart, 300);
            setTimeout(() => clearInterval(heartInterval), 2000);
            
            // 添加心跳动画
            document.body.style.animation = 'heartbeat 1.2s ease infinite';
        });

        // 触摸互动
        document.addEventListener('touchstart', (e) => {
            if (e.touches.length > 0) {
                createHeartAtPosition(e.touches[0].clientX, e.touches[0].clientY);
            }
        });

        function createHeartAtPosition(x, y) {
            const heart = document.createElement('div');
            heart.style.position = 'absolute';
            heart.style.left = x + 'px';
            heart.style.top = y + 'px';
            heart.style.fontSize = '24px';
            heart.innerHTML = '❤️';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 1000);
        }
    </script>
</body>
</html>

# ww.github.io
