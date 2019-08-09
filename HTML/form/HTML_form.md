# ⌨ HTML Form

## Input Form
- 웹 페이지에서는 form element를 사용하여 사용자로부터 입력을 받을 수 있다. 또한, 사용자가 입력한 데이터를 서버로 보낼 때에도 form 요소를 사용한다.

#### grammer
```html
<form action="처리할페이지주소" method="get|post"></form>
```
- `action` : 입력받은 데이터를 처리할 서버상의 URL 주소를 명시한다. 전달 받은 데이터를 처리하는 서버 프로그램을 Form-handler라고 한다.
- `method` : 입력받은 데이터를 서버에 전달할 방식을 명시한다. 따라서 사용자가 form 요소를 통해 입력한 데이터를 action 속성에 명시된 url 위치로 method 속성의 방식을 통해 전달된다.
- `GET` : 주소에 data를 추가하여 전달하는 방식이다. 데이터가 주소 입력창에 그래도 나타나며, 전송할 수 있는 데이터 크기도 제한적이다. 따라서, 검색 엔진의 query와 같이 크기가 작고 중요도가 낮은 정보를 보낼 때 주로 사용한다.
- `POST` : data를 별도로 첨부하여 전달하는 방식이다. 데이터가 외부에 드러나지 않으며, 전솔할 수 있는 데이터의 크기 또한 제한이 없다. 따라서, 보안성 및 활용성이 `GET`보다 좋다.