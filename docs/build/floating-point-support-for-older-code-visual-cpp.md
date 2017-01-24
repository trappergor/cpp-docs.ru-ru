---
title: "Поддержка плавающей запятой для устаревшего кода (Visual C++) | Microsoft Docs"
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
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Поддержка плавающей запятой для устаревшего кода (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Регистры MMX и регистры стека для значений с плавающей запятой \(MM0\-MM7\/ST0\-ST7\) сохраняются при переключениях контекста.  Явного соглашения о вызовах для данных регистров не существует.  Использование данных регистров в коде режима ядра строго запрещено.  
  
## См. также  
 [Соглашение о вызовах](../build/calling-convention.md)