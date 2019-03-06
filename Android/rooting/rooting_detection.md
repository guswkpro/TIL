# 루팅 탐지 기법

루팅은 안드로이드 폰을 좀 써본다 하는 사람들에게는 필수적인 요소이다.<br>
핸드폰의 최고 관리자 권한을 얻어, 매크로, 녹화 등 조금 더 자유로이 내 핸드폰을 쓸 수 있도록 만들어 준다.<br>
따라서 이를 탐지하는 기법들도 같이 나오는데, 흔히 많이 사용되는 탐지기법들을 간단히 목록화 하였다.

## 탐지 기법
```
“super”가 포함된 앱 탐색
“chain”이 포함된 패키지명 탐색
Busybox 탐색
Su 명령어 실행 여부
/system/build.prop옵션 확인
Su 바이너리 탐지
삼성 KNOX 루팅 카운트
폴더 쓰기권한 확인
프로세스 확인
```

두가지 예시만 보여주자면<br>
ps명령을 통해 eu.chainfire.supersu 프로세스가 작동중인 것을 확인이 가능하고<br>
삼성 KNOX 보안 솔루션에서는 루팅을 아래 사진과 같이 카운팅 하기도 한다.<br>

![1](/Image/rooting_detection_1.PNG)

![2](/Image/rooting_detection_2.PNG)
>KNOX WARRANTY VIOD : 1