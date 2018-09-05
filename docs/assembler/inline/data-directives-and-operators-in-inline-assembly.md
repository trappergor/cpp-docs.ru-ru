---
title: Директивы и операторы во встроенной сборке данных | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aff2f4c5ce5e7f5592aa9ec707d002c57f0eac0
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43678741"
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Директивы и операторы данных во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Хотя в блоке `__asm` можно ссылаться на типы данных и объекты языков C и C++, в нем невозможно определять объекты данных с помощью директив или операторов MASM. В частности, нельзя использовать директивы определения **DB**, `DW`, **дд**, `DQ`, `DT`, и `DF`, или операторов `DUP` или  **Это**. Структуры и записи MASM также недоступны. Встроенный ассемблер не принимает директивы `STRUC`, `RECORD`, **ШИРИНЫ**, или **маска**.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>