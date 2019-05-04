# Android Apktool

Apktool은 

[USB Debugging](https://github.com/guswkpro/TIL/blob/master/Android/apk_debuggable.md)

에 설명하였는데, 사용 도중에 에러가 발생해서 그에 대한 내용을 업로드 하고자 한다.
<br><br><br>
apktool을 잘 사용하다가 아래와 같은 에러를 마주했는데

![APKTOOL_1](/Image/apktool_1.png)

리버싱한 앱을 다시 재패키징 할 때 이러한 에러가 발생했다. 이유인 즉슨, 해당 경로에 쓸 수 없다고 하며 다른 경로를 대신 사용하는데 이것때문에 다른 에러를 동시다발적으로 일으켜 기능을 제대로 수행하지 못하는 상황을 마주했다.

조금 찾아보니 메뉴얼에 명시 되어 있어 금방 해결할 수 있었다.(언제나 도구를 쓰기 전에 메뉴얼부터 읽어보자...)

![APKTOOL_2](/Image/apktool_2.png)

위 그림과 같은 경로에 framework 디렉토리를 생성하게 되면, 쉽게 문제 문제 해결이 가능했다.