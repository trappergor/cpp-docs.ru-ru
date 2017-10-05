---
title: "Обработка исключений с ++ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling
- Visual C++, exception handling
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9e23f99ad4c2b2a1129fa318fe6960e1c08df21d
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="c-exception-handling"></a>Обработка исключений С++
Язык C++ предоставляет встроенную поддержку для создания и перехвата исключений. При программировании на C++ почти всегда необходимо использовать встроенную поддержку исключений C++, как описано в этом разделе.  
  
 Чтобы включить обработку исключений C++ в коде, используйте [/EHsc](../build/reference/eh-exception-handling-model.md).  
  
## <a name="in-this-section"></a>Содержание  
 В этом описании обработки исключений C++ рассматриваются:  
  
-   [Try, catch и throw-операторы](../cpp/try-throw-and-catch-statements-cpp.md)  
  
-   [Методика оценки блоков Catch](../cpp/how-catch-blocks-are-evaluated-cpp.md)  
  
-   [Исключения и очистка стека](../cpp/exceptions-and-stack-unwinding-in-cpp.md)  
  
-   [Спецификации исключений](../cpp/exception-specifications-throw-cpp.md)  
  
-   [noexcept](../cpp/noexcept-cpp.md)  
  
-   [Необработанные исключения C++](../cpp/unhandled-cpp-exceptions.md)  
  
-   [Сочетание исключений C (структурированные) и C++](../cpp/mixing-c-structured-and-cpp-exceptions.md)  
  
## <a name="support-for-earlier-mfc-exceptions"></a>Поддержка более ранних исключений MFC  
 Начиная с версии 4.0, MFC использует механизм обработки исключений C++. Хотя настоятельно рекомендуется использовать обработку исключений C++ в новом коде, версии MFC 4.0 и выше сохраняют макросы из предыдущих версий MFC, чтобы старый код не пострадал. Макросы и новый механизм также могут сочетаться. Сведения о сочетании макросов и обработки исключений C++ и о преобразовании старого кода для использования нового механизма см. в статьях [исключения: использование макросов MFC и исключений C++](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) и [исключения: преобразование из MFC Макросы исключений](../mfc/exceptions-converting-from-mfc-exception-macros.md). Более ранние макросы исключений MFC, если вы их еще используете, возвращают ключевые слова исключений C++. В разделе [исключения: изменения в макросах исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)
