#Camera

안드로이드에서 Camera앱을 개발할 때, 사진을 저장하였는데 갤러리에 나타나지 않는 현상이 있었다.
이는 미디어 스캐닝이 일어나지 않은 상황이기 때문에 갤러리가 새로 나타난 이미지를 인식하지 못한 것인데

```java
Context context = getApplicationContext();
context.sendBroadcast(new Intent(Intent.ACTION_MEDIA_SCANNER_SCAN_FILE, Uri.fromFile(pictureFile)));
```

아래의 코드를 추가하게 되면 미디어스캐닝을 하게 된다. 이 코드를 적용시킨후 사진을 저장하면 갤러리에 이미지가 바로 나타나는 것을 볼 수 있다.