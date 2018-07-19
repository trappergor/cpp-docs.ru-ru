---
title: Комментарии языка ассемблера | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assembly language [C++], comments
- comments [C++], assembly language
- macros [C++], assembly language
- __asm keyword [C++], instructions
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 048635a874db604f872b4fa87d72bd06d0455438
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050767"
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