---
title: "Admonition 사용 예시"
date: 2026-01-22
draft: false
---

# Admonition 커스터마이징 예시

## 1. 기본 admonition

> [!note]
> 기본 NOTE admonition입니다.

> [!tip]
> TIP admonition입니다.

> [!important]
> IMPORTANT admonition입니다.

> [!warning]
> WARNING admonition입니다.

## 2. 아이콘 숨기기

> [!note]
> 아이콘이 숨겨진 노트입니다.
{hideIcon="true"}

> [!important]
> 아이콘이 숨겨진 중요 메시지입니다.
{hideIcon="true"}

## 3. 커스텀 아이콘

> [!tip]
> 하트 아이콘을 사용하는 팁입니다.
{icon="heart"}

> [!warning]
> 불 아이콘을 사용하는 경고입니다.
{icon="fire"}

> [!note]
> 로켓 아이콘을 사용하는 노트입니다.
{icon="rocket"}

## 4. 접기/펼치기

> [!note]+
> 기본적으로 펼쳐진 상태입니다.

> [!tip]-
> 기본적으로 접힌 상태입니다. 클릭해서 펼쳐보세요!

## 5. 복합 사용

> [!important]+
> 펼쳐진 상태이면서 아이콘이 숨겨진 중요 메시지입니다.
{hideIcon="true"}

> [!warning]-
> 접힌 상태이면서 커스텀 아이콘(경고 삼각형)을 사용합니다.
{icon="triangle-exclamation"}

> [!tip]+
> 펼쳐진 상태이면서 전구 아이콘을 사용합니다.
{icon="lightbulb"}
