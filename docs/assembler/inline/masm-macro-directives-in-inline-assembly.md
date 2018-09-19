---
title: Директивы макросов MASM во встроенной сборке | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 35ad22a9a4b79a31665ab6b156f8174d395bb0ee
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "43687977"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Директивы макросов MASM во встроенном коде на языке ассемблера

**Блок, относящийся только к системам Microsoft**

Встроенный ассемблер не является ассемблером макроса. Невозможно использовать директивы макроса MASM (**МАКРОС**, `REPT`, **IRC**, `IRP`, и `ENDM`) или операторы макроса (**<>**, **!** , **&**, `%`, и `.TYPE`). Однако блок `__asm` может использовать директивы препроцессора C. См. в разделе [использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) Дополнительные сведения.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)<br/>