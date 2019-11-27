---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: e8213052dce8d84d62f90d4bc2653435c2b31434
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398222"
---
# <a name="if-32-bit-masm"></a>. Если (32-разрядный MASM)

Создает код, который проверяет *condition1* (например, AX > 7) и выполняет *инструкции* , если это условие истинно. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> **. Если** *condition1*\
> *инструкции*\
> ⟦ **.\ ELSEIF** *condition2*
> *инструкции*⟧ \
> ⟦ **. ELSE**\
> *инструкции*⟧ \
> **.ENDIF**

## <a name="remarks"></a>Примечания

Если [. В ПРОТИВном](../../assembler/masm/dot-else.md) случае его операторы выполняются, если исходное условие было ложным. Обратите внимание, что условия оцениваются во время выполнения.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)
