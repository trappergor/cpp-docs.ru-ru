---
title: 'Исключения: Перехват и удаление исключений | Документация Майкрософт'
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
ms.openlocfilehash: 5bd59cc19c80e305a7e57fb711a49f59a024d528
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434769"
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>Исключения. Перехват и удаление исключений

Следующие инструкции и примеры показывают, как для перехвата и удаление исключений. Дополнительные сведения о **попробуйте**, **catch**, и **throw** ключевые слова, см. в разделе [обработка исключений C++](../cpp/cpp-exception-handling.md).

Обработчиках исключений необходимо удалить объекты исключений, которые они обрабатывают, так как не удалось удалить исключение приводит к утечке памяти каждый раз, когда этот код перехватывает исключение.

Ваш **catch** блок необходимо удалить исключение при:

- **Catch** блок вызывает исключение.

     Конечно не удаляйте исключение при появлении этого исключения еще раз:

     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]

- Выполнение возвращается изнутри **catch** блока.

> [!NOTE]
>  При удалении `CException`, использовать `Delete` функция-член для удаления исключение. Не используйте **удалить** ключевое слово, так как он может завершиться ошибкой, если исключение не в куче.

#### <a name="to-catch-and-delete-exceptions"></a>Для перехвата и удаление исключений

1. Используйте **попробуйте** ключевое слово для настройки **попробуйте** блока. Выполните все инструкции программы, которые могут создавать исключение в **попробуйте** блока.

     Используйте **catch** ключевое слово для настройки **catch** блока. Поместите код обработки исключений в **catch** блока. Код в **catch** блок выполняется только в том случае, если код внутри **попробуйте** блок вызывает исключение типа, указанного в **catch** инструкции.

     Скелет показано как **попробуйте** и **catch** блоки обычно упорядочиваются:

     [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]

     Когда создается исключение, управление передается первой **catch** блок, объявление которого исключение соответствует типу исключения. Можно выборочно обрабатывать различные типы исключений с последующими **catch** блокирует, как показано ниже:

     [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]

Дополнительные сведения см. в разделе [исключения: преобразование из макроса исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md).

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)

