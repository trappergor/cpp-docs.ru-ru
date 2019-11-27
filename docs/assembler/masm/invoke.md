---
title: INVOKE
ms.date: 11/05/2019
f1_keywords:
- Invoke
helpviewer_keywords:
- INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
ms.openlocfilehash: a5175252364918ca218e81536b29f084f7fd19cc
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397297"
---
# <a name="invoke-32-bit-masm"></a>INVOKE (32-разрядный MASM)

Вызывает процедуру по адресу, заданному *выражением*, передавая аргументы в стеке или в регистрах в соответствии со стандартными соглашениями о вызовах типа языка. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> **Вызвать** *выражение* ⟦ __,__ *аргумент* ... ⟧

## <a name="remarks"></a>Примечания

Каждый аргумент, передаваемый в процедуру, может быть выражением, парой регистров или выражением адреса (выражением с префиксом **addr**).

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)
