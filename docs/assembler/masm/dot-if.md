---
title: . ЕСЛИ | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .IF
dev_langs:
- C++
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f7bd5ba5821b4dcfb2d088e31816f50540445018
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691548"
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