# Web-page-create-in-different-colour
<!DOCTYPE html><html lang="en">
<head>
<meta charset="UTF-8">
<title>Multi Color Box Blink</title><style>
body {
    margin: 0;
    height: 100vh;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 1fr);
}

/* Boxes */
.box {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 24px;
    color: white;
    font-weight: bold;
    cursor: pointer;
}

/* Initial colors */
.box1 { background: red; }
.box2 { background: blue; }
.box3 { background: green; }
.box4 { background: orange; }
.box5 { background: purple; }
.box6 { background: teal; }

/* Multi-color blinking */
@keyframes multiBlink {
    0%   { background-color: red; }
    20%  { background-color: blue; }
    40%  { background-color: green; }
    60%  { background-color: orange; }
    80%  { background-color: purple; }
    100% { background-color: teal; }
}

.blink {
    animation: multiBlink 1s infinite;
}
</style></head>
<body><div class="box box1">1</div>
<div class="box box2">2</div>
<div class="box box3">3</div>
<div class="box box4">4</div>
<div class="box box5">5</div>
<div class="box box6">6</div><script>
const boxes = document.querySelectorAll(".box");

boxes.forEach(box => {

    const start = () => {
        box.classList.add("blink");
    };

    const stop = () => {
        box.classList.remove("blink");
    };

    // Works for both mobile + PC
    box.addEventListener("pointerenter", start);
    box.addEventListener("pointerleave", stop);
});
</script></body>
</html>
