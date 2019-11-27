---
title: IF (MASM)
ms.date: 08/30/2018
f1_keywords:
- if
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
ms.openlocfilehash: ed7b9e63bb19dcc16539dbdaaf1f6a7f16566b3c
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397454"
---
# <a name="if-masm"></a>IF (MASM)

Предоставляет сборку *ифстатементс* , если *expression1* имеет значение true (отличное от нуля) или *елсеифстатементс* , если *expression1* имеет значение false (0), а *Expression2* имеет значение true.

## <a name="syntax"></a>Синтаксис

> **Если** *expression1*\
> *If-операторы*\
> ⟦**ELSEIF**\ *выражение2*
> *ElseIf-операторы*⟧ \
> ⟦**ELSE**\
> *else-Операторы*⟧ \
> **ENDIF**

## <a name="remarks"></a>Примечания

Следующие директивы могут быть заменены на [ElseIf](../../assembler/masm/elseif-masm.md): **елсеифб**, **елсеифдеф**, **елсеифдиф**, **елсеифдифи**, **ELSEIF**, **елсеифидн**, **елсеифидни**, **елсеифнб**и **елсеифндеф**. При необходимости собирает *else-Операторы* , если предыдущее выражение имеет значение false. Обратите внимание, что выражения оцениваются во время сборки.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)
