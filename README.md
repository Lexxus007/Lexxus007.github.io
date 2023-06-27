﻿<!DOCTYPE html>

<html>
<head>
    <title></title>
    <script>
        if (window.Worker) {
            console.log("step 1");
            let worker = new Worker("worker.js");
            console.log("step 2");
            worker.postMessage("hello");
            console.log("step 3");
            worker.addEventListener("message", function (e) {
                document.querySelector("div").innerHTML = e.data;
            }, false);
            console.log("step 4");
        } else {
            document.querySelector("div").innerHTML = "Fault";
        }
    </script>
</head>
<body>
    <div>
        Temp
    </div>
</body>
</html>
