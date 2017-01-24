---
title: "setjmp/longjump | Microsoft Docs"
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
ms.assetid: b0e21902-095d-4198-8f9a-b6326525721a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# setjmp/longjump
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Если включить в сборку файл setjmpex.h или setjmp.h, все вызовы [setjmp](../c-runtime-library/reference/setjmp.md) или [longjmp](../c-runtime-library/reference/longjmp.md) приводят к очистке, вызывающей деструкторы и вызовы предложения finally.  Это отличается от платформ x86, в которых включение файла setjmp.h не вызывало предложения finally и деструкторы.  
  
 При вызове функции `setjmp` сохраняется текущий указатель стека, энергонезависимые регистры и регистры MxCsr.  При вызове `longjmp` возвращается последняя точка вызова `setjmp`, указатель стека, энергонезависимые регистры и регистры MxCsr сбрасываются в состояние, сохраненное при последнем вызове `setjmp`.  
  
## См. также  
 [Соглашение о вызовах](../build/calling-convention.md)