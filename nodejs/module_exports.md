# module

필자는 평소에 node 코딩을 하면서 모듈을 만들때 exports만을 사용해서 생성하였다.<br>
최근 지인의 코드를 도와주다 module.exports.~~라는 코드를 발견하고 순간 '어..? 내가 잘못 쓰고 있었나?'라는 생각에 검색을 해보았다.

기본적으로 모듈을 만들기 위해서는 exports 객체의 속성이나 메소드를 정의해주면 되는것이 맞다.
> // cicle.js<br>
var PI = Math.PI;<br>
 <br>
exports.area = function (r) {<br>
    return PI * r * r;<br>
};<br>
 <br>
exports.circumference = function (r) {<br>
    return 2 * PI * r;<br>
};<br>

>// foo.js<br>
var circle = require('./circle.js');<br>
console.log( 'The area of a circle of radius 4 is '
    + circle.area(4));

위와 같은 코드의 경우 각각의 메소드를 exports객체의 메소드로 정의하여 foo.js에서 불러다 사용하게 된다. 여기까지는 내가 쓰는 방식과 동일하였다. 그렇다면 module.exports.~~~를 쓰는경우는 언제인가?

exports는 속성이나 메소드를 여러 개 정의할 수 있지만, module.exports는 하나만 정의할 수 있다.

>// square.js<br>
module.exports = function(width) {<br>
    return {<br>
        area: function() {<br>
                return width * width;<br>
           }<br>
    };<br>
}<br>

> // bar.js<br>
var square = require('./square.js');<br>
var mySquare = square(2);<br>
console.log('The area of my square is ' + mySquare.area());<br>

위에 보이는 코드처럼 require로 불러온변수가 바로 함수로 사용된다.

내 코드에서 한번도 사용해본적이 없다고 생각했으나 사용한 곳이 한곳 있었다.

>module.exports = client;

이런식으로 db를 연동할때 사용하고 있었다.

출처 : https://opentutorials.org/module/938/7190