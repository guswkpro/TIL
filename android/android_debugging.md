# 디버깅

디버깅은 코드상 원하는 지점에 중단점을 찍고 메모리에 저장된 값을 살펴보며 에러를 확인하거나, 코드를 단계적으로 실행하는 동작들을 의미하는데 역공학에서 이를 활용하여 동적분석을 진행하게 된다.

1월 15일자에 등록한 TIL galaxy_bootloader.md ( https://github.com/guswkpro/TIL/blob/master/android/galaxy_bootloader.md )를 보면 부트로더를 언락하는 이유가 현재 사용하는 툴에서 해당 기기의 process를 추적하여 원하는 앱을 디버깅하기 위해서였다. 해당 문서에서 말하였듯이 갤럭시 기종은 패스트부트 등 기본적인 기능들을 제거하였기 때문에 이를 하기위해 상당히 애를 먹었다. 결론부터 이야기하자면
```
1. 루팅
2. boot.img 추출
3. boot.img unpack
4. default.prop 파일 수정
5. repack
6. 새롭게 만든 boot.img 업로드
```

이 과정을 거치면 된다. 다른 과정은 검색하면 충분히 찾을 수 있으니 업로드하지않고 설정파일을 어떻게 수정하면되는지만 업로드 한다.

![Edit setting](/img/default.prop.PNG)