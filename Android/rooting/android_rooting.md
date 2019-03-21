# Android Rooting

루트 권한이 허용되지 않는 기기나 OS에서 루트 권한을 획득 하는 것.<br>

리눅스에서는 root계정에 로그인 하게되면 얻을 수 있지만, 루트권한을 획득하는 것을 제한한 경우<br>
보안 허점을 통하여 코드를 실행해 획득해야 한다.<br>
앞으로 이 과정을 실제로 내부적으로 어떻게 돌아가는지 공부할계획이다.


### 추가 : <br>
갤럭시 루팅을 하기 위해선 Odin이라는 삼성에서 제공하는 다운로드 툴이 필요하다.<br>
이 Odin을 사용하다 보면 생소한 단어를 마주치게 되는데.<br>

![Odin](/Image/Odin.PNG)
BL AP CP CSC 라는 축약어가 나와있다. 이들의 의미는 다음과 같다.
```
CSC (Consumer Software Customization): It is specific to geographical region and carriers. It contains the software packages specific to that region, carrier branding and APN setting.
PIT (Partition Information Table): You only need it if you screw up your partition table or if the firmware specifically requires it because of a change in the partition table layout.
BL (Bootloader): As its name implies, this option is used to flash the Bootloader of the device.
AP (Application Processor or PDA): Android.
CP (Core Processor): We call it Modem.
```
[출처] : https://android.stackexchange.com/questions/176515/what-do-the-terms-bl-ap-cp-and-csc-mean-in-odin

더 자세한 내용은 아래에 정리되어 있다.
```
https://huriman.tistory.com/99
```

# 매일 추가하는 내용<br>
1. TWRP는 FRP Lock이 걸려있는 상태에서는 설치 할 수 없다. ( 190320 )

2. Galaxy S7 Android 8.0 버전을 루팅하는 과정중에 삽질이 있었다.<br>
보통 루팅을 진행할 때, 기존의 펌웨어를 밀어버리고 리커버리를 설치한 후 루팅을 진행하는데, <br>
리커버리까지만 설치했을 때, 시스템 부팅을 하게 되면 무한재부팅 현상이 발생했다.<br>
그래서 리커버리모드에서 usb를 연결하여 supersu.zip을 넣고 설치를 진행하니, 루팅도되고 부팅도 되었다. ( 190321 )