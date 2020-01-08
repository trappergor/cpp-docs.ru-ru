---
title: OPTION (MASM)
ms.date: 12/17/2019
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: bd50ac2e051db7f02ac077054e5856524745df54
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318752"
---
# <a name="option"></a>OPTION

Включает и отключает функции ассемблера.

## <a name="syntax"></a>Синтаксис

> **Параметр** *оптионлист*

## <a name="remarks"></a>Заметки

Доступны следующие варианты:

|||||
|-|-|-|-|
|**касемап**|**дотнаме**|**нодотнаме**|**ЭМУЛЯТОР**|
|**ЭМУЛЯТОР**|**ЭПИЛОГА**|**EXPR16**|**EXPR32**|
|**LANGUAGE**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**Ключевое слово "ключевоеслово"**|**носигнекстенд**|**СОБОЙ**|
|**олдмакрос**|**нулдмакрос**|**олдструктс**|**нулдструктс**|
|**PROC**|**Пролог**|**ДОСТУПНО**|**READONLY**|
|**ОБЛАСТИ**|**С неограниченной областью**|**SEGMENT**|**SETIF2**.|

Синтаксис языка — **параметр Language:** <em>x</em>, где *x* — один из C, syscall, stdcall, Pascal, Fortran или Basic.  SYSCALL, PASCAL, FORTRAN и BASIC не поддерживаются с [. МОДЕЛЬ](dot-model.md) плоской.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
