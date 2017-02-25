---
title: "ML Nonfatal Error A2085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2085"
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**инструкция или регистр не принятые в текущем режиме ЦП**  
  
 Предпринята попытка использовать инструкцию, регистр или ключевое слово, которое недопустимо для режима текущего процессора.  
  
 Например, регистры требуют обновления 32 \(sp2\) [0.386](../Topic/.386.md) или выше.  Регистры элемента управления как CR0 требуют привилигированного режима .386P или выше.  Эта ошибка также будет сгенерирована для **NEAR32**"  **FAR32**и  **Плоский** ключевые слова, которые требуются.**386** или выше.  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)