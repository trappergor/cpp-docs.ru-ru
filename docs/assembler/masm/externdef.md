---
title: EXTERNDEF
ms.date: 12/06/2019
f1_keywords:
- EXTERNDEF
helpviewer_keywords:
- EXTERNDEF directive
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
ms.openlocfilehash: 2cc5884a7473da9175a6b6af4b4251314deffeb4
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75313396"
---
# <a name="externdef"></a>EXTERNDEF

Определяет одну или несколько внешних переменных, меток или символов *с именем, типом которых* является *Type*.

## <a name="syntax"></a>Синтаксис

> **Екстерндеф** ⟦*Language — введите* *имя ⟧* __:__ *Type* ⟦ __,__ ⟦*Language-Type*⟧ *Name* __:__ *Type* ... ⟧

## <a name="remarks"></a>Заметки

Аргумент *Language-Type* допустим только в 32-разрядном MASM.

Если *имя* определено в модуле, оно считается [открытым](public-masm.md). Если в модуле есть ссылка на *имя* , он рассматривается как [внешний](extern-masm.md). Если ссылка на *имя* не указана, она игнорируется. *Тип* может быть [ABS](operator-abs.md), который импортирует *имя* как константу. Обычно используется в включаемых файлах.

## <a name="see-also"></a>См. также:

[Справочник по директивам](directives-reference.md)\
[Грамматика MASM BNF](masm-bnf-grammar.md)
