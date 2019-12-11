---
title: EXTERNDEF
ms.date: 12/06/2019
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: e757781151bd1bb57940e5c54f7333a5daa93c74
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74987895"
---
# <a name="externdef"></a>EXTERNDEF

Определяет одну или несколько внешних переменных, меток или символов *с именем, типом которых* является *Type*.

## <a name="syntax"></a>Синтаксис

> **Екстерндеф** ⟦*Language — введите* *имя ⟧* __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* __:__ *Type* ... ⟧

## <a name="remarks"></a>Заметки

Аргумент *Language-Type* допустим только в 32-разрядном MASM.

Если *имя* определено в модуле, оно считается [открытым](../../assembler/masm/public-masm.md). Если в модуле есть ссылка на *имя* , он рассматривается как [внешний](../../assembler/masm/extern-masm.md). Если ссылка на *имя* не указана, она игнорируется. *Тип* может быть [ABS](../../assembler/masm/operator-abs.md), который импортирует *имя* как константу. Обычно используется в включаемых файлах.

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)
