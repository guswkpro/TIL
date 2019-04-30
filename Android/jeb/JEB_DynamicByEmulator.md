# JEB 에뮬레이터 동적 분석

오랜만에 글을 남긴다.<br>
바쁘다는 핑계로 문서를 쓰지 않았고, 덕분에 내 잔디밭은 완전 탈모가 왔다.<br>
공부를 하며 기록할만한 내용이 나왔고, 이에 한 모 심어주고자 글을 쓴다.<br>

그동안 JEB툴로 동적분석을 해오며, 나는 실제 기기에 설치를 하고 실제 기기에서 동작시켜보며<br>
분석을 진행해왔다. 그동안은 별 문제가 없었다.<br>
( 물론, 나의 부주의로 인하여 연결이 끊어지거나 하는 아주 '사소한' 문제들이 있었다. )<br>
큰 문제는 다른 과제와 병행하기 시작하며 발생했다. 한두개의 기기로 두가지의 과제를 하려다보니<br>
불편한점이 다수 발생했다. 따라서 PC에 있는 앱 플레이어를 통하여 동적분석을 하기위한 사전 준비내용을 쓰고자 한다.<br>

우선 사전 준비 없이 JEB에서 디버깅을 실행하면 아래와 같은 현상이 나타난다.

![EmulatorSetting.PNG](/Image/JEB_Emulator_1.PNG)

방법은 아주 간단하다. 아래의 한줄만 추가하면 된다.
```xml
<Forwarding name="MY_PORT" proto="1" hostip="127.0.0.1" hostport="5565" guestip="10.0.2.15" guestport="5555"/>
```
hostport는 5555-5585 사이 중 한개이면 된다.<br>

위 코드를<br>
```
Droid4X는 /vms/droid4x/droid4x.vbox
MEMU는    /Memu/memuHyperv VMs/Memu/Memu.memu
```

다른 프로그램은 어디인지 잘 모르겠다.<br>
위 두개의 파일 안에 있는 <NAT>안에 코드를 넣어주면 된다.

![EmulatorSetting.PNG](/Image/JEB_Emulator_Setting.PNG)

이렇게 하면 에뮬레이터에서도 동적분석을 진행할 수 있게 된다.

![EmulatorSetting.PNG](/Image/JEB_Emulator_2.PNG)