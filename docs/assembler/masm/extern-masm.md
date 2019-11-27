---
title: EXTERN (MASM)
ms.date: 08/30/2018
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: fc66338d90b54ecb12ef3ab1aa56214fb445cb13
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397566"
---
# <a name="extern-masm"></a>EXTERN (MASM)

Определяет одну или несколько внешних переменных, меток или символов *с именем, типом которых* является *Type*.

## <a name="syntax"></a>Синтаксис

> **Extern** ⟦*Language — Type*⟧ *Name* ⟦ __(__ *АЛТИД* __)__ ⟧ __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* ⟦ __(__ *АЛТИД* __)__ ⟧ __:__ *Type* ... ⟧

## <a name="remarks"></a>Примечания

*Тип* может быть [ABS](../../assembler/masm/operator-abs.md), который импортирует *имя* как константу. То же, что и [екстрн](../../assembler/masm/extrn.md).

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)
