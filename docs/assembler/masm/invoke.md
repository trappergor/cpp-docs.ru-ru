---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: 7a005e5e70a2696ca89fb0ad1a3ff02aab8ffe5a
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317192"
---
# <a name="invoke"></a>INVOKE

(только 32-разрядный MASM.) Вызывает процедуру по адресу, заданному *выражением*, передавая аргументы в стеке или в регистрах в соответствии со стандартными соглашениями о вызовах типа языка.     

## <a name="syntax"></a>Синтаксис

> **Вызвать** *выражение* ⟦ __,__ *аргумент* ... ⟧

## <a name="remarks"></a>Заметки

Каждый аргумент, передаваемый в процедуру, может быть выражением, парой регистров или выражением адреса (выражением с префиксом **addr**).

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
