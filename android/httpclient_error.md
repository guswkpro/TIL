# HttpClient

HttpClient는 API 23부터 지원을 하지 않는다.
따라서 API를 낮추던지 다른 방법을 쓰던지 해야하는데

```javascript
android {
    useLibrary 'org.apache.http.legacy'
}
```

를 추가해주면 사용할 수 있다.