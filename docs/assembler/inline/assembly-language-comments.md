---
title: "Комментарии языка ассемблера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee9ab1975a1146b598d7955d15b8e91a0f396724
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="assembly-language-comments"></a>Комментарии языка ассемблера
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 В инструкциях, которые находятся в блоке `__asm`, можно использовать комментарии в стиле языка ассемблера.  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 Поскольку макросы C развертываются в одну логическую строку, в них не следует использовать комментарии в стиле ассемблера. (См. [определение блоков __asm как макросов C](../../assembler/inline/defining-asm-blocks-as-c-macros.md).) `__asm` Блок может также содержать комментарии в стиле C; Дополнительные сведения см. в разделе [использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование языка ассемблера в блоках __asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)