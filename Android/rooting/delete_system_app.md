# Delete System App

안드로이드 루팅을 진행한 후에 기본 시스템 앱을 삭제하려 했는데<br>
삭제되지 않고 아래와 같은 에러를 뿜어내는 경우가 있었다.
```
rm: SecGallery2015.apk: Read-only file system
```

왜인지 삭제가 안되고, 검색을 좀 해보니 remount를 하라는 방법들이 많이 나왔지만<br>
다들 정삭적으로 되지 않았고, 다른 방법으로 삭제했다.

```
pm list packages -f | grep gallery
```
위 명령어를 실행할 경우 설치된 패키지를 찾을 수 있다.<br>
나의 경우에는 갤러리 앱을 삭제하고자 하였다.<br>
![1](/Image/delete_system_app_1.PNG)

```
pm uninstall -k --user 0 com.sec.android.gallery3d
```

위 명령어를 실행시키면, 아래와 같이 "Success"라는 메시지와 함께 앱이 삭제됨을 볼 수 있다.

![2](/Image/delete_system_app_2.PNG)