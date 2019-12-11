---
title: EXTERN (MASM)
ms.date: 12/06/2019
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 38ea50e75f2a8e19a7a99860f691904053b6739a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74987854"
---
# <a name="extern-masm"></a>EXTERN (MASM)

Определяет одну или несколько внешних переменных, меток или символов *с именем, типом которых* является *Type*.

## <a name="syntax"></a>Синтаксис

> **Extern** ⟦*Language — Type*⟧ *Name* ⟦ __(__ *АЛТИД* __)__ ⟧ __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* ⟦ __(__ *АЛТИД* __)__ ⟧ __:__ *Type* ... ⟧

## <a name="remarks"></a>Заметки

Аргумент *Language-Type* допустим только в 32-разрядном MASM.

*Тип* может быть [ABS](../../assembler/masm/operator-abs.md), который импортирует *имя* как константу. То же, что и [екстрн](../../assembler/masm/extrn.md).

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)
