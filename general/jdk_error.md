# JDK Error

이번에 jd-gui라는 클래스파일을 JAVA언어로 보여주는 툴을 사용하기위해 명령어를 실행했는데 에러를 뿜어내며 실행되지 않는 현상이 발생하였다.

>WARNING: An illegal reflective access operation has occurred
WARNING: Illegal reflective access by org.codehaus.groovy.reflection.CachedClass$3$1 (file:/home/zihad/Downloads/jd-gui.jar) to method java.lang.Object.finalize()<br>
WARNING: Please consider reporting this to the maintainers of org.codehaus.groovy.reflection.CachedClass$3$1<br>
WARNING: Use --illegal-access=warn to enable warnings of further illegal reflective access operations<br>
WARNING: All illegal access operations will be denied in a future release<br>
Gtk-Message: 18:32:55.443: Failed to load module "canberra-gtk-module"<br>
Exception in thread "main" java.lang.reflect.InaccessibleObjectException:<br> Unable to make jdk.internal.loader.ClassLoaders$AppClassLoader<br>(jdk.internal.loader.ClassLoaders$PlatformClassLoader,jdk.internal.loader.URLClassPath) accessible: module java.base does not "opens jdk.internal.loader" to unnamed module @6e6c3152
	at java.base/java.lang.reflect.AccessibleObject.checkCanSetAccessible(AccessibleObject.java:337)
	at java.base/java.lang.reflect.AccessibleObject.checkCanSetAccessible(AccessibleObject.java:281)
	at java.base/java.lang.reflect.Constructor.checkCanSetAccessible(Constructor.java:192) ...

이러한 저주스러운 에러를 나타내기에 검색을 해 보니<br>
역시나 우려한대로 jdk버전의 문제엿다.<br>
아파치때도 고생했던 문제인데 jdk 10버전을 사용하겠다고 용을 썼었던 기억이있다.<br>
그러나 이번에는 방법이 아예 없는 것 같아 ( 검색해 보니 9버전도 마찬가지도 안된다더라 ) 바로 8버전을 설치하고 환경변수만 바꾸고 실행을 시켰다.

그러나... 똑같은 에러가 뜬 것이다. 혹시나 싶어 환경변수도 다시 설정하고 다시확인하고 다시확인하고 다시확인했으나 여전히 되지않음... 결국 jdk 10버전을 삭제하기에 이르는데 삭제하고나니

>Error: could not find java.dll<br>
Error: Could not find Java SE Runtime Environment.

... 덕분에 powershell도 켜서 
> get-command java.exe

를 실행시키니

Version 부분에 10버전으로 인식되고 있었다. 이를 해결하기위해선 C:/ProgramData/Oracle/Java 디렉토리를 삭제하면 된다고한다. 삭제하고나니 버전을 제대로 8버전으로 인식했다.

