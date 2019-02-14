# Android Rooting

루트 권한이 허용되지 않는 기기나 OS에서 루트 권한을 획득 하는 것.<br>

리눅스에서는 root계정에 로그인 하게되면 얻을 수 있지만, 루트권한을 획득하는 것을 제한한 경우<br>
보안 허점을 통하여 코드를 실행해 획득해야 한다.<br>
앞으로 이 과정을 실제로 내부적으로 어떻게 돌아가는지 공부할계획이다.


### 추가 : <br>
갤럭시 루팅을 하기 위해선 Odin이라는 삼성에서 제공하는 다운로드 툴이 필요하다.<br>
이 Odin을 사용하다 보면 생소한 단어를 마주치게 되는데.<br>

![Odin](/img/Odin.PNG)
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