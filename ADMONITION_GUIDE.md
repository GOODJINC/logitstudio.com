# Admonition 커스터마이징 가이드

Hugo Blowfish 테마의 Admonition을 커스터마이징하는 방법을 설명합니다.

## 📋 목차

1. [기본 사용법](#기본-사용법)
2. [아이콘 숨기기](#아이콘-숨기기)
3. [아이콘 변경하기](#아이콘-변경하기)
4. [색상 변경하기](#색상-변경하기)
5. [지원되는 타입](#지원되는-타입)

---

## 기본 사용법

Admonition은 마크다운 blockquote 문법을 사용합니다.

```markdown
> [!note]
> 이것은 NOTE 타입의 admonition입니다.
```

### 접기/펼치기 기능

`+` 또는 `-` 기호를 사용하여 접기/펼치기를 제어할 수 있습니다.

```markdown
> [!tip]+
> 기본적으로 펼쳐진 상태

> [!warning]-
> 기본적으로 접힌 상태
```

---

## 아이콘 숨기기

`{hideIcon="true"}` 속성을 사용하여 아이콘을 숨길 수 있습니다.

### 사용 예시

```markdown
> [!note]
> 아이콘이 숨겨진 노트입니다.
{hideIcon="true"}
```

```markdown
> [!important]
> 중요한 정보를 아이콘 없이 표시합니다.
{hideIcon="true"}
```

---

## 아이콘 변경하기

`{icon="아이콘명"}` 속성을 사용하여 커스텀 아이콘을 지정할 수 있습니다.

### 사용 예시

```markdown
> [!note]
> 트위터 아이콘을 사용하는 노트
{icon="twitter"}
```

```markdown
> [!tip]
> 하트 아이콘으로 변경
{icon="heart"}
```

### 사용 가능한 아이콘

Blowfish는 Font Awesome 아이콘을 지원합니다.
아이콘 목록: https://fontawesome.com/icons

---

## 색상 변경하기

`assets/css/custom.css` 파일에서 CSS 변수를 수정하여 색상을 변경할 수 있습니다.

### 라이트 모드 색상 변경

```css
:root {
  /* 테두리 색상 */
  --adm-note-border: #6366f1;
  /* 배경 색상 */
  --adm-note-bg: #e0e7ff;
  /* 텍스트 색상 */
  --adm-note-text: #3730a3;
}
```

### 다크 모드 색상 변경

```css
html.dark {
  --adm-note-bg: #312e81;
  --adm-note-text: #c7d2fe;
}
```

### 전체 예시 (인디고 테마 NOTE)

```css
/* assets/css/custom.css에 추가 */
:root {
  --adm-note-border: #6366f1;
  --adm-note-bg: #e0e7ff;
  --adm-note-text: #3730a3;
}

html.dark {
  --adm-note-bg: #312e81;
  --adm-note-text: #c7d2fe;
}
```

### 여러 타입 색상 변경

```css
:root {
  /* NOTE 타입 */
  --adm-note-border: #6366f1;
  --adm-note-bg: #e0e7ff;
  --adm-note-text: #3730a3;

  /* TIP 타입 */
  --adm-tip-border: #10b981;
  --adm-tip-bg: #d1fae5;
  --adm-tip-text: #064e3b;

  /* WARNING 타입 */
  --adm-warning-border: #f59e0b;
  --adm-warning-bg: #fef3c7;
  --adm-warning-text: #78350f;
}

html.dark {
  --adm-note-bg: #312e81;
  --adm-note-text: #c7d2fe;

  --adm-tip-bg: #064e3b;
  --adm-tip-text: #d1fae5;

  --adm-warning-bg: #78350f;
  --adm-warning-text: #fef3c7;
}
```

---

## 지원되는 타입

### GitHub 스타일 (5가지)

- `[!note]` - 일반 정보
- `[!tip]` - 유용한 팁
- `[!important]` - 중요한 정보
- `[!warning]` - 경고
- `[!caution]` - 주의

### Obsidian 스타일 (확장)

- `[!abstract]` - 요약
- `[!info]` - 정보
- `[!todo]` - 할 일
- `[!success]` - 성공
- `[!question]` - 질문
- `[!failure]` - 실패
- `[!danger]` - 위험
- `[!bug]` - 버그
- `[!example]` - 예시
- `[!quote]` - 인용

---

## 복합 사용 예시

여러 속성을 함께 사용할 수 있습니다.

```markdown
> [!note]+
> 아이콘이 숨겨지고 기본적으로 펼쳐진 노트
{hideIcon="true"}
```

```markdown
> [!important]
> 커스텀 아이콘을 사용하는 중요한 정보
{icon="fire"}
```

```markdown
> [!tip]-
> 기본적으로 접혀있고 커스텀 아이콘을 사용
{icon="lightbulb"}
```

---

## CSS 변수 전체 목록

각 타입별로 3가지 CSS 변수를 제공합니다:

- `--adm-{type}-border`: 테두리 색상
- `--adm-{type}-bg`: 배경 색상
- `--adm-{type}-text`: 텍스트 색상

**사용 가능한 타입:**

- `note`, `tip`, `important`, `warning`, `caution`
- `abstract`, `info`, `todo`, `success`, `question`
- `failure`, `danger`, `bug`, `example`, `quote`

**예시:**

```css
:root {
  --adm-note-border: 색상값;
  --adm-note-bg: 색상값;
  --adm-note-text: 색상값;
}
```

---

## 참고 자료

- [Blowfish 공식 문서 - Alert](https://blowfish.page/docs/shortcodes/#alert)
- [Font Awesome 아이콘](https://fontawesome.com/icons)
- [Tailwind CSS 색상 팔레트](https://tailwindcss.com/docs/customizing-colors)
