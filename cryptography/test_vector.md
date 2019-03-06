# Test Vector

Test Vector는 어떤 시스템을 테스트 하기위해 제공되는 입력들이다.

암호학에서는 어떠한 암호 알고리즘을 구현한 후 표준 문서에 나와있는 Test Vector들을 사용하여 테스트를 진행한다.

이때 사용하는 문서들은 다양하게 존재하는데
                 
기본적으로는 RFC문서를 참고한다.

RFC문서는 국제 표준으로써 
https://www.ietf.org/standards/rfcs/ 에서 확인할 수 있다.

구글에서 RFC + 필요한 알고리즘의 이름을 검색함으로써 검색이 가능하다.

혹은 RFC 번호를 알고 있다면 그것을 통해서도 검색 할 수 있다.

또한 국내 알고리즘들에 대해서는 KISA와 NIS에서 확인이 가능하며

미국 국제 표준 기술연구소인 NIST에서도 다양하게 확인이 가능했으나 지금은

![no money](/Image/Nomoney.PNG)

출처 : https://csrc.nist.gov/projects/cryptographic-algorithm-validation-program/block-ciphers

Due to the lapse in government funding, csrc.nist.gov and all associated online activities will be unavailable until further notice. Learn more.

즉 돈이 없어서 더이상 제공하지 않는다고한다(?)

이후 알고리즘을 구현하게 된다면 꼭 테스트 벡터를 돌려보도록 하자! ( 즉, 표준대로 코딩하지 않으면 값이 틀릴 수 있으니, 꼭 참고하도록 하자 )

----
