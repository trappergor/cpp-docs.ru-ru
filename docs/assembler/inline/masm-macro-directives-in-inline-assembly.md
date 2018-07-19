---
title: Директивы макросов MASM во встроенной сборке | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: cfd8e3ca5fb6bf65a288c17b1754d567b2b081a8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32049855"
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Директивы макросов MASM во встроенном коде на языке ассемблера
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Встроенный ассемблер не является ассемблером макроса. Нельзя использовать директивы макросов MASM (**МАКРОС**, `REPT`, **IRC**, `IRP`, и `ENDM`) или макрос операторов (**<>**, **!** , **&**, `%`, и `.TYPE`). Однако блок `__asm` может использовать директивы препроцессора C. В разделе [использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) для получения дополнительной информации.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)