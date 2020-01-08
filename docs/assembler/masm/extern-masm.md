---
title: EXTERN (MASM)
ms.date: 12/06/2019
f1_keywords:
- extern
helpviewer_keywords:
- EXTERN directive
ms.assetid: 667d703d-3aaf-4139-a586-29bc5dab1aff
ms.openlocfilehash: 681c4091a3c54a781bed4b01b235dfeb04f552c6
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75318102"
---
# <a name="extern"></a>EXTERN

Определяет одну или несколько внешних переменных, меток или символов *с именем, типом которых* является *Type*.

## <a name="syntax"></a>Синтаксис

> **Extern** ⟦*Language — Type*⟧ *Name* ⟦ __(__ *АЛТИД* __)__ ⟧ __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* ⟦ __(__ *АЛТИД* __)__ ⟧ __:__ *Type* ... ⟧

## <a name="remarks"></a>Заметки

Аргумент *Language-Type* допустим только в 32-разрядном MASM.

*Тип* может быть [ABS](operator-abs.md), который импортирует *имя* как константу. То же, что и [екстрн](extrn.md).

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
