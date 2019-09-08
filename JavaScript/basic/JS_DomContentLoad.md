# 🎡 DomContentLoad

## 🔵 페이지 라이프 사이클
1. DomContentLoad - HTML이 모두 load되고 DOM 트리가 완성되었지만 외부(img등)가 아직 로드되어지지 않았을때
2. load - 브라우저에 모든 리소스(img,style,script 등)가 로드 되었을때
3. beforeunload / unload - 페이지를 떠날때

=> DomContentLoad가 load보다 빨리 발생한다는 것을 알 수 있다.

## 🔵 장점
1. DomContentLoad : DOM이 준비 상태이기 때문에 DOM 노드를 제어 할 수 있다.
2. load : 모든 리소스가 로드된 시점에 image 사이즈와 같은 것들을 얻을 수 있다.
3. beforeunload / unload : 변화에 따른 저장 여부 및 페이지 이탈 여부를 확인 할 수 있다.

## ⚪ example
~~~
<html>
    <head>
        <script>
            window.addEventListener('load', function(){
                console.log('load');
            })
            window.addEventListener('DOMContentLoaded', function(){
                console.log('DOMContentLoaded');
            })
        </script>
    </head>
    <body>
        <p id="target">Hello</p>
    </body>
</html>
~~~

## 🔶 정리
- load는 모든 리소스를 로드해야하기 때문에 DomContentLoad가 먼저 발생된 후 발생한다.
- 대부분 모든 리소스를 기다릴 필요가 없는 경우가 많기에 단순히 빠른 실행을 위함입니다.
- HTML문서를 파싱하는 과정에서 script태그를 만나면 DOM구축 작업이 중단됩니다. 중단된 후 , script 작업이 실행된 후에 다시 작업이 실행됩니다.
