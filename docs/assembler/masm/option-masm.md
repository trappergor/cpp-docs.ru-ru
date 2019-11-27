---
title: OPTION (MASM)
ms.date: 08/30/2018
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: 0f90ab0115c3dde894d468bbbe60ffa0193b8336
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74395172"
---
# <a name="option-masm"></a>OPTION (MASM)

Включает и отключает функции ассемблера.

## <a name="syntax"></a>Синтаксис

> **Параметр** *оптионлист*

## <a name="remarks"></a>Примечания

Доступные варианты:

|||||
|-|-|-|-|
|**касемап**|**дотнаме**|**нодотнаме**|**ЭМУЛЯТОР**|
|**ЭМУЛЯТОР**|**ЭПИЛОГА**|**EXPR16**|**EXPR32**|
|**ЯЗЫКЕ**|**лжмп**|**нолжмп**|**M510**|
|**NOM510**|**Ключевое слово "ключевоеслово"**|**носигнекстенд**|**СОБОЙ**|
|**олдмакрос**|**нулдмакрос**|**олдструктс**|**нулдструктс**|
|**PROC**|**Пролог**|**ДОСТУПНО**|**READONLY**|
|**ОБЛАСТИ**|**С неограниченной областью**|**SEGMENT**|**SETIF2**.|

Синтаксис языка — **параметр Language:** <em>x</em>, где *x* — один из C, syscall, stdcall, Pascal, Fortran или Basic.  SYSCALL, PASCAL, FORTRAN и BASIC не поддерживаются при использовании с [. МОДЕЛЬ](../../assembler/masm/dot-model.md) плоской.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)
