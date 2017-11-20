---
title: "Директивы макросов MASM во встроенной сборке | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- directives, macros
- inline assembly, macro directives
- macros, directives
- MASM (Microsoft Macro Assembler), inline assembly macro directives
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f789df759729deb3c2b548efb008ae9a27357ab2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="masm-macro-directives-in-inline-assembly"></a>Директивы макросов MASM во встроенном коде на языке ассемблера
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 Встроенный ассемблер не является ассемблером макроса. Нельзя использовать директивы макросов MASM (**МАКРОС**, `REPT`, **IRC**, `IRP`, и `ENDM`) или макрос операторов (**<>**, **!** ,  **&** , `%`, и `.TYPE`). Однако блок `__asm` может использовать директивы препроцессора C. В разделе [использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md) для получения дополнительной информации.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)