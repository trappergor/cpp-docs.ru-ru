---
title: "Комментарии в языке ассемблера | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm - ключевое слово [C++], инструкции"
  - "язык ассемблера [C++], комментарии"
  - "примечания [C++], язык ассемблера"
  - "макросы [C++], язык ассемблера"
ms.assetid: 0dc10850-77f5-426e-9dab-185ea28e06e4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Комментарии в языке ассемблера
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Майкрософт  
 В инструкциях, которые находятся в блоке `__asm`, можно использовать комментарии в стиле языка ассемблера.  
  
```  
__asm mov ax, offset buff ; Load address of buff  
```  
  
 Поскольку макросы C развертываются в одну логическую строку, в них не следует использовать комментарии в стиле ассемблера. \(См. раздел [Определение блоков \_\_asm как макросов C](../../assembler/inline/defining-asm-blocks-as-c-macros.md).\) Блок `__asm` может также содержать комментарии в стиле языка C. Дополнительные сведения см. в разделе [Использование C или C\+\+ в блоках \_\_asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## См. также  
 [Использование языка ассемблера в блоках \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)