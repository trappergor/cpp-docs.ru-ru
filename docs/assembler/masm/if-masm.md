---
title: IF (MASM)
ms.date: 12/17/2019
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: 38d366a3a41e7b08759594899cdcbb2cb84dfbfa
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317296"
---
# <a name="if"></a>IF

Предоставляет сборку *ифстатементс* , если *expression1* имеет значение true (отличное от нуля) или *елсеифстатементс* , если *expression1* имеет значение false (0), а *Expression2* имеет значение true.

## <a name="syntax"></a>Синтаксис

> **Если** *expression1*\
> *If-операторы*\
> ⟦**ELSEIF**\ *выражение2*
> *ElseIf-операторы*⟧ \
> ⟦**ELSE**\
> *else-Операторы*⟧ \
> **ENDIF**

## <a name="remarks"></a>Заметки

Следующие директивы могут быть заменены на [ElseIf](elseif-masm.md): **елсеифб**, **елсеифдеф**, **елсеифдиф**, **елсеифдифи**, **ELSEIF**, **елсеифидн**, **елсеифидни**, **елсеифнб**и **елсеифндеф**. При необходимости собирает *else-Операторы* , если предыдущее выражение имеет значение false. Обратите внимание, что выражения оцениваются во время сборки.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
