# Android Smali Code

안드로이드 apk파일을 apktool로 리패키징 하게 되면<br>
Smali코드라는 어셈블리어와 비스무리한 코드로 나타나게 된다.<br>
Smali 자체로 이해할 수는 있지만, 코드에 익숙치 않아 난해하다.<br>
그래서 JEB툴을 이용해서 코드를 JAVA코드 형태로 바꾸어 해독을 시작한다.<br>

분석 도충 apk를 내 입맛대로 바꿀 수 있을까? 하는 생각이 들었고<br>
Smali코드를 수정하여 apk파일을 재패키징 하게 되면 원하는대로 apk를 수정할 수 있엇다.<br>

이를 앱 리버싱에 적용하고자 android device를 모니터링 할 수 있는 툴을 찾아보니<br>
Android Studio에서 기본적으로 제공하고 있었다. ( 내가 만든 앱만 볼 수 있을 줄... )

![Logcat Monitor](/Image/AndroidStudio_Logcat.PNG)

분석중인 앱은 비공개...