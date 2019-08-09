# 🎫 HTML HyperLink

---
- HyperLink는 웹을 만드는 중요한 요소이다.
- 문서를 우리가 원하는 다른 문서에 연결할 수 있다.
- 문서의 특정 부분에 대한 정보를 제공하고 간단한 웹 주소로 앱을 사용할 수 있도록 한다.
- 클릭하면 웹 브라우저가 다른 웹 주소(URL)로 이동한다.
---
> 참고 :
URL은 HTML 파일, Text 파일, 이미지, 문서, 비디오 및 오디오 등 항목을 가리킬 수 있다. 웹 브라우저가 파일을 표시하거나 처리하는 방법을 모르는 경우 파일을 열지 묻는 메시지가 표시된다.

## What is HyperLink ?
- 기본 링크는 요소 내부의 링크로 바꾸려는 text를 감싸고 `<a>`을 포함할 `href`속성을 제송하여 생성된다.

```html
<p>I'm creating a link to
    <a href="https://www.mozilla.org/en-US/">the Mozilla homepage</a>.
</p>
```

##### code run
<p>I'm creating a link to
<a href="https://www.mozilla.org/en-US/">the Mozilla homepage</a>.
</p>

### Title Attribute
- 링크에 추가할 수 있는 속성은 `title`이 있는데 이 속성은 페이지에 포함 된 정보의 종류 또는 알아야 할 사항과 같은 링크에 대한 정보가 포함되어 있다.

```html
<p>I'm creating a link to
<a href="https://www.mozilla.org/en-US/"
   title="The best place to find more information about Mozilla's
          mission and how to contribute">the Mozilla homepage</a>.
</p>
```

##### code run
<p>I'm creating a link to
<a href="https://www.mozilla.org/en-US/"
   title="The best place to find more information about Mozilla's
          mission and how to contribute">the Mozilla homepage</a>.
</p>

- 마우스 커서를 올리면 제목이 tooltip으로 나타난다.
