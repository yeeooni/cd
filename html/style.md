### style

- 개요

  - HTML에서 STYLE 속성을 이용하면 CSS의 속성을 태그에 직접 설정할 수 있다.

  - JavaScript에서도 비슷하게 QuerySelector로 가져온 노드에서 style 속성을 참조하며 CSS 속성을 적용시킬 수 있다.

  - CSS에서 여러 단어로 이어진 속성은 -로 구분되었는데 JavaScript 에서는 -를 사용하지 않고 다음 단어를 카멜 케이스로 접근한다.

    ```javascript
    var box = document.getElementById("box");
    box.style.backGroundColor = "red"; //box의 배경색은 레드이다.
    ```

    

    ```html
    <!DOCTYPE HTML>
    <head>
    <script type="text/javacript">
        function changeColor(){
           var box = document.getElementById("box");
           var red = parseInt(Math.random() * 256);
           var green = parseInt(Math.random() * 256);
           var blue = parseInt(Math.random() * 256);
           box.style.backGroundColor = "rgb(" + red + "," + green + "," + blue + ")";
        }
    </script>    
    <style>
    #box{
         cursor : pointer;
         width : 80px;
         height : 80px;
         background-color : #ccc;
    }
    </style>
    	</head>
    	<body>
        	<div>
                click to change color 
            </div>    
            <div id="box" onclick="changeColor();">
            </div>
    	</body>
    </html>
    ```

    

    