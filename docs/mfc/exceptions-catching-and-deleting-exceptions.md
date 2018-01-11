---
title: "Исключения: Перехват и удаление исключений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8496b5228fe4002bb1ca80f8fbe793fd5e16ca81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Исключения. Перехват и удаление исключений
Следующие инструкции и примеры показывают, как перехватить и удаление исключений. Дополнительные сведения о **повторите**, **перехватывать**, и `throw` ключевые слова, в разделе [обработку исключений C++](../cpp/cpp-exception-handling.md).  
  
 Обработчики исключений необходимо удалить объекты исключений, которые они обрабатывают, так как не удалось удалить исключение вызывает утечку памяти, каждый раз, когда этот код перехватывает исключение.  
  
 Ваш **перехватывать** блок необходимо удалить исключение при:  
  
-   **Перехватывать** блок вызывает новое исключение.  
  
     Конечно не требуется удалять исключение, если то же исключение еще раз:  
  
     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]  
  
-   Выполнение возвращается из среды **перехватывать** блока.  
  
> [!NOTE]
>  При удалении `CException`, используйте **удалить** функция-член для удаления исключение. Не используйте **удалить** ключевое слово, так как он может завершиться неудачей, если исключение не в куче.  
  
#### <a name="to-catch-and-delete-exceptions"></a>Для перехвата и удаление исключений  
  
1.  Используйте **повторите** ключевое слово, чтобы настроить **повторите** блока. Выполнять все инструкции программы могут создавать исключение в **повторите** блока.  
  
     Используйте **перехватывать** ключевое слово, чтобы настроить **перехватывать** блока. Поместите код обработки исключений в **перехватывать** блока. Код в **перехватывать** выполняется только в том случае, если блок кода в **повторите** блок вызывает исключение типа, указанного в **перехватывать** инструкции.  
  
     Каркас показано как **повторите** и **перехватывать** блоки, обычно упорядочиваются:  
  
     [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]  
  
     Когда создается исключение, управление передается первой **перехватывать** блока, объявление которого исключение соответствует тип исключения. Можно выборочно обработки различных типов исключений с помощью последовательных **перехватывать** блокируется, как показано ниже:  
  
     [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]  
  
 Дополнительные сведения см. в разделе [исключения: преобразование из макросов исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

