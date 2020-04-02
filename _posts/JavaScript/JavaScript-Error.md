## JavaScript Error

JavaScript 에러 모음

### TypeError : Cannot read property 'OOO' of null

_addEventListener_, _length_

> 원인 : HMTL이 로드되기전에 JavaScript에서 HTML을 참조하여 에러

> 해결방법1 : HTML이 전부 로드된 후 script를 읽히도록 body 태그 아래 배치  
> 해결방법2 : script 태그에 defer 추가

    
    <script src="test.js" defer/>
    

> 해결방법3 : function을 onload 함수 내부에 추가

    
    window.onload = function(){...}
    
