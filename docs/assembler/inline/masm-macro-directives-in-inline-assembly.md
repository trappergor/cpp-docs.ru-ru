---
title: Директивы макросов MASM во встроенном коде на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 7e1bed782d28a5bf7c934c3f57f50aae70038578
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508931"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Директивы макросов MASM во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Встроенный ассемблер не является ассемблером макроса. Невозможно использовать директивы макроса MASM (**МАКРОС**, `REPT`, **IRC**, `IRP`, и `ENDM`) или операторы макроса (**<>**, **!** , **&**, `%`, и `.TYPE`). Однако блок `__asm` может использовать директивы препроцессора C. См. в разделе [использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) Дополнительные сведения.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>