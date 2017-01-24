---
title: "Предупреждение компилятора (уровень 4) C4837 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4837"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4837"
ms.assetid: 9a3c7b6b-ffe4-443d-96af-43deb80d85b4
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4837
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

обнаружен триграф: "??%c" заменяется на "%c"  
  
 Обнаруженный триграф заменен на указанный символ.  
  
 Компилятор преобразует триграфы до выполнения какой\-либо другой обработки.  Используйте управляющую последовательность символов, `\?`, чтобы избежать неправильного использования последовательности символов, похожей на триграф.  Дополнительные сведения о триграфах см. в разделе [Триграфы](../Topic/Trigraphs.md).  Дополнительные сведения об управляющих последовательностях см. в разделе [Escape\-последовательности](../../c-language/escape-sequences.md).  
  
 Предупреждение C4837 по умолчанию отключено.  Дополнительные сведения см. в разделе [Выключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
### Исправление этой ошибки  
  
1.  Используйте escape\-последовательность символов, `\?`, вместо одного символа "?" в исходном коде.  
  
## См. также  
 [Триграфы](../Topic/Trigraphs.md)   
 [Escape\-последовательности](../../c-language/escape-sequences.md)   
 [Выключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md)