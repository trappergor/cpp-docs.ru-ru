---
title: .IF
ms.date: 08/30/2018
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: cf9c594d843c937dd2191bee2a7cebadbc615c82
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62185271"
---
# <a name="if"></a>.IF

Создает код, который проверяет `condition1` (например, AX > 7) и выполняет *инструкций* Если это условие истинно.

## <a name="syntax"></a>Синтаксис

> . Если Условие1<br/>
> операторы<br/>
> [[. ELSEIF condition2<br/>
> операторы]]<br/>
> [[. ELSE<br/>
> операторы]]<br/>
> .ENDIF

## <a name="remarks"></a>Примечания

Если [. ELSE](../../assembler/masm/dot-else.md) следующим, его операторы выполняются в том случае, если исходное состояние была ошибочной. Обратите внимание, что условия проверяются во время выполнения.

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>