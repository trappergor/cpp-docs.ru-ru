---
title: "Директивы макроса MASM во встроенной сборке | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "директивы, макросы"
  - "встроенная сборка, директивы макроса"
  - "макросы, директивы"
  - "MASM (макроассемблер Майкрософт), встроенные директивы макроса сборки"
ms.assetid: 83643a09-1699-40a8-8ef2-13502bc4ac2c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Директивы макроса MASM во встроенной сборке
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Майкрософт  
 Встроенный ассемблер не является ассемблером макроса.  Невозможно использовать директивы макроса MASM \(**MACRO**, `REPT`, **IRC**, `IRP` и `ENDM`\) или операторы макроса \(**\<\>**, **\!**, **&**, `%` и `.TYPE`\).  Однако блок `__asm` может использовать директивы препроцессора C.  См. дополнительные сведения в разделе [Использование C или C\+\+ в блоках \_\_asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## См. также  
 [Использование языка ассемблера в блоках \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)