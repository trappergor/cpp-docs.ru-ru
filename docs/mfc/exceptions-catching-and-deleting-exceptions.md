---
title: 'Исключения: Перехват и удаление исключений | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 29dea08d778ba91c5b8ab3a10aaff998095e7123
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928773"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Исключения. Перехват и удаление исключений
Следующие инструкции и примеры показывают, как перехватить и удаление исключений. Дополнительные сведения о **повторите**, **перехватывать**, и **throw** ключевые слова, в разделе [обработку исключений C++](../cpp/cpp-exception-handling.md).  
  
 Обработчики исключений необходимо удалить объекты исключений, которые они обрабатывают, так как не удалось удалить исключение вызывает утечку памяти, каждый раз, когда этот код перехватывает исключение.  
  
 Ваш **перехватывать** блок необходимо удалить исключение при:  
  
-   **Перехватывать** блок вызывает новое исключение.  
  
     Конечно не требуется удалять исключение, если то же исключение еще раз:  
  
     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]  
  
-   Выполнение возвращается из среды **перехватывать** блока.  
  
> [!NOTE]
>  При удалении `CException`, используйте `Delete` функция-член для удаления исключение. Не используйте **удалить** ключевое слово, так как он может завершиться неудачей, если исключение не в куче.  
  
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

