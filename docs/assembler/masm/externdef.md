---
title: EXTERNDEF
ms.date: 08/30/2018
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 469b49832c171ee78336a0c457f0d269acd3b59d
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397542"
---
# <a name="externdef"></a>EXTERNDEF

Определяет одну или несколько внешних переменных, меток или символов *с именем, типом которых* является *Type*.

## <a name="syntax"></a>Синтаксис

> **Екстерндеф** ⟦*Language — введите* *имя ⟧* __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* __:__ *Type* ... ⟧

## <a name="remarks"></a>Примечания

Если *имя* определено в модуле, оно считается [открытым](../../assembler/masm/public-masm.md). Если в модуле есть ссылка на *имя* , он рассматривается как [внешний](../../assembler/masm/extern-masm.md). Если ссылка на *имя* не указана, она игнорируется. *Тип* может быть [ABS](../../assembler/masm/operator-abs.md), который импортирует *имя* как константу. Обычно используется в включаемых файлах.

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)
