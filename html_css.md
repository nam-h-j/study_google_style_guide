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

- **Protocol, 프로토콜**
  - 가능한 한 내장 리소스에 HTTPS로 표기한다.
    - Use HTTPS for embedded resources where possible.
  - HTTPS에서 각 파일을 사용할 수 없는 경우를 제외하고 항상 이미지 및 기타 미디어 파일, 스타일 시트 및 스크립트에 HTTPS를 사용한다.
    - Always use HTTPS (https:) for images and other media files, style sheets, and scripts, unless the respective files are not available over HTTPS.

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

---

### General Formatting Rules

####Indetation, 들여쓰기

- 들여쓰기는 스페이스 2개를 사용한다.
  - Indent by 2 spaces at a time.
- 탭을 사용하거나 탭과 스페이스를 섞어서 들여쓰기 하지 않는다.
  - Don’t use tabs or mix tabs and spaces for indentation.

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

  - 소문자만 사용한다
    - Use only lowercase.
  - 모든 코드는 소문자로 작성한다
  - HTML엘리먼트 이름
  - 어트리뷰트
  - 어트리뷰트 값
  - CSS 선택자
  - 프로퍼티
  - 프로퍼티 값
  - 문자열은 예외
    - All code has to be lowercase: This applies to HTML element names, attributes, attribute values (unless text/CDATA), CSS selectors, properties, and property values (with the exception of strings).

- Trailing Whitespace

  - Trailing white space를 삭제한다.
  - Trailing white space : 직전 라인과 가장 끝과 직후 라인 가장 앞 사이에 들여쓰기를 제외한 공백
    - Remove trailing white spaces.
  - Trailing white space는 불필요하고, 차이를 복잡하게 만든다.
  - Trailing white spaces are unnecessary and can complicate diffs.

  ***

  ### General Meta Rules

  - Encoding
    - UTF-8 (BOM없이)
      - Use UTF-8(no BOM).
    - \*BOM?
      - Byte Order Mark, '바이트 순서 표시'
      - 유니코드가, little-endian 인지 big-endian 인지 아니면 UTF-8 인지 쉽게 알 수 있도록, 유니코드 파일이 시작되는 첫부분에 보이지 않게, 2~3바이트의 문자열을 추가하는 것
      - 텍스트 에디터 화면에서는 보이지 않고, 헥사 에디터(Hex Editor)\*로 열었을 때만 보인다.
        > 엔디안에 따른 BOM 문자
        > little-endian 의 BOM : 0xFF 0xFE
        > big-endian 의 BOM : 0xFE 0xFF
        > UTF-8 의 BOM : 0xEF 0xBB 0xBF
    - 에디터에서도 BOM이 없는 UTF-8 캐릭터 셋인지 확인
      - Make sure your editor uses UTF-8 as character encoding, without a byte order mark.
    - HTML 템플릿과 문서에 \<meta charset="utf-8"\>을 사용해서 인코딩을 명시해야 한다. 스타일 시트는 UTF-8로 가정하고 있으므로 인코딩을 명시하지 않는다.
      - Specify the encoding in HTML templates and documents via \<meta charset="utf-8"\>. Do not specify the encoding of style sheets as these assume UTF-8.
    - (인코딩 명시에 대한 자세한 내용은 HTML 과 CSS의 캐릭터 인코딩 핸들링에서 확인 할 수 있다)
      - (More on encodings and when and how to specify them can be found in Handling character encodings in HTML and CSS.)
