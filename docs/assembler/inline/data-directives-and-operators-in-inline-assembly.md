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
ms.openlocfilehash: bcacb0cdd26181da3cf80a582866c1e30567d043
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87192357"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Директивы и операторы данных во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Хотя **`__asm`** блок может ссылаться на типы данных и объекты C или C++, он не может определять объекты данных с директивами и операторами MASM. В частности, нельзя использовать директивы определения **DB**, `DW` , **DD**,, `DQ` `DT` , и `DF` , или операторы `DUP` или. **THIS** Структуры и записи MASM также недоступны. Встроенный ассемблер не принимает директивы, `STRUC` `RECORD` , **ширину**или **маску**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
