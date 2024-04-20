## Date 함수가 뭐에요?
```
그냥 병신 함수
```
## Time함수는요?
```
더머
```
## DateTime
```
병신같은 함수를 보완한 함수
```

## 본래의도
```
Date는 날짜,

Time은 시간을 계산하는 함수였는데(단어의미만 봐도 그런잖아)

근데 막상 만든 새끼가 ㅈ같이 만들어서

괜히 사용자만 헷갈리게 하는 함수가 되었다.

지금은 DateTime으로 새로 보완하여 내놓은 함수가 있으니

DateTime 앞에 아래 키워드를 접두사처럼 붙이면 된다.

LocalDateTime

ZonedDateTime

OffsetDateTime

그러면 컴퓨터가 가공하지 않은 형식으로 결과를 출력함

별로 마음에 안든다.

DateTimeFormatter formatter = DateTimeFormatter.ofPattern("HH시 mm분 ss초");

이렇게 큰 따옴표안에 원하는 형식으로 바꾸고 리턴하면 됨

    String localClock() {
        LocalDateTime start = LocalDateTime.now();
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("HH시 mm분 ss초");
        return "서울 " + start.format(formatter);
    }

리턴값은 LocalDateTime이 아닌 스트링이다.(형식 변환안하면 원래 LocalDateTime임)

이유를 찾아보려고 했는데

now()
Returns:
the current date-time using the system clock and default time-zone, not null
대충 현재 내 컴퓨터 시간을 반환함

ofPattern()
Returns:
the formatter based on the pattern, not null
뭔 개소리지

format()
Returns:
the formatted date-time string, not null
여기 String으로 반환하고

이게 return 자리 옆에 있으니까

메서드에서도 String으로 타입선언을 해야하는 것 같다.
```

