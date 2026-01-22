# 빠른 테스트 가이드

## 1단계: Hugo 서버 재시작

터미널에서 Hugo 서버를 중지하고 다시 시작하세요:

```bash
# Ctrl+C로 중지 후
hugo server
```

## 2단계: 테스트 페이지 접속

브라우저에서 다음 페이지를 열어보세요:
- http://localhost:1313/admonition-examples/

## 3단계: 기능 확인

다음 기능들이 제대로 작동하는지 확인:

### ✅ 아이콘 숨기기
"아이콘 숨기기" 섹션에서 아이콘이 보이지 않아야 합니다.

### ✅ 커스텀 아이콘
"커스텀 아이콘" 섹션에서 하트, 불, 로켓 아이콘이 보여야 합니다.

### ✅ 접기/펼치기
"접기/펼치기" 섹션에서 클릭하여 내용을 접고 펼칠 수 있어야 합니다.

## 사용법 요약

### 아이콘 숨기기
```markdown
> [!note]
> 내용
{hideIcon="true"}
```
**주의**: `{hideIcon="true"}` 앞에 빈 줄이 없어야 합니다!

### 아이콘 변경
```markdown
> [!tip]
> 내용
{icon="heart"}
```

### 색상 변경
`assets/css/custom.css` 파일에서 주석을 해제하고 수정:

```css
:root {
  --adm-note-border: #6366f1;
  --adm-note-bg: #e0e7ff;
  --adm-note-text: #3730a3;
}
```

## 문제가 있다면?

[TROUBLESHOOTING.md](TROUBLESHOOTING.md) 파일을 참고하세요.
