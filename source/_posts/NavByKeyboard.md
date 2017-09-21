---
title: NavByKeyboard
date: 2017-09-21 14:44:41
tags:
---
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport"
          content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Nan'HOME</title>
    <style type="text/css">
        html{
            color: #000;
        }
        .link_container {
            margin: 32px;
        }

        p {
            color: black;
            margin: 8px;
            padding: 4px;
        }

        .focused {
            border: 2px solid blue;
        }
    </style>
</head>
<body bgcolor="#F6F6EF">
<center>
    <h2 style="color:black">Nan's Home</h2>
</center>

<div class="link_container" id="link_container">
    <p class="focusable">dev-hisntv2-TEST</p>
    <p class="focusable">dev-hisntv2-DEV</p>
    <p class="focusable">keyboard_jq</p>
    <p class="focusable">keyboard_vue</p>
    <p class="focusable">dev-sellMaster</p>
    <p class="focusable">sell-prod</p>
    <p class="focusable">music-prod</p>
    <p class="focusable">sellDemo</p>
    <p class="focusable">DevicePixelRatio</p>
    <p class="focusable">Time-test</p>
    <p class="focusable">es5Test</p>
</div>

<br/><br/><br/>
<center>
    <p id="out"></p>
</center>
</body>
<script src="./hisntv/base/js/lib/jquery-1.7.2.min.js"></script>
<script>
    var links = new Array(
            "http://192.168.88.87:8080/",  // dev sr:node ev:xiaomi-FRF
            "http://192.168.20.203:8080/",  // dev sr:node ev:italkbb-TV2
            "http://192.168.10.220/TestProject/keyboard_jq/index.html",  // dev sr:node ev:italkbb-TV2
            "http://192.168.10.220/TestProject/keyboard_vue/index.html",  // dev sr:node ev:italkbb-TV2
            "http://192.168.20.83:8888/",  // dev sr:node
            "http://192.168.20.83/sell/dist/index.html",  // sell-prod sr:nginx
            "http://192.168.20.83/vue-music/dist/index.html", // music-prod sr:nginx
            "http://192.168.20.83/sell-master/dist/index.html", // sellDemo-prod sr:nginx
            "http://192.168.10.220/TestProject/devicePixelRatio/index.html",   // devicePixelRatio
            "http://192.168.10.220/TestProject/time/index.html" ,   // time
            "http://192.168.10.220/TestProject/es5Test/index.html"    // es5Test
            )
            ;

    var currentIndex = 0;
    var linkItems = $(".focusable");
    $(linkItems[currentIndex]).addClass("focused");

    var out = document.getElementById("out");

    $(document).keydown(function (e) {
        switch (e.keyCode) {
            case 37:
            case 38:
                if (currentIndex > 0) {
                    $(linkItems[currentIndex]).removeClass("focused");
                    currentIndex--;
                    $(linkItems[currentIndex]).addClass("focused");
                }
                break;
            case 39:
            case 40:
                if (currentIndex < linkItems.length - 1) {
                    $(linkItems[currentIndex]).removeClass("focused");
                    currentIndex++;
                    $(linkItems[currentIndex]).addClass("focused");
                }
                break;
            case 13:
                location.href = links[currentIndex];
                break;
            case 403: // RED key.
                localStorage.clear();
                out.innerHTML = "Local storage cleared.";
                break;
            default:
                break;
        }
    });
    $('#link_container').on('mouseover','p',function (e) {
        $(e.target).addClass("focused").siblings().removeClass("focused");
        console.log($(e.target).index())
    }).on('click touch','p',function (e) {
        location.href = links[$(e.target).index()];
    })
</script>

</html>
```
