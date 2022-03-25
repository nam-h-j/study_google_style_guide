# HTML,CSS
## Background
 - This document defines formatting and style rules for HTML and CSS.
 - 이 글은 HTML과 CSS의 포맷과 스타일 규칙을 정의한 문서이다.
 
 - It aims at improving collaboration, code quality, and enabling supporting infrastructure.
 - 이 문서는 협업과 코드품질, 그리고 서포팅 인프라 스트럭처를 가능하게 하기 위함이다.
 
 - It applies to raw, working files that use HTML and CSS, including GSS files. 
 - 이 문서는 로우파일, 워킹파일(GSS파일을 포함한 HTML과 CSS)에 적용된다.
 
 - Tools are free to obfuscate, minify, and compile as long as the general code quality is maintained.
 - 일반적인 코드 품질이 유지되는 한 툴로써 자유롭게 난독화, 최소화, 및 컴파일할 수 있다.

## General
 ### General Style Rules
 - Protocol, 프로토콜

  * Use HTTPS for embedded resources where possible.<br/>
  * 가능한 한 내장 리소스에 HTTPS로 표기한다.
   
  * Always use HTTPS (https:) for images and other media files, style sheets, and scripts, unless the respective files are not available over HTTPS.<br/>
  * HTTPS에서 각 파일을 사용할 수 없는 경우를 제외하고 항상 이미지 및 기타 미디어 파일, 스타일 시트 및 스크립트에 HTTPS를 사용한다.

```
<!-- Not recommended: omits the protocol -->
<script src="//ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>

<!-- Not recommended: uses HTTP -->
<script src="http://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>

<!-- Recommended -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
```
```
/* Not recommended: omits the protocol */
@import '//fonts.googleapis.com/css?family=Open+Sans';

/* Not recommended: uses HTTP */
@import 'http://fonts.googleapis.com/css?family=Open+Sans';

/* Recommended */
@import 'https://fonts.googleapis.com/css?family=Open+Sans';
```

 ### General Formatting Rules
 - Indetation, 들여쓰기
   - Indent by 2 spaces at a time.
   - 들여쓰기는 스페이스 2개를 사용한다.

  - Don’t use tabs or mix tabs and spaces for indentation.
  - 탭이나 탭과 스페이스를 섞여서 들여쓰기 하지 않는다.

```
<ul>
  <li>Fantastic</li>
  <li>Great</li>
</ul>
```
```
.example {
  color: blue;
}
```
- Capitalization, 대소문자 사용
 - Use only lowercase.
 - 소문자만 사용한다
 
 - All code has to be lowercase: This applies to HTML element names, attributes, attribute values (unless text/CDATA), CSS selectors, properties, and property values (with the exception of strings).
 - 모든 코드는 소문자로 작성한다
  - HTML엘리먼트 이름
  - 어트리뷰트
  - 어트리뷰트 값
  - CSS 선택자
  - 프로퍼티
  - 프로퍼티 값
  - 문자열은 예외
