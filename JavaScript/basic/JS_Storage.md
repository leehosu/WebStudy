# JS_Storage

## Web Storage란
- 클라이언트의 디스크에 소량의 데이터를 저장해두기 위한 저장공간
    ### 특징
    - key-value형태의 데이터를 저장하기 윈한 Storage
    - JavaScript에서 객체를 다루듯이 사용법이 간단.
        (저장 : Storage 속성에 값을 지정 / 읽기 : Storage 속성에 접근)
    - 비교적 간단한 형태의 데이터 저장에 알맞음 ( 복잡하면 DB )

## Web Storage VS Cookie
### - Web Storage
- 기본 크기는 5Mbyte
- 서버로 데이터 보내지 않음
- 만료기간 없음
- JS 객체를 저장 할 수 있음
### Cookie
- 기본 크기 4Mbyte
- 요청헤더에 포함
- 만료기간 지정
- 문자열만 저장

## local Storage
~~~
setItem() : local storage 추가
getItem() : local storage 불러오기
removeItem() : local storage 삭제
clear() : 전체 삭제
~~~
