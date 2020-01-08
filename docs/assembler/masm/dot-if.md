---
title: .IF
ms.date: 11/05/2019
f1_keywords:
- .IF
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
ms.openlocfilehash: 6992ec8b151a83b3f9fa920997845c20caf0476d
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317751"
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

## <a name="remarks"></a>Заметки

Если [. В ПРОТИВном](dot-else.md) случае его операторы выполняются, если исходное условие было ложным. Обратите внимание, что условия оцениваются во время выполнения.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
