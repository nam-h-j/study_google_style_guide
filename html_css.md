# HTML,CSS

[1.Background](#1-background)
[2.General](#2-general)

- [2.1 General Style Rules](#21-general-style-rules)
  - [2.1.1 Protocol, 프로토콜](#211-protocol-프로토콜)
- [2.2 General Formatting Rules](#22-general-formatting-rules)
  - [2.2.1 Indetation, 들여쓰기](#221-indetation-들여쓰기)
  - [2.2.2 Capitalization, 대소문자 사용](#222-capitalization-대소문자-사용)
  - [2.2.3 Trailing Whitespace](#223-trailing-whitespace)
- [2.3 General Meta Rules](#23-general-meta-rules)
  - [2.3.1 Encoding, 인코딩](#231-encoding-인코딩)
  - [2.3.2 Comments, 주석](#232-comments-주석)
  - [2.3.3 Action Items, 작업항목](#233-action-items-작업항목)

[3.HTML](#3-HTML)

- [3.1 HTML Style Rules](#31-html-style-rules)
  - [3.1.1 Document Type, 문서유형](#311-document-type-문서유형)
  - [3.1.2 HTML Validity, HTML 유효성](#312-html-validity-html-유효성)

## 1. Background

- This document defines formatting and style rules for HTML and CSS.
- 이 글은 HTML과 CSS의 포맷과 스타일 규칙을 정의한 문서이다.

- It aims at improving collaboration, code quality, and enabling supporting infrastructure.
- 이 문서는 협업과 코드품질, 그리고 서포팅 인프라 스트럭처를 가능하게 하기 위함이다.

- It applies to raw, working files that use HTML and CSS, including GSS files.
- 이 문서는 로우파일, 워킹파일(GSS파일을 포함한 HTML과 CSS)에 적용된다.

- Tools are free to obfuscate, minify, and compile as long as the general code quality is maintained.
- 일반적인 코드 품질이 유지되는 한 툴로써 자유롭게 난독화, 최소화, 및 컴파일할 수 있다.

---

## 2. General

### 2.1 General Style Rules

#### 2.1.1 Protocol, 프로토콜

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

### 2.2 General Formatting Rules

#### 2.2.1 Indetation, 들여쓰기

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

---

#### 2.2.2 Capitalization, 대소문자 사용

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

---

#### 2.2.3 Trailing Whitespace

- Trailing white space를 삭제한다.
  - Remove trailing white spaces.
- Trailing white space\*
  > 직전 라인과 가장 끝과 직후 라인 가장 앞 사이에 들여쓰기를 제외한 공백
- Trailing white space는 불필요하고, 차이를 복잡하게 만든다.
  - Trailing white spaces are unnecessary and can complicate diffs.

---

### 2.3 General Meta Rules

#### 2.3.1 Encoding, 인코딩

- UTF-8 (BOM없이)
  - Use UTF-8(no BOM).
- BOM\*?
  - Byte Order Mark, '바이트 순서 표시'
  - 유니코드가, little-endian 인지 big-endian 인지 아니면 UTF-8 인지 쉽게 알 수 있도록, 유니코드 파일이 시작되는 첫부분에 보이지 않게, 2~3바이트의 문자열을 추가하는 것
  - 텍스트 에디터 화면에서는 보이지 않고, 헥사 에디터(Hex Editor)\*로 열었을 때만 보인다.
    - 엔디안에 따른 BOM 문자
      - little-endian 의 BOM : 0xFF 0xFE
      - big-endian 의 BOM : 0xFE 0xFF
      - UTF-8 의 BOM : 0xEF 0xBB 0xBF
- 에디터에서도 BOM이 없는 UTF-8 캐릭터 셋인지 확인
  - Make sure your editor uses UTF-8 as character encoding, without a byte order mark.
- HTML 템플릿과 문서에 \<meta charset="utf-8"\>을 사용해서 인코딩을 명시해야 한다. 스타일 시트는 UTF-8로 가정하고 있으므로 인코딩을 명시하지 않는다.
  - Specify the encoding in HTML templates and documents via \<meta charset="utf-8"\>. Do not specify the encoding of style sheets as these assume UTF-8.
- (인코딩 명시에 대한 자세한 내용은 HTML 과 CSS의 캐릭터 인코딩 핸들링에서 확인 할 수 있다)
  - (More on encodings and when and how to specify them can be found in Handling character encodings in HTML and CSS.)

---

#### 2.3.2 Comments, 주석

- 가능한 경우 필요에 따라 코드를 설명 한다.
  - Explain code as needed, where possible.
- 주석을 사용한 코드 설명: (쓸수 있는 내용의 예)

  - 무엇을 보조 하는지?
  - 어떤 목적으로 쓰이는지?
  - 각 솔루션이 사용된 이유, 선호되는 이유?
  - Use comments to explain code:
    What does it cover, what purpose does it serve, why is respective solution used or preferred?

- ...???
- (This item is optional as it is not deemed a realistic expectation to always demand fully documented code. Mileage may vary heavily for HTML and CSS code and depends on the project’s complexity.)

---

#### 2.3.3 Action Items, 작업항목

- 작업 항목을 TODO를 사용해서 표기 한다
  - Mark todos and action items with TODO.
- todo는 항상 TODO키워드로만 강조 표시 한다, @@ 같은 포맷은 사용하지 않는다
  - Highlight todos by using the keyword TODO only, not other common formats like @@.
- 아래 형식과 같이 괄호 안에 연락처(사용자 이름 또는 메일링 리스트)를 추가합니다. TODO(contact)
  - Append a contact (username or mailing list) in parentheses as with the format TODO(contact).
- 작업 항목은 콜론 뒤에 추가 합니다. TODO : action item.
  - Append action items after a colon as in TODO: action item.

```
{# TODO(john.doe): revisit centering #}
<center>Test</center>
```

```
<!-- TODO: remove optional tags -->
<ul>
  <li>Apples</li>
  <li>Oranges</li>
</ul>
```

---

## 3. HTML

### 3.1 HTML Style Rules

#### 3.1.1 Document Type, 문서유형

- HTML5 사용
  - Use HTML5.
- HTML5는 모든 HTML문서에 사용해야 한다.
  (HTML문서(text/html)사용을 권장합니다. XHTML(application/xhtml+xml)은 사용하지 마십시오, 브라우저와 인프라지원이 부족하고 HTML보다 최적화가 어렵습니다.)
  - HTML5 (HTML syntax) is preferred for all HTML documents: <!DOCTYPE html>.
    (It’s recommended to use HTML, as text/html. Do not use XHTML. XHTML, as application/xhtml+xml, lacks both browser and infrastructure support and offers less room for optimization than HTML.)
- HTML에서 문제가 없지만, void 요소를 닫지 마십시오, <br>(O) <br />(X)

---

#### 3.1.2 HTML Validity, HTML 유효성

- 가능한 유효한 HTML을 사용한다.
  - Use valid HTML where possible.
- 파일 크기와 관련한 성능을 목적으로 인해 불가능한 경우가 아니면 유효한 HTML 코드를 사용한다.
  - Use valid HTML code unless that is not possible due to otherwise unattainable performance goals regarding file size.
- W3C HTML 유효성 검사기와 같은 도구를 사용하여 테스트 한다(https://validator.w3.org/nu/)
  - Use tools such as the W3C HTML validator to test.
- 유효한 HTML의 사용은 측정 가능한 기준 품질 속성으로 기술 요구 사항 및 제약 조건에 대한 학습에 기여하고 적절한 HTML 사용을 보장한다.
  - Using valid HTML is a measurable baseline quality attribute that contributes to learning about technical requirements and constraints, and that ensures proper HTML usage.
