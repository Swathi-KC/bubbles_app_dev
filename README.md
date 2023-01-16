# bubblesappdev
<!DOCTYPE html>
<html>

<head>
</head>

<body>
    <h1 style="text-align:center; font-size:48px; font-family:Roboto;"> Bubbles App</h1>
    <canvas id="myCanvas" width="1000" height="900" style="border:1px solid black; line-width:3;"></canvas>
    <div style="text-align:right;">
        <button id="resetButton" style="border:2px solid black; font-size:18px; font-family:Roboto; height:30px; width:70px;  box-shadow:5px 5px 2px black; margin:40px;">Reset</button>
    </div>
    <script>
        let canvas = document.getElementById("myCanvas");
        let ctx = canvas.getContext("2d");

        let ctx1 = canvas.getContext("2d");
        ctx1.fillStyle = "yellow";
        ctx1.beginPath();
        ctx1.arc(150, 100, 50, 0, 2 * Math.PI);
        ctx1.fill();
        ctx1.stroke();

        let ctx2 = canvas.getContext("2d");
        ctx2.fillStyle = "blue";
        ctx2.beginPath();
        ctx2.arc(150, 300, 50, 0, 2 * Math.PI);
        ctx2.fill();
        ctx2.stroke();

        let ctx3 = canvas.getContext("2d");
        ctx3.fillStyle = "red";
        ctx3.beginPath();
        ctx3.arc(150, 500, 50, 0, 2 * Math.PI);
        ctx3.fill();
        ctx3.stroke();

        let ctx4 = canvas.getContext("2d");
        ctx4.fillStyle = "green";
        ctx4.beginPath();
        ctx4.arc(150, 700, 50, 0, 2 * Math.PI);
        ctx4.fill();
        ctx4.stroke();

        ctx.beginPath();
        canvas_arrow(ctx, 800, 100, 700, 100);
        canvas_arrow(ctx, 800, 300, 700, 300);
        canvas_arrow(ctx, 800, 500, 700, 500);
        canvas_arrow(ctx, 800, 700, 700, 700);
        ctx.lineWidth = "7"
        ctx.stroke();

        function canvas_arrow(context, fromx, fromy, tox, toy) {
            var headlength = 10;
            var dx = tox - fromx;
            var dy = toy - fromy;
            var angle = Math.atan2(dy, dx);
            context.moveTo(fromx, fromy);
            context.lineTo(tox, toy);
            context.lineTo(tox - headlength * Math.cos(angle - Math.PI / 6), toy - headlength * Math.sin(angle - Math.PI / 6));
            context.moveTo(tox, toy);
            context.lineTo(tox - headlength * Math.cos(angle + Math.PI / 6), toy - headlength * Math.sin(angle + Math.PI / 6));
        };


        canvas.addEventListener("click", function(event) {
            let x = event.offsetX;
            let y = event.offsetY;
            console.log(x);
            console.log(y);
            if (x <= 200 && (y >= 100 && y <= 150)) {
                let ctx1 = canvas.getContext("2d");
                ctx1.fillStyle = "#d3d3d3";
                ctx1.beginPath();
                ctx1.arc(150, 100, 50, 0, 2 * Math.PI);
                ctx1.lineWidth = "1"
                ctx1.fill();
                ctx1.stroke();

                ctx.beginPath();
                canvas_arrow(ctx, 200, 100, 300, 100);
                ctx.lineWidth = "7"
                ctx.stroke();
            }

            if (x <= 200 && (y >= 300 && y <= 350)) {
                let ctx2 = canvas.getContext("2d");
                ctx2.fillStyle = "#d3d3d3";
                ctx2.beginPath();
                ctx2.arc(150, 300, 50, 0, 2 * Math.PI);
                ctx2.lineWidth = "1"
                ctx2.fill();
                ctx1.stroke();

                ctx.beginPath();
                canvas_arrow(ctx, 200, 300, 300, 300);
                ctx.lineWidth = "7"
                ctx.stroke();
            }

            if (x <= 200 && (y >= 500 && y <= 550)) {
                let ctx3 = canvas.getContext("2d");
                ctx3.fillStyle = "#d3d3d3";
                ctx3.beginPath();
                ctx3.arc(150, 500, 50, 0, 2 * Math.PI);
                ctx3.lineWidth = "1"
                ctx3.fill();
                ctx3.stroke();

                ctx.beginPath();
                canvas_arrow(ctx, 200, 500, 300, 500);
                ctx.lineWidth = "7"
                ctx.stroke();
            }

            if (x <= 200 && (y >= 700 && y <= 750)) {
                let ctx4 = canvas.getContext("2d");
                ctx4.fillStyle = "#d3d3d3";
                ctx4.beginPath();
                ctx4.arc(150, 700, 50, 0, 2 * Math.PI);
                ctx4.lineWidth = "1"
                ctx4.fill();
                ctx4.stroke();

                ctx.beginPath();
                canvas_arrow(ctx, 200, 700, 300, 700);
                ctx.lineWidth = "7"
                ctx.stroke();
            }

        });

        let resetBtnEl = document.getElementById("resetButton");
        resetBtnEl.addEventListener("click", function(event) {

            let ctx1 = canvas.getContext("2d");
            ctx1.fillStyle = "yellow";
            ctx1.beginPath();
            ctx1.arc(150, 100, 50, 0, 2 * Math.PI);
            ctx.lineWidth = "1"
            ctx1.fill();
            ctx1.stroke();


            ctx.beginPath();
            canvas_arrow(ctx, 800, 100, 700, 100);
            ctx.lineWidth = "7"
            ctx.stroke();


            let ctx2 = canvas.getContext("2d");
            ctx2.fillStyle = "blue";
            ctx2.beginPath();
            ctx2.arc(150, 300, 50, 0, 2 * Math.PI);
            ctx.lineWidth = "1"
            ctx2.fill();
            ctx2.stroke();

            ctx.beginPath();
            canvas_arrow(ctx, 800, 300, 700, 300);
            ctx.lineWidth = "7"
            ctx.stroke();

            let ctx3 = canvas.getContext("2d");
            ctx3.fillStyle = "red";
            ctx3.beginPath();
            ctx3.arc(150, 500, 50, 0, 2 * Math.PI);
            ctx.lineWidth = "1"
            ctx3.fill();
            ctx3.stroke();

            ctx.beginPath();
            canvas_arrow(ctx, 800, 500, 700, 500);
            ctx.lineWidth = "7"
            ctx.stroke();

            let ctx4 = canvas.getContext("2d");
            ctx4.fillStyle = "green";
            ctx4.beginPath();
            ctx4.arc(150, 700, 50, 0, 2 * Math.PI);
            ctx.lineWidth = "1"
            ctx4.fill();
            ctx4.stroke();

            ctx.beginPath();
            canvas_arrow(ctx, 800, 700, 700, 700);
            ctx.lineWidth = "7"
            ctx.stroke();
        });
    </script>
</body>

</html>
