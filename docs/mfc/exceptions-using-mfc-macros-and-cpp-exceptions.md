---
title: 'Исключения: Использование макросов MFC и исключений C++ | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 698d8a754716f6876f9a72a0d5043807a32d2089
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932212"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>Исключения. Использование макросов MFC и исключений C++
В этой статье рассматриваются рекомендации по написанию кода, использующего обработку исключений макросов MFC и ключевые слова обработки исключений C++.  
  
 В этой статье рассматриваются следующие темы:  
  
-   [Смешивание ключевые слова исключений и макросы](#_core_mixing_exception_keywords_and_macros)  
  
-   [Блоки try внутри блоки catch](#_core_try_blocks_inside_catch_blocks)  
  
##  <a name="_core_mixing_exception_keywords_and_macros"></a> Смешивание ключевые слова исключений и макросы  
 Можно комбинировать макросы исключений MFC и ключевые слова исключений C++ в одной программе. Но нельзя смешивать макросов MFC с ключевые слова исключений C++ в одном блоке, поскольку макросы удаление объектов исключения автоматически при выходе из области видимости, а нет кода с помощью ключевых слов обработки исключений. Дополнительные сведения см. в статье [исключений: исключения перехвата и удаление](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
 Основное различие между макросами и ключевые слова является, что макросы «автоматически» удалить перехваченное исключение, когда исключение выходит из области. Код с помощью ключевых слов не; исключения в блоке catch, необходимо явно удалить. Смешение макросов и ключевые слова исключений C++ можно вызвать утечку памяти, когда объект исключения не удаляется или повреждение в куче при удалении исключения дважды.  
  
 Следующий код, например, делает недействительными указатель исключение:  
  
 [!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]  
  
 Проблема возникает из-за `e` удаляется после выхода из «внутренний» **ПЕРЕХВАТЫВАТЬ** блока. С помощью **THROW_LAST** макрос вместо **THROW** инструкция вызовет «внешней» **ПЕРЕХВАТЫВАТЬ** блок, чтобы получить допустимый указатель:  
  
 [!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]  
  
##  <a name="_core_try_blocks_inside_catch_blocks"></a> Повторите блоки внутри блоков Catch  
 Не удается заново создать исключение, текущий изнутри **повторите** блок, находящийся внутри **ПЕРЕХВАТЫВАТЬ** блока. Следующий пример является недопустимым:  
  
 [!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]  
  
 Дополнительные сведения см. в разделе [исключения: анализ содержимого исключений](../mfc/exceptions-examining-exception-contents.md).  
  
## <a name="see-also"></a>См. также  
 [Обработка исключений](../mfc/exception-handling-in-mfc.md)

