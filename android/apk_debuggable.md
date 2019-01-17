# App is not debuggable

JEB 툴로 동적분석을 하겠다고 까불다가 내 눈에 들어온 한 문장이다.<br>
어제 저녁부터 오늘 지금이순간까지 왜 디버깅이 내 생각대로 안되는 이유이기도 하다.<br>
보통 앱은 배포하면서 역공학을 막고자 디버깅을 막은채로 출시된다고 한다. 그런데 그걸 무시하고 디버깅을 하려했으니 마음대로 안될수밖에....<br>

일단 디버깅을 허용하기 위해서는 최종적으로 Androidmanifest.xml파일에 application에 degguable="true"를 넣어주면 된다. 이제 방법들을 설명하기전에 두가지 툴이 필요한데 apk파일을 리버싱하는 apktool과 signapk라는 툴이 필요하다. ( 혹시나 이 글을 읽는 사람이 필요하다면 주도록 하겠다. )<br>

이제 본격적으로 방법을 설명한다면

1. apk파일을 리버싱 한다.
```
java -jar apktoo.jar d app.apk
```
2. Androidmanifest.xml에서 application에 다음의 코드를 추가한다.
```
android:debuggable="true"
```
3. 다시 재패키징 한다.
```
java -jar apktoo.jar b app(폴더이름)
```
4. 디바이스에 업로드하기위해 사인한다.
```
java -jar signapk.jar testkey.x509.pem testkey.pk8 app.apk signedapp.apk
```

이 과정을 거치면 디버깅 실행시 디버깅 가능한 apk라는 문장을 볼 수 있다!!1