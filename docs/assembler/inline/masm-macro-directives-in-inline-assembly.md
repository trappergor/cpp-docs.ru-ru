---
title: Директивы макросов MASM во встроенном коде на языке ассемблера
ms.date: 08/30/2018
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
ms.openlocfilehash: 964f70aeef6e0e62ac4b941b2cc26d3e7c7ef466
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191799"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Директивы макросов MASM во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Встроенный ассемблер не является ассемблером макроса. Нельзя использовать директивы макроопределения MASM (**макрос**, `REPT` , **IRC**, `IRP` и `ENDM` ) или операторы макросов ( **<>** , **!**, **&** , `%` и `.TYPE` ). **`__asm`** Однако блок может использовать директивы препроцессора C. Дополнительные сведения см. [в разделе Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) .

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>
