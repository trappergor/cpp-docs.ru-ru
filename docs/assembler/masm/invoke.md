---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: ba1377359ba9bc960e5d7d2a55df15adfe0d5d33
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80076227"
---
# <a name="invoke"></a>INVOKE

(только 32-разрядный MASM.) Вызывает процедуру по адресу, заданному *выражением*, передавая аргументы в стеке или в регистрах в соответствии со стандартными соглашениями о вызовах типа языка.

## <a name="syntax"></a>Синтаксис

> **Вызвать** *выражение* ⟦ __,__ *аргумент* ... ⟧

## <a name="remarks"></a>Примечания

Каждый аргумент, передаваемый в процедуру, может быть выражением, парой регистров или выражением адреса (выражением с префиксом **addr**).

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
