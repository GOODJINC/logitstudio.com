# Admonition 커스터마이징 문제 해결

아이콘 숨기기나 변경이 작동하지 않을 때 확인할 사항들입니다.

## 1. Hugo 서버 재시작

레이아웃 파일이나 설정 파일을 변경한 후에는 **반드시 Hugo 서버를 재시작**해야 합니다.

```bash
# Ctrl+C로 서버 중지 후
hugo server
```

## 2. 올바른 문법 사용

### ✅ 올바른 예시

```markdown
> [!note]
> 아이콘이 숨겨진 노트입니다.
{hideIcon="true"}
```

**중요한 점:**
- `{hideIcon="true"}` 앞에 **빈 줄이 없어야** 합니다
- blockquote 바로 다음 줄에 attributes를 작성해야 합니다
- `hideIcon="true"`여야 합니다 (다른 값은 작동하지 않음)

### ❌ 잘못된 예시

```markdown
> [!note]
> 아이콘이 숨겨진 노트입니다.

{hideIcon="true"}  ← 빈 줄이 있으면 안됨!
```

```markdown
> [!note]
> 아이콘이 숨겨진 노트입니다.
{hideIcon="heart"}  ← "true"가 아니면 작동하지 않음!
```

## 3. 아이콘 변경

### ✅ 올바른 예시

```markdown
> [!tip]
> 하트 아이콘을 사용합니다.
{icon="heart"}
```

사용 가능한 아이콘:
- Font Awesome 아이콘 이름 사용
- 예: `heart`, `fire`, `rocket`, `star`, `check`, `lightbulb` 등
- 전체 목록: https://fontawesome.com/icons

## 4. Hugo 버전 확인

Hugo 버전이 0.81.0 이상인지 확인하세요.

```bash
hugo version
```

만약 버전이 낮다면 Hugo를 업데이트하세요.

## 5. 설정 파일 확인

`config/_default/markup.toml` 파일에 다음 설정이 있는지 확인:

```toml
[goldmark]
  [goldmark.parser]
    [goldmark.parser.attribute]
      block = true
      title = true
```

## 6. 브라우저 캐시 삭제

브라우저에서 하드 새로고침을 시도하세요:
- **Windows**: `Ctrl + Shift + R`
- **Mac**: `Cmd + Shift + R`

## 7. 테스트 페이지

제공된 테스트 페이지로 기능을 확인하세요:
- `content/admonition-examples.md` - 모든 기능의 예시
- `content/test-admonition.md` - 상세 테스트

Hugo 서버를 실행한 후 `/admonition-examples/` 또는 `/test-admonition/`으로 접속하세요.

## 8. 디버깅

여전히 작동하지 않는다면, 다음을 확인하세요:

### a. 파일 위치 확인
- `layouts/_default/_markup/render-blockquote.html` 파일이 존재하는지
- `config/_default/markup.toml` 설정이 올바른지

### b. 간단한 테스트
최소한의 예시로 테스트:

```markdown
> [!note]
> 테스트
{hideIcon="true"}
```

### c. 원본 테마 파일 확인
`themes/blowfish/layouts/_default/_markup/render-blockquote.html` 파일이 있다면,
우리가 만든 `layouts/_default/_markup/render-blockquote.html` 파일이 이를 오버라이드해야 합니다.

## 완전한 사용 예시

```markdown
---
title: "테스트 페이지"
date: 2026-01-22
---

# Admonition 테스트

## 아이콘 숨기기
> [!note]
> 아이콘이 보이지 않습니다.
{hideIcon="true"}

## 아이콘 변경
> [!tip]
> 하트 아이콘입니다.
{icon="heart"}

## 접기 + 아이콘 숨기기
> [!important]+
> 펼쳐진 상태이고 아이콘이 없습니다.
{hideIcon="true"}

## 접기 + 커스텀 아이콘
> [!warning]-
> 접힌 상태이고 불 아이콘입니다.
{icon="fire"}
```

## 문의

위의 모든 방법을 시도해도 작동하지 않는다면:
1. Hugo 버전을 확인
2. 에러 메시지가 있는지 터미널 확인
3. 브라우저 개발자 도구(F12)에서 콘솔 에러 확인
