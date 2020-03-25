---
title: Директивы макросов MASM во встроенном коде на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 38b73346fc52f6b5efe478f8eb960ad049fae924
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169283"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Директивы макросов MASM во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Встроенный ассемблер не является ассемблером макроса. Директивы макроопределения MASM нельзя использовать (**макрос**, `REPT`, **IRC**, `IRP`и `ENDM`) или операторы макросов ( **<>** , **!** , **&** , `%`и `.TYPE`). Однако блок `__asm` может использовать директивы препроцессора C. Дополнительные сведения см. [в разделе Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
