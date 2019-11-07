---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: 83c9ff588e2fe273e24e1d0b1c16517c5eee3365
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703777"
---
# <a name="if-32-bit-masm"></a>. Если (32-разрядный MASM)

Создает код, который проверяет `condition1` (например, AX > 7) и выполняет *инструкции* , если это условие истинно. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> . Если condition1<br/>
> операторы<br/>
> [[. ELSEIF condition2<br/>
> Операторы]]<br/>
> [[. Кроме<br/>
> Операторы]]<br/>
> .ENDIF

## <a name="remarks"></a>Заметки

Если [. В ПРОТИВном](../../assembler/masm/dot-else.md) случае его операторы выполняются, если исходное условие было ложным. Обратите внимание, что условия оцениваются во время выполнения.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>