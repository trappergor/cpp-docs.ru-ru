---
title: Директивы и операторы данных во встроенном коде на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- data directives [C++]
- __asm keyword [C++], referencing limitations
- MASM (Microsoft Macro Assembler), directives
- directives [C++], MASM
- MASM (Microsoft Macro Assembler), structures
- operators [MASM]
- inline assembly, operators
- inline assembly, data directives
- MASM (Microsoft Macro Assembler), operators
- structures [C++], MASM
ms.assetid: fb7410c7-156a-4131-bcfc-211aa70533e3
ms.openlocfilehash: 916dce0346bebfc5ff65ca558ae75317a187660a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169543"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Директивы и операторы данных во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Хотя в блоке `__asm` можно ссылаться на типы данных и объекты языков C и C++, в нем невозможно определять объекты данных с помощью директив или операторов MASM. В частности, нельзя использовать директивы определения **DB**, `DW`, **DD**, `DQ`, `DT`и `DF`или операторы `DUP` или **this**. Структуры и записи MASM также недоступны. Встроенный ассемблер не принимает директивы `STRUC`, `RECORD`, **ширины**или **маски**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
