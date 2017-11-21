---
title: "Директивы и операторы во встроенной сборке данных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9875a6d4ee0b061db609f45d574a80a7ee5424ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="data-directives-and-operators-in-inline-assembly"></a>Директивы и операторы данных во встроенном коде на языке ассемблера
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Хотя в блоке `__asm` можно ссылаться на типы данных и объекты языков C и C++, в нем невозможно определять объекты данных с помощью директив или операторов MASM. В частности, нельзя использовать директивы определения **DB**, `DW`, **дд**, `DQ`, `DT`, и `DF`, или операторы `DUP` или  **Это**. Структуры и записи MASM также недоступны. Встроенный ассемблер не принимает директивы `STRUC`, `RECORD`, **ширина**, или **МАСКИ**.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)