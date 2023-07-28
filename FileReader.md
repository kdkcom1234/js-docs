물론, FileReader의 readAsDataURL 메서드를 사용하여 이미지 프리뷰를 만드는 예시를 제공해드리겠습니다. 이 예시는 JavaScript로 작성되었습니다.

HTML 코드:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Image Preview Example</title>
  </head>
  <body>
    <input type="file" id="imageInput" accept="image/*" />
    <div>
      <h3>Image Preview:</h3>
      <img
        id="imagePreview"
        src="#"
        alt="Image Preview"
        style="max-width: 300px;"
      />
    </div>
    <script src="script.js"></script>
  </body>
</html>
```

JavaScript 코드 (script.js 파일):

```javascript
// 파일 선택 시 호출되는 함수
function handleImageSelect(event) {
  const file = event.target.files[0];

  // FileReader 객체 생성
  const reader = new FileReader();

  // FileReader 로드 완료 시 호출되는 이벤트 핸들러
  reader.onload = function (event) {
    const imagePreviewElement = document.getElementById("imagePreview");
    // 이미지 프리뷰 업데이트
    imagePreviewElement.src = event.target.result;
  };

  // 파일을 Data URL 형식으로 읽어오기
  reader.readAsDataURL(file);
}

// 파일 선택(input) 요소에 이벤트 리스너 추가
const imageInput = document.getElementById("imageInput");
imageInput.addEventListener("change", handleImageSelect);
```

위의 코드를 이용하여 HTML 파일과 script.js 파일을 생성하고 브라우저에서 HTML 파일을 열면 이미지를 선택하면 선택한 이미지가 프리뷰로 표시됩니다. 이 예시에서는 FileReader의 readAsDataURL 메서드를 사용하여 이미지 파일을 Data URL 형식으로 읽어오고, 이미지 태그의 src 속성을 이용하여 이미지를 표시하였습니다.
