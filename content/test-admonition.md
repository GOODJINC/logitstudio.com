---
title: "Admonition 테스트"
date: 2026-01-22
draft: false
---

# Admonition 기능 테스트

## 1. 기본 사용

> [!note]
> 기본 NOTE admonition입니다.

## 2. 아이콘 숨기기 테스트

> [!note]
> 아이콘이 숨겨져야 합니다.
{hideIcon="true"}

## 3. 아이콘 변경 테스트

> [!tip]
> 하트 아이콘으로 변경되어야 합니다.
{icon="heart"}

## 4. 아이콘 변경 (다른 아이콘)

> [!warning]
> 불 아이콘으로 변경되어야 합니다.
{icon="fire"}

## 5. 접기/펼치기 + 기본 아이콘

> [!important]+
> 기본으로 펼쳐진 상태입니다.

> [!caution]-
> 기본으로 접힌 상태입니다.

## 6. 복합 테스트 - 접기 + 아이콘 숨김

> [!note]+
> 펼쳐진 상태이고 아이콘이 숨겨져야 합니다.
{hideIcon="true"}

## 7. 복합 테스트 - 접기 + 커스텀 아이콘

> [!tip]-
> 접힌 상태이고 전구 아이콘이어야 합니다.
{icon="lightbulb"}
