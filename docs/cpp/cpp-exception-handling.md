---
title: "Обработка исключений С++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка исключений С++"
  - "Visual C++, обработка исключений"
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обработка исключений С++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Язык C\+\+ предоставляет встроенную поддержку для создания и перехвата исключений.  При программировании на C\+\+ почти всегда необходимо использовать встроенную поддержку исключений C\+\+, как описано в этом разделе.  
  
 Чтобы включить обработку исключений C\+\+ в коде, используйте [\/EHsc](../build/reference/eh-exception-handling-model.md).  
  
## Содержание  
 В этом описании обработки исключений C\+\+ рассматриваются:  
  
-   [Операторы try, catch и throw](../cpp/try-throw-and-catch-statements-cpp.md)  
  
-   [Методика оценки блоков catch](../Topic/How%20Catch%20Blocks%20are%20Evaluated%20\(C++\).md)  
  
-   [Исключения и очистка стека](../cpp/exceptions-and-stack-unwinding-in-cpp.md)  
  
-   [Спецификации исключений](../cpp/exception-specifications-throw-cpp.md)  
  
-   [noexcept](../Topic/noexcept%20\(C++\).md)  
  
-   [Необработанные исключения C\+\+](../cpp/unhandled-cpp-exceptions.md)  
  
-   [Сочетание исключений C \(структурированные\) и C\+\+](../Topic/Mixing%20C%20\(Structured\)%20and%20C++%20Exceptions.md)  
  
## Поддержка более ранних исключений MFC  
 Начиная с версии 4.0, MFC использует механизм обработки исключений C\+\+.  Хотя настоятельно рекомендуется использовать обработку исключений C\+\+ в новом коде, версии MFC 4.0 и выше сохраняют макросы из предыдущих версий MFC, чтобы старый код не пострадал.  Макросы и новый механизм также могут сочетаться.  Сведения о сочетании макросов и обработки исключений C\+\+ и о преобразовании старого кода для использования нового механизма см. в статьях [Исключения: использование макросов MFC и исключений C\+\+](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) и [Исключения: преобразование из макросов исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md).  Более ранние макросы исключений MFC, если вы их еще используете, возвращают ключевые слова исключений C\+\+.  См. [Исключения: изменения в макросах исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
## См. также  
 [Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)